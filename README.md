# NAS / Plex Tools

A Python toolkit for managing a large movie and TV library on a NAS so Plex picks it up cleanly — rename files to the format Plex wants, flatten boxset collections, backfill missing metadata from TMDB, and catalog the whole library for easy restore.

> *This repo is a public overview. The running code is private.*

---

## What it is

Plex is very picky about filenames. A library built over years has inconsistent naming, zipped collections, missing years in titles, and box-set folders Plex can't parse. This toolkit fixes all of that in place — a handful of small Python scripts, each solving one specific failure mode.

## What it does

- **Renames to Plex format** — `Title (Year).ext`, pulling the year from TMDB if it's missing
- **Flattens collections** — box-set folders become individual movie folders Plex can match
- **Backfills metadata** via TMDB API — year, canonical title, alternate names
- **Scans for duplicates** and reports which copy to keep (biggest + highest-resolution wins)
- **Catalogs the library** as a manifest so a future disk failure doesn't lose the organization work
- **Dry-run first** — every script runs in preview mode before touching files

## Software

| Layer | Tech |
|---|---|
| Scripts | Python |
| Metadata | TMDB API |
| Storage target | NAS (SMB mount) |
| Consumer | Plex Media Server |

## What this demonstrates

- **Defensive file-system work** — dry-run mode, manifest-based backups, no batch-rename surprises
- **Practical API integration** — TMDB for the long tail of missing metadata
- **Library-scale pipelines** — built to handle thousands of files without choking

## Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Plex](https://img.shields.io/badge/Plex-E5A00D?style=flat&logo=plex&logoColor=white)
![TMDB](https://img.shields.io/badge/TMDB-01B4E4?style=flat&logo=themoviedatabase&logoColor=white)

---

Part of the AIOS portfolio. See the [profile README](https://github.com/mikecutillo) for the full system map.
