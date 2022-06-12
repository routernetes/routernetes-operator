```
make podman-build podman-push
make bundle bundle-build bundle-push
make bundle-build catalog-build

operator-sdk run bundle quay.io/routernetes/routernetes-operator-bundle:v0.0.1 -n operators
operator-sdk cleanup routernetes-operator -n operators
```
