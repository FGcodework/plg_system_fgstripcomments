# Changelog — plg_system_fgstripcomments

## 2.0.7 – 2026-09-25
- Added an **Info & Support** tab to the plugin options (the first tab),
  with the plugin's settings moved to their own **Settings** tab —
  matching the layout used across the FG series of extensions.
- The tab shows a short note that the plugin is free and open source,
  the official Ko-fi badge (optional tip) and a **More FG Extensions**
  button styled like the white Joomla toolbar buttons, including hover
  state and dark-mode support.
- Links use single-quoted HTML attributes, so they render correctly
  from the `.ini` language string without any escaping.
- The Atum "opens in new window" icon is suppressed on the Ko-fi badge
  only (rule scoped to the `fg-kofi` class); all other admin links keep it.

## 2.0.1 – 2026-08-02
- Plugin display name changed to `System - FG Strip Comments` to follow
  the JED `{Type} - {Extension Name}` naming convention.
- Update feed (`updates.xml`) now targets both Joomla 5.x and 6.x
  (`targetplatform` regex `[56]\.[0-9]+`), matching the stated
  compatibility.

## 2.0.0 – 2026-08-02
- **Breaking:** renamed to "FG Strip Comments", part of the FG series of
  Joomla extensions. The technical element changed from `stripcomments`
  to `fgstripcomments` (folder, PHP namespace, language files, update
  feed) to avoid collisions with other developers' plugins.
- Because the element changed, this is **not** an in-place update from
  1.x — Joomla installs it as a separate plugin. Uninstall 1.x first,
  then install 2.x.
- GitHub repository renamed to `plg_system_fgstripcomments`.

## 1.x – 2026-06 to 2026-08 (legacy element `stripcomments`)
Summary of the original plugin, published as "System - Strip Comments":
- Strips custom marker tags `{-- ... --}` from the rendered front-end
  output via `onAfterRender` (the behaviour of the old BIGSHOT Strip
  Comments plugin); opening and closing delimiters are configurable.
- **Scope** option: *Titles only* (headings `h1`–`h6`, `<title>` and link
  text such as menu items and breadcrumbs) or *Whole page*.
- In *Whole page* scope, `<script>` and `<style>` blocks are never
  touched (PCRE `(*SKIP)(*FAIL)`, no performance cost).
- Optional run in the administrator back-end (off by default).
- Joomla Update System support (`<updateservers>` + `updates.xml`).
- Slovak (sk-SK) localization alongside English.
- GPL license headers in all PHP files, as required by the JED Checker.
