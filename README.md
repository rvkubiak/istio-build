# istio-build

Tools used to build Istio releases.

## Building Istio with pre-build artifacts

Today Istio is built using pre-built artifacts for the dependencies.  This build
can be performed using the [build_istio_release.yaml](build_istio_release.yaml)
config.

To run this build on Google Container Builder run the following command:
```
gcloud container builds submit --config build_istio_release.yaml --no-source
```

## Building Istio with Repo

Efforts are under way to start building dependencies as part of a release
instead of relying on pre-built artifacts.  Currently this involves using the
Repo tool to create a workspace composed of multiple repositories.  Once the
workspace has been prepared we run Bazel to build Istio and its dependencies.

This build can be performed using the
[build_istio_with_repo.yaml](build_istio_with_repo.yaml) config.

To run this build on Google Container Builder run the following command:
```
gcloud container builds submit --config build_istio_with_repo.yaml --no-source
```

## Building the build container

Configs for generating the build container can be found under
[build_container](build_container/README.md)
