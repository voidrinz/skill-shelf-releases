# Skill Shelf Releases

Official installers and application updates for Skill Shelf. Source development
is maintained in [voidrinz/skill-shelf](https://github.com/voidrinz/skill-shelf); this repository builds tagged source revisions and
hosts the resulting GitHub Releases.

Download an installer from [Releases](https://github.com/voidrinz/skill-shelf-releases/releases/latest):

Installers will be available after the first release is published.

- macOS Apple Silicon: `skill-shelf-<version>-mac-arm64.dmg`
- macOS Intel: `skill-shelf-<version>-mac-x64.dmg`
- Windows: `skill-shelf-<version>-win-x64.exe`
- Linux: `skill-shelf-<version>-linux-x64.AppImage`

In the installed app, open Settings > About to check for updates, download a
new version, and restart to install it. Closing the main window keeps the app
running in the menu bar/system tray; use Quit to exit.

Published macOS builds require Developer ID signing and notarization. The
current Windows workflow does not configure code signing. Each release includes
`SHA256SUMS`, installer files, blockmaps, and architecture-specific update feeds.

## Maintainer Setup

The build workflow trusts `voidrinz/skill-shelf` by default. Push the source code
and a stable tag matching `desktop/package.json`, such as `v0.1.0`, before
running it. In Actions, **Build And Publish Skill Shelf** can build a preview
with `publish` unchecked; preview artifacts do not create a public release.

For automatic publishing, add `RELEASES_REPO_TOKEN` to the source repository's
Actions secrets. Use a fine-grained token with Contents write access to this
repository. Create a `release` environment here and add the macOS signing and
notarization secrets: `CSC_LINK`, `CSC_KEY_PASSWORD`, `APPLE_ID`,
`APPLE_APP_SPECIFIC_PASSWORD`, and `APPLE_TEAM_ID`.

The complete configuration and release process are documented in the source
repository's [release guide](https://github.com/voidrinz/skill-shelf/blob/main/docs/releases.md).
