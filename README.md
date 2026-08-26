Test this with:

```
apiVersion: fleet.cattle.io/v1alpha1
kind: GitRepo
metadata:
  name: oci-bugreport-notworking
  namespace: fleet-local
spec:
  repo: "https://github.com/kklorenzotesta/fleet-oci-bugreport-notworking.git"
  branch: main
  pollingInterval: 60s
  helmSecretName: helm-secret
  helmRepoURLRegex: oci://registry-1\.docker\.io
```

and create a secret:

`kubectl create secret -n fleet-local generic helm-secret --from-literal=username=kklorenzotestagithub --from-literal=password=dckr_pat_ntKjB8qIe7l3Z4nWMqSuMowBRQk`
