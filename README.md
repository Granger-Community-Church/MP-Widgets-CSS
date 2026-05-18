# Widgets CSS
Contains custom CSS for MP Widgets on Webflow Site
Can add to Webflow using GitHub CDN like:

```<link href="https://cdn.jsdelivr.net/gh/Granger-Community-Church/MP-Widgets-CSS@main/mp-widgets.css" rel="stylesheet">```

## Per-widget overrides

Widget-specific stylesheets `@import` `mp-widgets.css` and layer on overrides
scoped to a single widget. Load one of these in place of `mp-widgets.css` on
the relevant page:

- `mp-oppfinder.css` — Opportunity Finder / Details
- `mp-groupfinder.css` — Group Finder / Group Details
- `mp-getform.css` — Standalone Get-Form

Example:

```<link href="https://cdn.jsdelivr.net/gh/Granger-Community-Church/MP-Widgets-CSS@main/mp-groupfinder.css" rel="stylesheet">```

> **Note:** Group-specific rules currently in `mp-widgets.css` (e.g. the
> `.mppw-icon-group` default image and `.mpp-innerpage` heading sizes) are
> candidates to migrate into `mp-groupfinder.css` in a future pass so the
> base file becomes leaner.
