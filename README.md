# Haddadmj Tap

Homebrew casks for my macOS menu-bar apps.

## Install

```sh
brew tap Haddadmj/tap
brew trust Haddadmj/tap
brew install --cask updatebar
```

The `brew trust` step is not optional. Homebrew refuses to load a cask from a
third-party tap until you trust it, because a cask is Ruby that runs on your
machine — it fails with *"Refusing to load cask … from untrusted tap"*
otherwise. Read [`Casks/updatebar.rb`](Casks/updatebar.rb) first if you like;
it is short.

## What's here

| Cask | What it is |
|------|------------|
| [`updatebar`](Casks/updatebar.rb) | [UpdateBar](https://github.com/Haddadmj/UpdateBar) — every pending update on your Mac, in one menu-bar badge |

The apps are signed with a Developer ID and notarized by Apple, so they install
and launch without a Gatekeeper prompt.

## Releasing a new version

The cask in each app's own repository is the source of truth. On a release,
bump `version` and `sha256` there, then copy the file here:

```sh
shasum -a 256 .build/dist/UpdateBar.dmg
```
