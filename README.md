# apache-web GitOps repo for NKP

## Layout

```
apps/apache-web/            Helm chart (source of truth for what gets deployed)
  Chart.yaml
  values.yaml
  templates/
clusters/example-workspace/ Flux CRs that tell NKP's GitOps engine to deploy the chart
  apache-web-gitrepository.yaml
  apache-web-helmrelease.yaml
```

Rename `clusters/example-workspace` to match the Workspace/cluster you are
targeting in NKP, and update the `namespace:` fields in the two Flux
manifests to the namespace NKP creates for that Workspace's GitOps
reconciliation (see instructions from Claude for how to find it, or check
via `kubectl get gitrepositories -A` after configuring a repo in the UI).

See the chat response for full step-by-step setup instructions in NKP.
