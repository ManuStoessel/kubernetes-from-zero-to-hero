# Helm

In this training, we will use Kustomize to create and customize an application.

>Navigate to the folder `27_kustomize` from CLI, before you get started. 

## Verify if kustomize is installed
* Check kustomize
  ```bash
  kustomize version
  ```

## Have a look at the files

* kustomization is the entrypoint for kustomize
```bash
cat kustomization.yaml
```

* patch.yaml is the patch that is going to be overlayed by kustomize
```bash
cat patch.yaml
```

* to see what the patch will change have a look at the base/configmap.yaml
```bash
cat base/configmap.yaml
```

## Use kustomize to patch and apply the resources

* Show resources with applied patch. Mark the prefix `training-`for the names of all resources and the new labels applied.
  ```bash
  kustomize build .
  ```

* Deploy patched resources
  ```bash
  kustomize build . | kubectl apply -f -
  ```

## Cleanup

```bash
kustomize build . | kubectl delete -f -
```

[Jump to Home](../README.md) | [Previous Training](../26_helm/README.md) | [Next Training](../28_prometheus/README.md)