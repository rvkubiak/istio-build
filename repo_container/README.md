# istio-builder

This config rebuilds the Docker container used to host Debian and RedHat package
repositories.  This build should be run any time the dependencies defined in
the Dockerfile are updated.

To update run:
```
gcloud container builds submit --config update_repo_container.yaml .
```

## Dependencies

Packages installed on the build container are documented here.

- **curl** - Used for fetching build dependencies as part of the container
  build.
- **gnupg2** - Used for adding public keys for apt repositories.

- **python** - Required by repo utilities.
- **python-libxml2** - Python bindings required by createrepo
- **python-rpm** - Python bindings required by createrepo
- **python-sqlitecachec** - Metadata parser for Yum required by createrepo
