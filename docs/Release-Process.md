# How to do a Kata Containers Release
This document lists the tasks required to create a Kata Release.

## Requirements

- GitHub permissions to run workflows.

## Release Process

### Bump the `VERSION` file

When the `kata-containers/kata-containers` repository is ready for a new release,
first create a PR to set the release in the `VERSION` file and have it merged.

### Check GitHub Actions

We make use of [GitHub actions](https://github.com/features/actions) in the
[release](https://github.com/kata-containers/kata-containers/actions/workflows/release.yaml)
file from the `kata-containers/kata-containers` repository to build and upload
release artifacts.

The action is manually triggered and is responsible for generating a new
release (including a new tag), pushing those to the
`kata-containers/kata-containers` repository.

Check the [actions status
page](https://github.com/kata-containers/kata-containers/actions) to verify all
steps in the actions workflow have completed successfully. On success, a static
tarball containing Kata release artifacts will be uploaded to the [Release
page](https://github.com/kata-containers/kata-containers/releases).

### Improve the release notes

Release notes are auto-generated by the GitHub CLI tool used as part of our
release workflow.  However, some manual tweaking may still be necessary in
order to highlight the most important features and bug fixes in a specific
release.

With this in mind, please, poke @channel on #kata-dev and people who worked on
the release will be able to contribute to that.

### Announce the release

Publish in [Slack and Kata mailing
list](https://github.com/kata-containers/community#join-us) that new release is
ready.
