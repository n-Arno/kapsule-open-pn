kapsule-open-pn
===============

Small test using Kapsule + PN with a pre-created Security Group to keep the cluster open for specific use cases.

The trick is to create the Security Group with the correct name `kubernetes <cluster-id>` before creating the node pool.

Can also be used to specify rules in the Security Group instead of accepting all incoming traffic, for exemple only TCP 80/443 for ingress through the wildcard DNS.

Pre-requisite
-------------

```
brew install make terraform
```

Usage
-----

Build infra:

```
make
```

Clean infra:

```
make clean
```

The cleaning can fail due to instances not being deleted yet (through pool deletion) when the deletion of the Security Group is triggered. Re-apply the destroy will do the job.
