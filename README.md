# Updates

A signed update feed for Prism and Mesh, two of the Mac applications of the **Lucid Dreams** show software (Iziko,
2026).

**Dormant.** There are no feed files or releases here yet, and nothing reads this repository: the show's
applications update through Deck, the show controller on each show Mac, from a private store. This feed is kept for
a possible public update path later.

| Application | What it is | Feed file | Release tags |
|---|---|---|---|
| **Prism** (formerly OVS) | Plays one wide film and cuts it into splits for projection | `ovs.json` | `ovs-v<version>` |
| **Mesh** (formerly OM, OpenMapper) | Mapping and blending for projectors | `om.json` | `om-v<version>` |

The feed files keep the applications' old names (`ovs`, `om`), as do the bundle identifiers, so that copies already
installed keep finding them.

Nothing is here yet: the release signing key has not been made, so no version has been published here. If the feed
is ever used, each application will have one small file here saying what its newest version is, and each version
will be a release on this repository carrying the application as a zip.

## How an application would use this

An installed application would read its own file here, at start and once a day. If a newer version is listed it says so.
It installs only when a person asks it to.

Every zip is signed. An application checks that signature against a key built into it before it replaces anything,
and refuses an update whose signature does not verify. The file's size and SHA-256 are listed beside it for anyone
who wants to check by hand.

The check sends nothing about the computer or its user.

## Installing by hand

The applications need a Mac with Apple silicon and macOS 15 or later. They are signed for the Mac that built them,
not with an Apple Developer ID, and are not notarised, so macOS marks a downloaded copy as quarantined. After
unzipping and moving the application to Applications, remove the mark once in Terminal, for example:

```
xattr -dr com.apple.quarantine /Applications/Prism.app
```

## Source

The source of these applications is not in this repository.

Copyright (c) 2026 UWC Immersive Zone, University of the Western Cape. MIT licence: see [LICENSE](LICENSE).
