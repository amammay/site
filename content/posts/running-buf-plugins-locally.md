---
date: '2026-03-15T06:00:00-04:00'
draft: false
title: 'Running Buf Plugins Locally'
---

Buf plugins are designed to be run in the cloud, but you can also run them locally. This is useful for testing and
development, and it can also be used to run plugins that are not yet available in the Buf Schema Registry or are
self-hosted.

To get started, clone the [bufbuild/plugins](https://github.com/bufbuild/plugins) repository.
Then, run the following command to build the Go plugins for Protocol Buffers and gRPC:

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
