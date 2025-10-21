# KubeAid-config

A template for your own KubeAid instance configuration

# /k8s - you see managed Kubernetes clusters

## example. https://github.com/Obmondo/kubeaid-config/tree/main/k8s/test.cluster.com

name of the cluster: test.cluster.com

and runs these services: https://github.com/Obmondo/kubeaid-config/tree/main/k8s/test.cluster.com/argocd-apps/templates
and uses these values (settings) for those services: https://github.com/Obmondo/kubeaid-config/tree/main/k8s/test.cluster.com/argocd-apps
and here is the config used with kubeaid-cli to spinup/recover cluster https://github.com/Obmondo/kubeaid-config/tree/main/k8s/test.cluster.com - called kubeaid-bootstrap-general.yaml

Documentation for each service - can be found in its corresponding folder. Natively supported apps live in https://github.com/Obmondo/kubeaid/tree/master/argocd-helm-charts   and you can f.ex. read docs specificly for cloudnative-pg (we use for managing postgresql instances) - here: https://github.com/Obmondo/kubeaid/tree/master/argocd-helm-charts/cloudnative-pg


## Kube Prometheus Mixins

You can enable/disable any support mixins from your cluster jsonnet file (k8id-config).
You will to run the build script manually to update the yaml file

```sh
./build/kube-prometheus/build.sh /path/to/k8id-config/k8s/<cluster-name>
```

Now you can do the git add/commit/push and sync it the kube-prometheus app on argocd
Remember to select "Prune" in argocd when you are deleting any mixins

