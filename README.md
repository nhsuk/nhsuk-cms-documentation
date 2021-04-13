# Intro

`nhsuk-cms` is a Wagtail CMS Application used to serve content for [the NHS Website](https://www.nhs.uk).

The production app is run in a [Kubernetes](https://kubernetes.io/) environment, deployed with [Helm](https://helm.sh/).

If you would rather run the app locally without kubernetes in a python environment, see our [dockerless](./getting_started/dockerless.md) documentation.

## K8s Installation

To run the app in a local kubernetes environment, you will need to have installed:

- [Docker](http://docs.docker.com/engine/installation/)
- [Kubernetes](https://kubernetes.io/docs/setup/)
- [Helm](https://helm.sh/docs/intro/quickstart/)
- [Skaffold](https://skaffold.dev/docs/install/)

## K8s Quick Start

Deploy to your kubernetes cluster with skaffold in dev mode.

```sh
skaffold dev --port-forward
```

Visit [http://localhost:8000](http://localhost:8000)

## Contributing

Read the [Style Guide](./development/style-guidelines.md) for guidance on writing code.

Read our [How To](https://confluence.service.nhs.uk/display/NA/How+To) Confluence pages to learn about the development process, how to propose feature requests, logging bugs and testing your build.

## Documentation

You can build the documentation site by running `mkdocs` commands in the `_documentation/` directory, or read the markdown files directly in `./_documentation/docs`.
