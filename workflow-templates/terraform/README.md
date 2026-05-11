# terraform

These are the common terraform pipelines, one for CI and one for CD.

## Prerequisites

In order to use these templates you must have setup _Workload Identity Federation_ with your repository.
This is setup in the [gcp-org-management](https://github.com/blok-x-blok/gcp-org-management) repo using the `gha-workload-identity` module.

This needs to be implemented for each environment you want to apply the configuration for. The principle of least privlidge should be followed only granting roles specific to the minimum required for the identity to fully manage the resource declared in the configuration.

Once the workload identities are created, the `GHA_SERVICE_ACCOUNT` and `GHA_WORKLOAD_IDENTITY_PROVIDER` environment specific variables need to be created on the associated repository.
This should be done using the [github-management](https://github.com/blok-x-blok/github-management) repo using the `secrets-variables` module.