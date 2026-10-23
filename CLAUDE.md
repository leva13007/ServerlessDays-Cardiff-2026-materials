# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Raw media captured at a two-day conference: a workshop on 2026-10-20 and a day of talks on 2026-10-21. It holds photos, audio recordings and their transcripts, and no code, so there is nothing to build, lint or test. Total size is about 400 MB, mostly `.jpg` and `.m4a`.

This directory is not its own git repo. The nearest repo is the root `~/projects` management layer, whose default-deny `.gitignore` excludes it, so nothing here is version-controlled. Don't delete or rename the originals: no other copy exists.

## Layout

- `00/`: opening and organiser segment. Photos sit directly in the folder, alongside `audio/` and `transcripts/`.
- `01_workshop/`: day-1 workshop photos only, in a flat folder with no audio.
- `02_…` to `11_…`: one folder per day-2 talk, numbered in running order and named after the speaker or company (e.g. `07_Gunnar_Grosch`, `05_FinTech Wales`, which contains a space, so quote paths). Each one has:
  - `audio/`: the recording(s) of the talk as `.m4a`
  - `transcripts/`: a `.txt` and a `.srt` for each audio file, with the same basename
  - `photo/`: photos of slides and the stage

A talk can be split across two recordings (e.g. `…_1422_DJI_14` and `…_1453_DJI_14`). Read them in timestamp order to get the full talk.

## File naming

`YYYY-MM-DD_HHMM_<source>.<ext>`, where the time is local capture time:

- `DJI_NN`: audio from a DJI wireless mic. `NN` is the mic's recording index, not the talk number.
- `IMG_NNNN`: phone photo.
- `nodate_camphoto_<id>_<n>.jpg`: photos with no capture date in their metadata.

Because the timestamp is in the filename, a plain sort gives chronological order. You can match a photo to the transcript section it belongs to by comparing the photo's `HHMM` with the audio's start time plus the `.srt` offset.

## Transcripts

- The transcripts are automatic speech recognition (ASR) output, not edited. Expect misheard names, product names and technical terms, and check them against the slide photos before quoting.
- `.srt` holds the timestamped segments, starting at `00:00:00` for each audio file. `.txt` holds the same text with no timing, and its line wrapping differs between files.
- `README.md` holds the agenda. It has the official slot time, the actual recording time and each speaker's correct name and role (taken from the official agenda in `image-1.png`), so use it as the source of truth for names, not the transcripts. Running order changed on the day, and two speakers were replaced, so folder numbers follow the order recordings were made rather than the official slots.
