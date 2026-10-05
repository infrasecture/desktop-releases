# Infrasecture - Desktop releases

This public repository distributes binary releases and signed update metadata for **Infrasecture - Desktop**. Application source and build tooling are maintained separately.

## Downloads

Published installers and their verification material will be available on the [Releases page](https://github.com/infrasecture/desktop-releases/releases). Only qualified platform builds are published; macOS is the initial target.

## Automatic updates

The production application uses this repository as its credential-free release source. Signed TUF metadata is planned under `metadata/stable/` and `metadata/preview/` on `main`. Those channels are not available until trusted metadata has been provisioned and published.

GitHub release labels alone do not authorize an update. The application must verify signed metadata, package integrity, compatibility, and the expected native signing identity before installation.

## Publishing

Assemble each release as a draft, upload and verify all artifacts, then publish it. Published releases are immutable: corrected binaries require a new version. Promote the release through signed channel metadata only after publication.

This repository contains distribution artifacts and public verification material. Private signing keys, credentials, development trust keys, and local test builds do not belong here.
