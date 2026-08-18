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

### Opportunity Details — per-opportunity message field

`mp-oppfinder.css` carries a hand-maintained allowlist controlling the optional
"Tell us a little about yourself:" textarea (`#formMessage`) on the opportunity
signup form. It is **shown by default** — many opportunities rely on it as the only
free-text field — and hidden only for the opportunity IDs listed in the rule.

To hide it on another opportunity, copy a selector line and swap in that
opportunity's ID (the `?id=` value in its `/volunteer-details` URL):

```css
#responseForm:has(#opportunityId[value="2119"]) #formMessage,
#responseForm:has(#opportunityId[value="1234"]) #formMessage
  { display:none !important; }
```

The field is optional in MinistryPlatform, so hiding it never blocks form
validation — responses simply save with an empty Message.

> **Deploying:** the Webflow embed loads this file via its `customcss` attribute
> pointing at jsDelivr `@main`, which is cached. After pushing, either purge the
> file at `purge.jsdelivr.net` or bump a `?v=` query string on the `customcss`
> attribute in Webflow before the change goes live.
