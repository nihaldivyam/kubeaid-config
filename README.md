# kubeaid-config repo [Template]

## Directory Structure

```raw
k8s/
├── common  # common static yamls for all cluster
│   └── argocd-apps
├── dev.k8s.com  # your cluster name
│   ├── argocd-apps  # all the argocd apps
│   │   └── templates
│   ├── kube-prometheus # Monitoring setup
│   └── sealed-secrets  # secret encrypted with sealed-secret
│       ├── argocd
│       ├── cert-manager
│       ├── monitoring
│       ├── obmondo-website
│       └── traefik
```
## Kube Prometheus Mixins

You can enable/disable any support mixins from your cluster jsonnet file (kubeaid-config).
You will to run the build script manually to update the yaml file

```sh
./build/kube-prometheus/build.sh /path/to/kubeaid-config/k8s/<cluster-name>
```

Now you can do the git add/commit/push and sync it the kube-prometheus app on argocd
Remember to select "Prune" in argocd when you are deleting any mixins
