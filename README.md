# Grafana BOSH Release

A [BOSH](https://bosh.io) release for deploying [Grafana](http://grafana.org/).

## Usage

See [the `grafana` job spec](jobs/grafana/spec).

## Updating to a new version
- Download the tar.gz file from http://grafana.org/ for (called the Binary TAR Linux 64bit) into the blobs folder.
- Make sure to configure your `config/private.yml` for [S3](http://bosh.io/docs/reference/blobs.html#s3)
- Change the path in `packages/grafana/packaging` and `packages/grafana/spec`
- Try to deploy it with `bosh create release --force && bosh upload release && bosh deploy`
- Upload the blob with `bosh upload blobs` and commit
- Create the final release with `bosh create release --final` and commit
