# k8s-common
Common apps the IT-SRE clusters will use and include using `kustomize`

# Configuring
To include these apps using kustomize you need to have a `kustomization.yaml` that looks something like this

```
---
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
resources:
- github.com/mozilla-it/k8s-common/sealed-secrets?ref=v0.0.1
- github.com/mozilla-it/k8s-common/kube2iam?ref=v0.0.1
- github.com/mozilla-it/k8s-common/cluster-autoscaler?ref=v0.0.1
- github.com/mozilla-it/k8s-common/external-dns?ref=v0.0.1
- github.com/mozilla-it/k8s-common/dashboard?ref=v0.0.1
- github.com/mozilla-it/k8s-common/metrics-server?ref=v0.0.1
```

To have flux pick this up you need a `.flux.yaml` file that looks like this

```
---
commandUpdated:
  generators:
  - command: kustomize build .
version: 1
```


