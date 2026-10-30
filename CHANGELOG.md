# Changelog

All notable changes to this module are documented here.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.1.0] - 2026-10-14

### Added
- Configurable form **title**, **description** and **privacy policy link** next to the GDPR consent
  (Stores > Configuration > Customers > Newsletter > Newsletter Pro Form).
- HTML5 `required` attributes and `autocomplete` hints on the form fields.

### Removed
- Last project-specific leftovers: a hardcoded form description (and its translation) and a module
  sequence on a third-party popup module.

### Changed
- Submit button label "Subscribe" instead of "Send Request"; email field label "Email".
- README rewritten (no reference to the removed data patch, compatibility notes).
- composer.json: Italian description, no hardcoded `version`.

## [1.0.1] - 2026-06-19

### Removed
- Project-specific newsletter popup data patch
  (`Setup/Patch/Data/SetNewsletterPopupText.php`) with hardcoded success texts
  for third-party popup modules. It was not part of the generic module.

## [1.0.0] - 2026-06-19

First packaged release.

### Features
- Extended newsletter subscribe form with first name, last name and a marketing
  opt-in checkbox, persisted on `newsletter_subscriber`.
- Explicit GDPR consent checkbox (flag + accepted text stored), automatically
  disabled when `Amasty_Gdpr` is active to avoid a duplicate consent.
- Admin toggle to disable the newsletter notification emails
  (`newsletter/subscription/notify_by_email`).
- Theme-agnostic CSS layout and Italian (`it_IT`) translation.

### Fixed
- **Critical:** the notification toggle had no default value, so
  `ScopeConfigInterface::isSetFlag()` returned `false` out of the box. This set
  the subscriber to import mode unconditionally and **silently suppressed all**
  confirmation/unsubscription emails regardless of the admin setting. Added
  `etc/config.xml` with `newsletter/subscription/notify_by_email = 1` so the
  module ships with Magento's stock behaviour (emails enabled) and only
  suppresses them when an admin opts out.
- The plugin handled `confirmation_success` and `unsubscription` emails but not
  the double opt-in `confirmation_request` email. Added
  `beforeSendConfirmationRequestEmail` so the single toggle consistently gates
  all three newsletter emails.