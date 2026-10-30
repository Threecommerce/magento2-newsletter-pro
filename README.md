# Threecommerce_Newsletter: newsletter form with GDPR consent for Magento 2 / Mage-OS

Upgrades the stock Magento newsletter subscription form into a **GDPR-ready, marketing-oriented form**: first name, last name, marketing opt-in and explicit consent, plus a switch to turn off the notification emails Magento sends for subscriptions.

**Compatibility:** Magento Open Source / Adobe Commerce 2.4.4 – 2.4.9 · Mage-OS 1.x / 3.x · PHP 8.1 – 8.4 · Themes: Luma-based
**License:** commercial · coming soon

## Features

- **Extra subscriber fields**: first name, last name and a marketing opt-in checkbox, saved on the core `newsletter_subscriber` table.
- **Explicit GDPR consent**: required checkbox; the consent flag and the exact text accepted are stored with the subscriber. Optional link to your privacy policy page. If `Amasty_Gdpr` is enabled the module steps aside and uses Amasty's consent instead of a duplicate.
- **Configurable title and description** of the form, per store view.
- **Disable notification emails**: one toggle suppresses the confirmation request, confirmation success and unsubscription emails while the subscription still works.
- **Server-side validation** of first name, last name, opt-in and consent on submit, not only in the browser.
- Small CSS scoped to the form id. English base strings with Italian translation.

## Requirements

- Magento Open Source / Adobe Commerce 2.4.4+ or Mage-OS
- PHP 8.1 – 8.4
- `Magento_Newsletter`
- The form template is built for Luma-based themes (it uses Magento's standard form validation); Hyvä and Breeze use their own newsletter templates.

## Availability

This module is not yet available for purchase. See the [product page](https://www.threecommerce.it/newsletter-pro-consenso-gdpr-magento-2?utm_source=github&utm_medium=readme&utm_campaign=magento2-newsletter-pro) for its status, or [contact us](https://www.threecommerce.it/contatti?utm_source=github&utm_medium=readme&utm_campaign=magento2-newsletter-pro) to be notified when it is released or to ask for information.

## Configuration

Admin → **Stores → Configuration → Customers → Newsletter**: *Notify newsletter by email* (No = no confirmation or unsubscription emails), form title, form description and privacy policy URL, all configurable per store view.

## Documentation and support

- Product page: [threecommerce.it/newsletter-pro-consenso-gdpr-magento-2](https://www.threecommerce.it/newsletter-pro-consenso-gdpr-magento-2?utm_source=github&utm_medium=readme&utm_campaign=magento2-newsletter-pro)
- [Changelog](CHANGELOG.md) (in Italian)
- Support and custom development: [threecommerce.it/contatti](https://www.threecommerce.it/contatti?utm_source=github&utm_medium=readme&utm_campaign=magento2-newsletter-pro)

---

*This repository is the public showcase of the module. The source code is kept in a private repository.*
