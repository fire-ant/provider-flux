### WIP

As the bootstrap resource is derived from the newer  This provider is dependent on resolution of the following issues:
https://github.com/upbound/upjet/issues/130
https://github.com/upbound/upjet/issues/131

interim workaround - https://github.com/upbound/upjet/issues/121#issuecomment-1290569474

# Provider Flux

`provider-flux` is a [Crossplane](https://crossplane.io/) provider that
is built using [Upjet](https://github.com/upbound/upjet) code
generation tools and exposes XRM-conformant managed resources for the
Flux API.

## Getting Started

Install the provider by using the following command after changing the image tag
to the [latest release](https://marketplace.upbound.io/providers/fire-ant/provider-flux):
```
up ctp provider install fire-ant/provider-flux:v0.1.0
```

Alternatively, you can use declarative installation:
```
cat <<EOF | kubectl apply -f -
apiVersion: pkg.crossplane.io/v1
kind: Provider
metadata:
  name: provider-flux
spec:
  package: fire-ant/provider-flux:v0.1.0
EOF
```

Notice that in this example Provider resource is referencing ControllerConfig with debug enabled.

You can see the API reference [here](https://doc.crds.dev/github.com/fire-ant/provider-flux).

## Developing

Run code-generation pipeline:
```console
go run cmd/generator/main.go "$PWD"
```

Run against a Kubernetes cluster:

```console
make run
```

Build, push, and install:

```console
make all
```

Build binary:

```console
make build
```

## Report a Bug

For filing bugs, suggesting improvements, or requesting new features, please
open an [issue](https://github.com/fire-ant/provider-flux/issues).
