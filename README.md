# Digimax updates

Built copies of Digimax's Mac applications, for the update check inside each application.

- **OVS** (Open Video Split): plays one wide film and cuts it into splits for projection.
- **OM** (OpenMapper): mapping and blending for projectors.
- **RMAI**: a panel for a rack-mounted audio interface.

Nothing is here yet. Each application will have one small file here saying what its newest version is (`ovs.json`, `om.json`, `rmai.json`), and each version is a release on this repository carrying the application as a zip.

## How an application uses this

An installed application reads its own file here, at start and once a day. If a newer version is listed it says so. It installs only when a person asks it to.

Every zip is signed. An application checks that signature against a key built into it before it replaces anything, and refuses an update whose signature does not verify. The file's size and SHA-256 are listed beside it for anyone who wants to check by hand.

The check sends nothing about the computer or its user.

## Installing by hand

The applications need a Mac with Apple silicon and macOS 15 or later. They are signed for the Mac that built them, not with an Apple Developer ID, and are not notarised, so macOS marks a downloaded copy as quarantined. After unzipping and moving the application to Applications, remove the mark once in Terminal, for example:

```
xattr -dr com.apple.quarantine /Applications/OVS.app
```

## Source

The source of these applications is not in this repository.

Copyright Digimax Ltd.
