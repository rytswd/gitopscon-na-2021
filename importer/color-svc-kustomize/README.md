# Kustomize + Importer

Kustomize is flexible and relatively easy to learn - and with Importer, this increases the configuration readability as well.

- `template`: This directory contains the YAML snippets of Kubernetes resource definitions for `color-svc`.
- `base`: Files under this directory is used as base file in Kustomize, and they use Importer to pull in some spec details from `template`.
- `dev`, `qa`, `staging`: With `kustomization.yaml` and patch with strategic merge, some Deployment details are updated.
- `prod`: Simply use `base` as is.
