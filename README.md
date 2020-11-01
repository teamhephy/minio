
# Hephy Minio v2

[![Build Status](https://travis-ci.org/teamhephy/minio.svg?branch=master)](https://travis-ci.org/teamhephy/minio)
[![Go Report Card](http://goreportcard.com/badge/teamhephy/minio)](http://goreportcard.com/report/teamhephy/minio)
[![Docker Repository on Docker Hub](https://hub.docker.com/r/hephy/minio "Docker Repository on Docker Hub")](https://hub.docker.com/r/hephy/minio)

Hephy (pronounced HEF-ee) Workflow is an open source Platform as a Service (PaaS) that adds a developer-friendly layer to any [Kubernetes](http://kubernetes.io) cluster, making it easy to deploy and manage applications on your own servers.

For more information about the Hephy workflow, please visit the main project page at https://github.com/teamhephy/workflow.

We welcome your input! If you have feedback, please submit an [issue][issues]. If you'd like to participate in development, please read the "Development" section below and submit a [pull request][prs].

# About

The Deis minio component provides an [S3 API][s3-api] compatible object storage server, based on [Minio](http://minio.io), that can be run on Kubernetes. It's intended for use within the [Deis v2 platform][deis-docs] as an object storage server, but it's flexible enough to be run as a standalone pod on any Kubernetes cluster.

Note that in the default [Helm chart for the Deis platform](https://github.com/teamhephy/charts/tree/master/deis-dev), this component is used as a storage location for the following components:

- [hephy/postgres](https://github.com/teamhephy/postgres)
- [hephy/registry](https://github.com/teamhephy/registry)
- [hephy/builder](https://github.com/teamhephy/builder)

Also note that we aren't currently providing this component with any kind of persistent storage, but it may work with [persistent volumes](http://kubernetes.io/docs/user-guide/volumes/).

# Development

The Hephy project welcomes contributions from all developers. The high level process for development matches many other open source projects. See below for an outline.

* Fork this repository
* Make your changes
* Submit a [pull request][prs] (PR) to this repository with your changes, and unit tests whenever possible.
* If your PR fixes any [issues][issues], make sure you write Fixes #1234 in your PR description (where #1234 is the number of the issue you're closing)
* The Hephy core contributors will review your code. After each of them sign off on your code, they'll label your PR with `LGTM1` and `LGTM2` (respectively). Once that happens, you may merge.

## Docker Based Development Environment

The preferred environment for development uses the [`go-dev` Docker image](https://github.com/teamhephy/docker-go-dev). The tools described in this section are used to build, test, package and release each version of Deis.

To use it yourself, you must have [make](https://www.gnu.org/software/make/) installed and Docker installed and running on your local development machine.

If you don't have Docker installed, please go to https://www.docker.com/ to install it.

After you have those dependencies, build your code with `make build` and execute unit tests with `make test`.

## Native Go Development Environment

You can also use the standard go toolchain to build and test if you prefer. To do so, you'll need [glide](https://github.com/Masterminds/glide) 0.9 or above and [Go](http://golang.org/) 1.6 or above installed.

After you have those dependencies, you can build and unit-test your code with `go build` and `go test $(glide nv)`, respectively.

Note that you will not be able to build or push Docker images using this method of development.


## Testing

The Hephy project requires that as much code as possible is unit tested, but the core contributors also recognize that some code must be tested at a higher level (functional or integration tests, for example).

The [end-to-end tests](https://github.com/teamhephy/workflow-e2e) repository has our integration tests. Additionally, the core contributors and members of the community also regularly [dogfood](https://en.wikipedia.org/wiki/Eating_your_own_dog_food) the platform.

## Running End-to-End Tests

Please see [README.md](https://github.com/teamhephy/workflow-e2e/blob/master/README.md) on the end-to-end tests repository for instructions on how to set up your testing environment and run the tests.

## Dogfooding

Please follow the instructions on the [official Hephy docs][hephy-docs] to install and configure your Hephy cluster and all related tools, and deploy and configure an app on Hephy.


[install-k8s]: http://kubernetes.io/gettingstarted/
[s3-api]: http://docs.aws.amazon.com/AmazonS3/latest/API/APIRest.html
[issues]: https://github.com/teamhephy/minio/issues
[prs]: https://github.com/teamhephy/minio/pulls
[hephy-docs]: https://docs.teamhephy.com/
[v2.18]: https://github.com/teamhephy/workflow/releases/tag/v2.18.0
