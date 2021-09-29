# Introduction
Kustomize is a tool for customizing Kubernetes configurations. It has the following features to manage application configuration files:

 - generating resources from other sources
 - setting cross-cutting fields for resources
 - composing and customizing collections of resources

Through this repository, I will demonstrate each features by leveraging bluegreen custom resources (check bluegreen repository)

# Requirements

- Openshift 4.5+ (Installed and configured)
- oc cli
- Kustomize

# Setup
**1 - Build Bluegreen application**
```shell
git clone https://github.com/atiouajni/bluegreen
cd bluegreen
oc apply -f openshift-manifests/bluegreen-php/bluegreen-php-buildconfig.yaml
```

# Usage
**1 - Deploy bluegreen application with default color (blue)**

```shell
git clone git clone https://github.com/atiouajni/bluegreen-kustomize
kustomize build ./base | oc apply -f -
```

**2 - Change to green color by applying the overlay

```shell
kustomize build ./overlay/green | oc apply -f -

```
# Documentation

More details will be found in ./docs folder.

