# References

## Main Items Used in Presentation

<!-- == export: main / begin == -->

### Dyff

https://github.com/homeport/dyff

#### Helm Diff Plugin

https://github.com/databus23/helm-diff

### Importer

https://github.com/upsidr/importer

<!-- == export: main / end == -->

---

## Examples Used

<!-- == export: examples / begin == -->

### Argo CD

https://github.com/argoproj/argo-cd

Official Installation spec taken from: https://github.com/argoproj/argo-cd/blob/master/manifests/install.yaml

### FLux

https://github.com/fluxcd/flux

Official Helm Chart taken from: https://github.com/fluxcd/flux/tree/master/chart/flux

### Grafana

https://github.com/grafana/grafana

Community Helm Chart taken from: https://github.com/grafana/helm-charts

## <!-- == export: examples / end == -->

## Others

<!-- == export: other / begin == -->

### ChatOps Setup

Comvent: https://github.com/rytswd/comvent (GitHub Action specific)

Comment event handling logic, which allows creating ChatOps support on GitHub Issues and PRs. This was used extensively for `/run-dyff` setup, and also `/run-importer-update`.

### PR Management

Merge Gatekeeper: https://github.com/upsidr/merge-gatekeeper

Merge Gatekeeper adds extra functionality for managing multiple CI jobs in a single repository. With the GitOps setup, you can easily end up with many CI jobs in the same repository. This job makes sure all CI jobs are clean and successful.

<!-- == export: other / end == -->
