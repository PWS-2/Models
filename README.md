# Models

Protobuf schema definitions for PWS-2, with generated C++ bindings published as release tarballs.

## Layout

```
proto/          Protobuf source files (package `proto`)
buf.yaml        buf module config (lint/breaking rules)
buf.gen.yaml    buf generate config (C++ codegen)
gen/            Generated output (git-ignored, produced by `buf generate`)
```

## Prerequisites

- [buf](https://buf.build/docs/installation)
- [protoc](https://protobuf.dev/installation/)

## Usage

Lint the proto files:

```sh
buf lint
```

Generate C++ bindings into `gen/cpp`:

```sh
buf generate
```

## Releases

Pushing a tag matching `v*` (e.g. `v1.0.0`) triggers [`.github/workflows/release.yml`](.github/workflows/release.yml), which runs `buf generate` and publishes a GitHub Release with the generated C++ sources attached as `pws2model-<tag>.tar.gz`.
