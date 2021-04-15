# CI Pipeline

The CI Pipeline is handled by Azure Devops. See `./kubernetes-build-pipeline.yaml` for the main pipeline.

## Review Environments

To review changes, branches can be pushed to `review/<branch-name>`. This will automatically trigger the build process for a review environment. The status of this environment is visible in the pipelines section on Azure Devops.

A typical url would look like:

https://nhsuk-cms-branch-name.nhswebsite-dev.nhs.uk

## Integration

Automatically deployed to integration via the pipeline when a branch is merged to the master branch and will be available at [https://nhswebsite-dev.nhs.uk/](https://nhswebsite-dev.nhs.uk/)

## Staging

Tagged releases are manually created and automatically deployed to staging via the pipeline and will be available at [https://www.nhswebsite-staging.nhs.uk/](https://www.nhswebsite-staging.nhs.uk/)

## Production

Tagged releases which have been tested and approved on staging are manually released to production via the pipeline and will be available at [https://www.nhs.uk/](https://www.nhs.uk/)
