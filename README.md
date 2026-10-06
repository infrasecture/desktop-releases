# Infrasecture - Desktop releases

This public repository distributes binary releases and signed update metadata for **Infrasecture - Desktop**. Application source and build tooling are maintained separately.

## Downloads

Download installers and their verification material from the [Releases page](https://github.com/infrasecture/desktop-releases/releases). macOS Apple Silicon is the first available development target. Each release states its tested platform and limitations.

## Development previews

Clearly marked development prereleases may contain unsigned Apple Silicon `.pkg` installers for team testing. Open the package with macOS Installer, approve administrator installation, then launch **Infrasecture - Desktop Dev** from Applications. Recipients need no Python, Xcode or terminal setup. macOS may require **Privacy & Security → Open Anyway** because these packages are not Developer ID signed or notarized. See the release instructions before installation.

Development previews use separate local state and ad-hoc executable identities. Update them manually with a newer development package; they cannot enter the production signed update channel. Successful installer and dashboard qualification is not a claim of complete planned feature coverage or production readiness.

## Automatic updates

The production application uses this repository as its credential-free release source. Signed TUF metadata is planned under `metadata/stable/` and `metadata/preview/` on `main`. Those channels are not available until trusted metadata has been provisioned and published.

GitHub release labels alone do not authorize an update. The application must verify signed metadata, package integrity, compatibility, and the expected native signing identity before installation.

## Publishing

Assemble each release as a draft, upload and verify all artifacts, then publish it. Published releases are immutable: corrected binaries require a new version. Promote the release through signed channel metadata only after publication.

This repository contains distribution artifacts and public verification material. Private signing keys, credentials, development trust keys and unreviewed local test artifacts do not belong here. Publish development previews only from an identified clean source commit, with checksums, installation instructions and explicit qualification limits.
