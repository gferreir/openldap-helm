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

### Helm Chart

### Configurations

### Envs

### LDIF files