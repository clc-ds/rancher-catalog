# Rancher Catalog

ref [Rancher doc](http://docs.rancher.com/rancher/v1.2/en/catalog/private-catalog/)


## Use

One of the primary benefits of the rancher catalog is version updates. Rancher watches the catalog version folders within `/templates` and provides an upgrade available flag when a new version is available. It also provides an upgrade and rollback button to apply changes to the cluster.

### Development

When first placing a container under Rancher control, you will figure out all the settings for that container including resource tagging. When happy with the config, you can edit the stack config to see the docker/rancher compose files that will go in this project.

Note that the rancher-compose.yml has additional catalog related info, like questions to ask the user - don't simply overwrite it.

### Strategy

Latest: on each build, we can update the version 0 compose files as necessary, or just to signal that version 0 has changed. This should be included in the build process.

Release: each tagged release would have a version folder matching the tag. This should also be done as part of the build/release process.
