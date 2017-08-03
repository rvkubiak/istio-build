# istio-build

This config rebuilds the Docker container used to perform Istio builds and
uploads to GCR.  This build should be run any time the dependencies defined in
the Dockerfile are updated.

To update run:
  gcloud container builds submit --config update_build_container.yaml .
