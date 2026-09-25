# Changelog — plg_system_fgstripcomments

## 2.0.6 – 2026-09-25
- "More FG Extensions" button restyled to match the white Joomla toolbar
  buttons (e.g. "Toggle inline help"). Those use `btn btn-info`, but the
  white look actually comes from Atum's `.subhead .btn` override via the
  `--atum-btn-*` CSS variables, so outside the toolbar `btn-info` would
  render coloured. The button now sets Bootstrap's `--btn-*` variables to
  the same `--atum-btn-*` values — identical look, working hover state,
  and automatic dark-mode support.

## 2.0.5 – 2026-09-25
- Removed the blue `alert-info` background from the Info & Support tab
  — plain text now, no colour box.
- "More FG Extensions" restyled from a plain text link into a proper
  `btn btn-secondary` button, matching the Joomla admin template's own
  button style and giving it visual weight comparable to the Ko-fi badge.

## 2.0.4 – 2026-09-25
- Restyled the Info & Support tab into two rows (info text, then a
  spaced-out button row) instead of one cramped line. This gives the
  Joomla admin template's automatic "opens in new tab" icons (added to
  every `target="_blank"` link) enough breathing room instead of
  crowding the Ko-fi badge and the text.

## 2.0.3 – 2026-09-25
- Fixed broken Ko-fi/links in the Info & Support tab: attribute values
  used HTML-entity-escaped double quotes (`&quot;`) which did not decode
  correctly in the rendered note field, producing a broken relative URL.
  Rewritten using single-quoted HTML attributes throughout, which need
  no escaping inside the `.ini` value.
- Replaced the plain "Support on Ko-fi" text link with the official
  Ko-fi badge image, matching the style already used in README.md.
- Shortened the intro text to "This plugin is free and open source...".
- Renamed "More FG plugins" to "More FG Extensions".
- Wrapped the note in a Bootstrap `alert alert-info` box so it picks up
  the current Joomla admin template's colours automatically.

## 2.0.2 – 2026-09-25
- Added an "Info & Support" tab to the plugin options (matching the FG
  series pattern used in FG Offline IP Whitelist): a short note about
  the plugin being free/open-source with an optional Ko-fi tip link,
  now separated from the actual settings tab.
- Settings moved to their own labelled "Settings" tab.

## 2.0.1 – 2026-08-02
- Fixed the plugin display name to `System - FG Strip Comments` — the
  JED naming convention requires the `{Type} - {Extension Name}` format,
  which was missed in the 2.0.0 rename.

## 2.0.0 – 2026-08-02
- **Breaking:** renamed the plugin to "FG Strip Comments", the first of
  the FG series of Joomla extensions. The technical element changed from
  `stripcomments` to `fgstripcomments` (folder, PHP namespace, language
  file names, update feed) to avoid any future collision with another
  developer's plugin using the same element name.
- Because the element name changed, this is **not** a smooth in-place
  update from 1.x — Joomla will install it as a new, separate plugin.
  If a 1.x version is already installed somewhere, uninstall it first,
  then install 2.0.0.
- GitHub repository renamed accordingly to `plg_system_fgstripcomments`.

## 1.6.1 – 2026-08-02
- Added the required GPL license header comment to all PHP files
  (`services/provider.php`, `src/Extension/StripComments.php`) — required
  by the JED Checker / Joomla Extensions Directory submission rules.

## 1.6.0 – 2026-08-01
- Added Joomla Update System support (`<updateservers>` in the manifest,
  plus a Joomla-format `updates.xml` feed) — required by the Joomla
  Extensions Directory for all listings submitted after 10 Jan 2017.

## 1.5.0 – 2026-07-28
- In "Whole page" scope (`scope=all`), markers are no longer removed
  inside `<script>` and `<style>` blocks — those are now always left
  untouched (implemented via a PCRE `(*SKIP)(*FAIL)` pattern, with no
  performance cost).

## 1.4.0 – 2026-07-28
- Added Slovak localization (sk-SK) for the plugin settings and description.

## 1.3.0
- "Titles only" scope extended to also cover link text (`<a>`) — this
  catches menu items and breadcrumbs, not just headings and `<title>`.

## 1.2.0
- Added a "Scope" parameter (Whole page / Titles only – headings and
  `<title>`).

## 1.1.0
- Behavior change: instead of stripping HTML comments, the plugin now
  strips custom marker tags `{-- ... --}` (matching the original BIGSHOT
  behavior). Delimiters are configurable.

## 1.0.0
- Initial release — strips HTML comments from the rendered output via
  `onAfterRender`.
