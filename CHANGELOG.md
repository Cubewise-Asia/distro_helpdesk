# Changelog

All notable changes for **Distro** releases and this helpdesk are recorded here.

## [5.1.0] - latest
### New Features
* **Turbo bursting:** A revolutionary new report-processing engine delivers dramatically faster TM1Web report exports — up to ~10× faster.
* **Faster merging & large workbooks:** Major speed-ups for multi-report merging and large-workbook generation (up to ~16× faster).
* **AnyShare integration:** New AnyShare cloud storage support for report distribution.
* **Asset-level distribution:** Distribute individual assets, with productized variable enhancements.
* **Storage validation:** New storage validation workflow and clearer execution-failure diagnostics.

### Improvements
* Improved stability and reliability under high-volume bursts.
* More reliable TM1Web export sessions with clearer diagnostics.
* Improved PAW report connectivity and handling.
* Smoother installation and updates on Linux and Windows.
* Better support for on-premise and private-cloud environments.

### Bug Fixes
* Improved PowerPoint template compatibility.
* Better preservation of Excel formatting, protection, and sparklines during export.
* Preserved Chinese sheet names and fixed distribution path handling.
* Kept email recipients active on profile switch; email body now defaults to rich HTML.

## [5.0.0] - 2026-05-21
### New Features
* **Apliqo NextGen / UX export:** First-class support for exporting Apliqo NextGen (UX) reports.
* **Alert emails:** Automatic alert emails for bursting failures and source disconnects.
* **Tools API:** New tools for distribution file download and Excel-to-CSV conversion.
* **Profile Migration:** Export, import, and update profiles between environments.
* **Platform modernization:** Rebuilt on a modern application platform for better performance and scalability.

### Improvements
* More stable export processing and improved resource handling under load.
* Stricter request validation and improved SMTP TLS trust controls.

### Security
* Admin-driven password reset and first-login password-change enforcement.

### Bug Fixes
* Fixed UX and TM1Web XLSX exports that could produce blank or missing files.
* Fixed NextGen login and variable-picker issues.
* Fixed loss of email recipients when switching profile tabs.
* Fixed PowerPoint waterfall and ChartEx export regressions.
* Fixed profile import/export duplicate-variable and ordering issues.

### Notes
* Self-hosted deployments run on Python 3.12 and Node.js 22.

## [4.5.3] - 2026-02-10
### New Features
* **Performance Boost:** Significantly improved the performance for **replacing formulas** during the merge process.
* **UX Enhancements:** * Added **free-text input** in the asset filter for more flexible searching. (#374)
    * Expanded **email body length** limits to support larger notification contents. (#359)
* **Build Improvements:** Upgraded frontend runtime to **Node 22** for faster and more modern builds. (#331)

### Bug Fixes
* **Database & Migration:**
    * Fixed **MS SQL Server** compatibility issues regarding `datetime` formats and `UNIQUE` constraints. (#340, #343)
    * Resolved database migration errors specifically affecting MS SQL environments.
* **System Stability:**
    * Fixed a critical bug where **bursting** could not be performed. (#345)
    * Resolved "Operation Timed Out" issues during distro execution. (#345)
    * Improved file saving stability and fixed scanning document issues. (#361)
    * Fixed service initialization order to prevent startup failures in certain environments. (#339)
* **API & Connectivity:**
    * Fixed API endpoint mismatches caused by incorrect trailing slashes. (#337)
    * Resolved email sending failures by updating field requirements in basic authentication. (#349)
    * Fixed an issue where ZIP files could not be renamed during export. (#363)
* **General:**
    * Fixed UI translation errors. (#375)
    * Cleaned up unused third-party libraries and removed redundant log messages from `ProgramData`. (#348, #359)

### Documentation
* Added detailed documentation for Distro features and usage rules.
* Updated incorrect README rules regarding private and public access. (#358)

## [4.5.2] - 2025-11-24
### Added
- SMTP OAuth support.
- Key Vault integration for client secrets.
### Changed
- [#332] CAM namespace may be optional when logging in with CAM.
- [#330] User passwords now support special characters.
- [#322] Fixed various frontend vulnerabilities.
- [#298] Improved handling for variables with special text.
### Fixed
- [#320] Fixed profile issue where UX data could not be displayed in email body.

## [4.4.2] - 2025-03-20
### Added
- Public/private profiles.
- Public/private schedules.
- API keys respect user access levels.
- Integrated HashiCorp Vault for key vault.
- Validation for the server URL in the Source System modal.
### Changed
- Improved combofield component in protocol selection.
- Enabled profiles to send emails with CC only.
- Enhanced formatting of user information after CAM login.

## [4.3.2] - 2024-12-31
### Added
- Support using CAM SSO to log in.
- Configuration for Flask Limiter default limits.
### Changed
- Improved frontend error messages to avoid showing HTML tags.
- User group is no longer required when creating/updating a user.

## [4.3.1]
### Fixed
- Added missing `flask-limiter` dependency for login rate limiting (see #217).

## [4.2.4]
### Fixed
- [#215] Failed to update user.

## [4.2.2]
### Changed
- Updated prompt messaging when a user password does not match.

## [4.2.1]
### Fixed
- [#179] PAW and UX file extension dependency issue.

## [4.2.0]
### Fixed
- [#166] Log configuration generation failure.

## [4.1.3]
### Notes
- Patch release.

## [4.1.2]
### Added
- New release features (see associated merge request !153 / #143).

## [3.0.0]
### Added
- All-new UI.
- PowerPoint export.
- Merge Excel and PDF in order.
- Worksheet renaming.
- Images in email.
- Attributes with titles.
- Internationalization (i18n).

---
