# Login-Logout (HackIndex Patched)

> [!IMPORTANT]
> This is an unofficial fork of [Login-Logout](https://wordpress.org/plugins/login-logout/) by [webvitaly](https://github.com/webvitalii/login-logout). HackIndex is not affiliated with or endorsed by the original author.

The original plugin is no longer maintained and its latest release (3.8) has a [known vulnerability](https://www.wordfence.com/threat-intel/vulnerabilities/id/00bb89b7-e8f3-4ffc-8086-34f70a66e641). HackIndex maintains this fork for security fixes only:

- We fix security issues and keep the plugin working on current WordPress and PHP versions.
- We do not add features or change how the plugin works.
- It is a drop-in replacement: same plugin folder and widget settings, so your Login-Logout widgets keep working.

Need help with this fork? [Open an issue](https://github.com/HackIndex-io/login-logout/issues) here, please don't contact the original author about it.

## What it does

Adds a Login-Logout widget, a replacement for the default Meta widget. It shows a login or logout link, and optionally a welcome text, a register link, a site admin link and extra items, as a list or inline.

## Security fixes

### 3.8.1

- Administrator+ stored Cross-Site Scripting ([CVE-2025-53467](https://www.cve.org/CVERecord?id=CVE-2025-53467), [Wordfence advisory](https://www.wordfence.com/threat-intel/vulnerabilities/id/00bb89b7-e8f3-4ffc-8086-34f70a66e641)): the widget texts and extra items were saved and printed without any filtering, so an administrator without the `unfiltered_html` capability (multisite site admins, or when `DISALLOW_UNFILTERED_HTML` is set) could add scripts that run for every visitor. These users can now only save the HTML allowed in posts, the same rule as the core Text widget. Users with `unfiltered_html` can still save any HTML. Widgets saved before the update are not changed, so on a multisite, check the widget settings and save them again.
- The display name in the welcome text is escaped
- Tested with WordPress 7.1 and PHP 8.0 to 8.5

## Install

1. Download `login-logout.zip` from the [latest release](https://github.com/HackIndex-io/login-logout/releases/latest).
2. Upload the zip in **Plugins > Add New > Upload Plugin** and choose **Replace current with uploaded**. The plugin stays active and your widgets stay in place. (Deactivating the original first can move its widgets to Inactive widgets when you open the Widgets screen in between.)

WordPress does not update this fork automatically. Watch this repo's releases to get new security fixes.

## License

GPLv3, like the original. See [LICENSE](LICENSE). Provided without any warranty.

All credit for the plugin goes to [webvitaly](https://github.com/webvitalii/login-logout). The full upstream history is kept in this repository.
