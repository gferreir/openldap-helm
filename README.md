# openldap-helm

> Project to deploy openLDAP + phpLDAPadmin on Kubernetes using Helm Chart

## Summary

- [openldap-helm](#openldap-helm)
  - [Summary](#summary)
  - [Considerations](#considerations)
  - [Usage](#usage)
    - [Helm Chart](#helm-chart)
    - [Configurations](#configurations)
    - [Envs](#envs)
    - [LDIF files](#ldif-files)

## Considerations

Sometimes you need a ldap server to integrate with an application to do a POC or something else.

If your application or solution is on a cloud envrionment, like [Kubernetes](https://kubernetes.io/) or [Openshift](https://www.redhat.com/en/technologies/cloud-computing/openshift), waiting for credentials or even if the environment doesn't have access to an external ldap server can be a pain.

Thinking on this, this project can facilitate all these issues. This project covers to deploy an instance of [OpenLDAP](https://hub.docker.com/r/bitnami/openldap/) and [phpLDAPadmin](https://github.com/osixia/docker-phpLDAPadmin), on those cloud environments.

## Usage

This repo is ready to go, so you can deploy in a kubernetes environment.

### Helm Chart

To deploy natively on kubernetes, we are using [Helm Chart](https://helm.sh/) to make the job more easy.

To deploy you'll need:
- Kubernetes environment
- Credentials with the necessary permissions

> *first you need to clone this repo... (:*

```sh
helm install openldap ./
```

If you want to delete all resources, you can:

```sh
helm uninstall openldap ./
```

If you make any change in the chart, you can simply update it:

```sh
helm upgrade openldap ./
```

### Configurations

### Envs

### LDIF files