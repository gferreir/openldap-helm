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
  - [Final considerations](#final-considerations)

## Considerations

Sometimes you need a ldap server to integrate with an application to do a POC or something else.

If your application or solution is on a cloud environment, like [Kubernetes](https://kubernetes.io/) or [Openshift](https://www.redhat.com/en/technologies/cloud-computing/openshift), waiting for credentials or even if the environment doesn't have access to an external ldap server can be a pain.

Thinking on this, this project can facilitate all these issues. This project covers deploying an instance of [OpenLDAP](https://hub.docker.com/r/bitnami/openldap/) and [phpLDAPadmin](https://github.com/osixia/docker-phpLDAPadmin), on those cloud environments.

## Usage

This repo is ready to go, so you can deploy it in a Kubernetes environment. Also, you can change some [configurations](#configurations) before.

### Helm Chart

To deploy natively on Kubernetes, we are using [Helm Chart](https://helm.sh/) to make the job easier.

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

One of the reasons to create this project using Helm Chart, is the easy way to configure everything. Saying that next you can see the configurations options.

### Envs

Taking advantage of Helm Chart, all configurable environments are on the `values.yaml` file.

About openLDAP we can list the main configurations:
- **openldap.adminUser**: admin user. AKA login DN. Default value: *admin*
- **openldap.adminPassword**: admin password of login DN. Default value: *adminpassord*
- **openldap.isPersistent**: if true a PVC will be created to persist the openLDAP database. Default value: *true*
- **openldap.pvcSize**: PVC size if it was created. Default value: *1Gi*

### LDIF files

The openLDAP has a mechanism to import a [LDIF](https://ldap.com/ldif-the-ldap-data-interchange-format/) file, which it contains all the instructions to populate the database in the server startup.

This project contains a LDIF file to demonstrate this feature. You can find it at `populateLdap.ldif`.

## Final considerations

This project is functional but is far from the ideal state. You can find more information about the solutions that I've used here on their respective sites ([OpenLDAP](https://hub.docker.com/r/bitnami/openldap/) and [phpLDAPadmin](https://github.com/osixia/docker-phpLDAPadmin)).

Also, you are invited to contribute (if you want of course).