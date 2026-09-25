<p align="center">
  <img src="assets/logo.png" width="120" alt="plg_system_fgstripcomments logo">
</p>

<h1 align="center">FG Strip Comments plugin for Joomla</h1>

<p align="center">
  <img src="https://img.shields.io/github/v/release/FGcodework/plg_system_fgstripcomments?color=FF6B4A&label=release" alt="Latest release">
  <img src="https://img.shields.io/badge/Joomla-6.x-blue?logo=joomla&logoColor=white" alt="Joomla 4 | 5 | 6">
  <img src="https://img.shields.io/badge/PHP-8.1%2B-purple.svg?logo=php&logoColor=white" alt="PHP">
  <img src="https://img.shields.io/badge/license-GPLv2%2B-green" alt="License: GPL-2.0">
  <img src="https://img.shields.io/github/downloads/FGcodework/plg_system_fgstripcomments/total?color=brown" alt="Downloads">
  <a href="https://ko-fi.com/fgcodework"><img src="https://img.shields.io/badge/support-Ko--fi-FF6061.svg?logo=ko-fi&logoColor=white" alt="Support on Ko-fi"></a>
</p>

[![JED](https://img.shields.io/badge/Joomla!%20Extensions%20Directory%E2%84%A2-StripComments-blue)](https://extensions.joomla.org/extension/extension-specific/extensions-specific-non-sorted/strip-comments/)


A Joomla 6 system plugin that removes internal marker tags
(e.g. `{-- My City --}`) from the rendered front-end output — from module
titles, article titles, menu items, and so on — while keeping them fully
visible in the administrator back-end.

Part of the **FG** series of Joomla extensions. A modern replacement for
the long-unavailable **BIGSHOT Strip Comments** plugin (for Joomla
1.5 – 3.x), rewritten for Joomla 6's plugin API and namespacing.

## Example

In the administrator you name a module like this:

```
Opening Hours {-- My City --}
```

On the front-end, only this is shown:

```
Opening Hours
```

The `{-- My City --}` note is for your own back-end reference only (e.g.
to tell apart several similarly named modules/articles) and is never
shown on the public site.

## Installation

1. Download the latest release (`.zip`) from the [Releases](../../releases) tab.
2. In the Joomla administrator go to **System → Install → Extensions**
   and upload the downloaded `.zip`.
3. **System → Manage → Plugins** → find "System - FG Strip Comments" and
   publish it.

## Plugin settings

| Parameter | Description | Default |
|---|---|---|
| **Scope** | `Titles only` – strips markers only inside `h1`–`h6`, `<title>`, and link text (`<a>`, menu items). `Whole page` – strips markers everywhere in the output, except inside `<script>`/`<style>` blocks, which are never touched. | `Titles only` |
| **Opening delimiter** | Opening marker string. | `{--` |
| **Closing delimiter** | Closing marker string. | `--}` |
| **Also run in administrator** | If enabled, markers are also stripped in the back-end. | off |

## Requirements

- Joomla 6 (5+)
- PHP 8.1+

## License

GNU General Public License v2.0 or later — see [LICENSE](LICENSE).

## Changelog

See [CHANGELOG.md](CHANGELOG.md).
