# Changelog

All notable changes to this extension are documented in this file.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [1.0.1] - 2021-12-06

### Added
- Primary key on the translation table `BXS_DocValidation_Trl` (`2Pack_1.0.1`).

### Fixed
- Where clauses containing `OR` are now surrounded with parentheses, so a condition such as
  `a = 1 OR b = 2` is evaluated as intended instead of leaking into the surrounding SQL.
- The plugin no longer fails at startup with "No Database Connection" when it activates before the
  database is available.
- The first validation message no longer starts with a stray `<br>`.

## [1.0.0] - 2021-01-22

### Added
- Initial release: `BXS_DocValidation` table, the **Document Status Validation** window, and the
  document-event validator that evaluates configured SQL conditions on status changes.
