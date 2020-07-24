# Torrentinim

Torrentinim is a self-hosted API-only, low memory footprint, torrent search engine and crawler.

### Goals

- **API-only**
- Crawl multiple index sites for torrents and magnet links.
- **[TODO]** Easily integrates with both [Sonarr](https://github.com/Sonarr/Sonarr) and [Radarr](https://github.com/Radarr/Radarr).
- Run without ceremony. You download a binary, run it, that's it.
- Easy to understand source code. Special care is taken to keep code lean and understandable. No code golf here.
- High performance, extremely low memory footprint.
  - RAM usage (avg.): **21.5MB**
  - Binary application size: **1.2MB**

We work closely with other providers and search engines to be respectful of their
hardware and minimize our impact to their systems. Want torrentinim to support your
site? Please open a Github Issue in this repo.

### Usage Guide

Torrentinim was designed to be painless to run. You download an executable, and run it. Done.
It will start slurping up data from supported sources automatically.

The `init` flag initializes the database. All subsequent runs should not include `init` or you
will nuke your entire database.

```
$ ./torrentinim init
INFO Jester is making jokes at http://0.0.0.0:5000
Starting 1 threads
```

Subsequent runs, don't use the `init` flag!

```
$ ./torrentinim
INFO Jester is making jokes at http://0.0.0.0:5000
Starting 1 threads
```

### Community

Want to talk about Torrentinim or suggest features? We have an official Discord server.

[Click to join our official Discord server](https://discord.gg/CFtGUaW)

### Development

You need at least Nim 1.2.0

1. Clone the project
2. `nimble install`
3. `nimble run torrentinim`

To compile release:

>nim c -d:danger -d:ssl --threads:on -d:release --opt:size src/torrentinim.nim

### Supported websites

The following websites are fully supported.

- 1337x.to
- EZTV
- Nyaa
- NyaaPantsu
- TorrentDownloads.me
- YTS