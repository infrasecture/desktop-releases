# Infrasecture Desktop releases

This public repository distributes binary releases and signed update metadata for **Infrasecture Desktop**. Application source and build tooling are maintained separately.

## Downloads

Download installers and their verification material from the [Releases page](https://github.com/infrasecture/desktop-releases/releases). macOS Apple Silicon is the first available development target. Each release states its tested platform and limitations.

Choose the `.pkg` installer. GitHub also automatically displays **Source code (zip)** and **Source code (tar.gz)** links: these archive this releases-only repository's public documentation/metadata, not the application's source. Application source is private and is never included in public releases. See [GitHub's explanation of these automatic archives](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases).

## Development previews

Team-testing builds are published as normal releases with unsigned Apple Silicon `.pkg` installers and explicit development-build limits. Open the package with macOS Installer, approve administrator installation, then launch **Infrasecture Desktop** from Applications. Recipients need no Python, Xcode or terminal setup. macOS may require **Privacy & Security → Open Anyway** because these packages are not Developer ID signed or notarized. See the release instructions before installation.

Development previews use separate local state and ad-hoc executable identities. Update them manually with a newer development package; they cannot enter the production signed update channel. Successful installer and dashboard qualification is not a claim of complete planned feature coverage or production readiness.

## Automatic updates

The production application uses this repository as its credential-free release source. Signed TUF metadata is planned under `metadata/stable/` and `metadata/preview/` on `main`. Those channels are not available until trusted metadata has been provisioned and published.

GitHub release labels alone do not authorize an update. The application must verify signed metadata, package integrity, compatibility, and the expected native signing identity before installation.

## Publishing

Prepare and verify the exact artifacts and installation instructions locally, then publish the team installer as a normal release. Verify its public downloads, checksums and release flags. Published releases are immutable: corrected binaries require a new version. Promote production releases through signed channel metadata only after publication and trust qualification.

This repository contains distribution artifacts and public verification material. Private signing keys, credentials, development trust keys and unreviewed local test artifacts do not belong here. Publish development previews only from an identified clean source commit, with checksums, installation instructions and explicit qualification limits.

Never publish application source trees, build/test tools, source maps, debug bundles or source archives. Inspect the exact installer contents and release assets before publication. Compiled runtime assets and required package scripts/licenses belong in installers. Create tags only on this repository's distribution commits; never push application source commits, branches or history here.
