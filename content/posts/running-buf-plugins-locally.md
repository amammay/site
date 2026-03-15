---
date: '2026-03-15T06:00:00-04:00'
draft: false
title: 'Running Buf Plugins Locally'
---

Buf plugins are designed to run in the cloud, but you can also run them locally. This is useful for testing,
development, and running plugins that are self-hosted or not yet available in the Buf Schema Registry.

In this example, we will use the Go plugins for Protocol Buffers and gRPC.

To get started, clone the [bufbuild/plugins](https://github.com/bufbuild/plugins) repository. Then, run the following
command to build the Go plugins for Protocol Buffers and gRPC:

```shell
make PLUGINS="protocolbuffers/go grpc/go" build
```

Finally, update your `buf.gen.yaml` to use the local plugins:

```diff
version: v2
clean: true
managed:
  enabled: true
  override:
    - file_option: go_package_prefix
      value: github.com/amammay/genplay/gen
plugins:
-  - remote: buf.build/protocolbuffers/go:v1.36.11
-    out: gen/go
-    opt:
-      - paths=source_relative
-  - remote: buf.build/grpc/go:v1.6.1
-    out: gen/go
-    opt:
-      - paths=source_relative
+  - local: ["docker", "run", "-i", "-a", "stdin", "-a", "stdout", "-a", "stderr", "bufbuild/plugins-grpc-go:v1.6.1"]
+    out: gen/go
+    opt:
+      - paths=source_relative
+  - local: ["docker", "run", "-i", "-a", "stdin", "-a", "stdout", "-a", "stderr", "bufbuild/plugins-protocolbuffers-go:v1.36.11"]
+    out: gen/go
+    opt:
+      - paths=source_relative
```

The important thing to note here is the attaching of stdin, stdout, and stderr to the Docker container. This allows Buf
to communicate with the plugin via standard input and output. The `-i` flag keeps stdin open when running the container.
