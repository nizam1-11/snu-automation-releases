# SAM Automation - releases

This repository is the **auto-update feed** for SAM Automation.

It holds no source code. Every release carries exactly three files:

| File | Purpose |
|---|---|
| `latest.yml` | the update manifest the app polls for (version, sha512, size) |
| `SAM-Automation-Setup-<version>.exe` | the Windows installer |
| `SAM-Automation-Setup-<version>.exe.blockmap` | the delta-update map for that installer |

The app fetches `<publish.url>/latest.yml`, where `publish.url` is set in the project
`electron-builder.yml`. When a newer version is published here, running installs find it
on the next check (silently, every 6 hours and on every launch) and show an Update button
in the sidebar.

Publishing a new version: see the README in the SAM Automation project, section 5.
