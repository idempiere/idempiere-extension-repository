# Changelog

All notable changes to this extension are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.1] - 2026-10-24

### Changed

* Drop lazy activation so the web bundle starts as Active when it is installed.

### Fixed

* Parse `AuthFailure` log files, which use a longer timestamp than the trace log.
* List only files whose names end in `.log`.

## [1.0.0] - 2025-01-07

### Added

* Browser page at `/log-viewer` with light and dark themes.
* Download an individual log file.
* Delete trace logs and rotate the trace log.
* Require an authorized iDempiere user before the page is shown.
* Optional System Configurator `LOG_VIEWER_LIMIT_SIZE` (bytes) so large files are not rendered in the browser. Default is 50 MB.
