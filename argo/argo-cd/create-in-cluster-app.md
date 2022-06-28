
CLI
```
argocd app create --name test \
--repo https://github.com/marcel-dempers/docker-development-youtube-series \
--dest-server https://kubernetes.default.svc \
--dest-namespace marcel --path kubernetes
```

YAML

```
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: test
  namespace: satya
spec:
  project: default
  source:
    repoURL: https://github.com/bvsatyanarayana/argocd.git
    targetRevision: HEAD
    path: argo/example-app
  destination:
    server: https://kubernetes.default.svc
    namespace: satya
```

```
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: sealed-secrets
  namespace: argocd
spec:
  project: default
  source:
    chart: sealed-secrets
    repoURL: https://bitnami-labs.github.io/sealed-secrets
    targetRevision: 1.16.1
    helm:
      releaseName: sealed-secrets
  destination:
    server: "https://kubernetes.default.svc"
    namespace: kubeseal
    
```


