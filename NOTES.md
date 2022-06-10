```
make docker-build docker-push
make bundle bundle-build bundle-push

operator-sdk run bundle quay.io/routernetes/routernetes-operator-bundle:v0.0.1 -n operators
operator-sdk cleanup routernetes-operator -n operators
```
