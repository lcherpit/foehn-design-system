---
title: "Upgrade to Bootstrap 4 Beta"
---

Foehn v0.29.0 used the Bootstrap alpha 6 version. Since v0.30.0, Foehn use the beta version of Bootstrap.

Here are all the changes you need to do to make the jump.

## Update scripts

Update the scripts to inlcude before the `</body>` tag.

```html
{% view '@scripts-footer' %} {% view '@webfont-loading' %}
```

## Update spacing utilities

Two size are included in spacing utilities.

| old values            | new values            |
| --------------------- | --------------------- |
|                       | `{property}{sides}-1` |
|                       | `{property}{sides}-2` |
| `{property}{sides}-1` | `{property}{sides}-3` |
| `{property}{sides}-2` | `{property}{sides}-4` |
| `{property}{sides}-3` | `{property}{sides}-5` |

### Regex to use (in this order)

#### size 3 becomes 5

- Find: `([pm])([xytrbl])-3`
- Replace: `$1$2-5`

#### size 2 becomes 4

- Find: `([pm])([xytrbl])-2`
- Replace: `$1$2-5`

#### size 1 becomes 3

- Find: `([pm])([xytrbl])-1`
- Replace: `$1$2-5`

## Update button class

Replace `.btn-primary` class with `.btn-dark`.

## Update color helpers

- Replace `.text-muted` class with `.text-secondary`
- Replace `.bg-inverse` class with `.bg-dark`
- Replace `.bg-faded` class with `.bg-light`

## Update grid offsetting columns

Update the grid to `drop` `push`, `pull`, and `offset` in favor of new `.order-` modifiers and margin utilities. Take a look at [the documentation](https://getbootstrap.com/docs/4.0/layout/grid/#offsetting-columns).

In foehn these change take place in two components.

### [Header](http://dsi-vd.github.io/foehn/components/detail/header)

Use `.ml-auto` to push the search-form on the right.

```html
{% view '@header' %}
```

### [Header homepage](http://dsi-vd.github.io/foehn/components/detail/header--homepage)

Use `.ml-auto` to push the search-form on the right.

```html
{% view '@header--homepage' %}
```

## Update display property helpers

Remove `.hidden-*` classes in favor of the newer `.d-*` [display utilities](https://getbootstrap.com/docs/4.0/utilities/display/).

- Find: `hidden-(xxs|xs|sm|md|lg|xl)-up`
- Replace: `d-$1-none`

For the next class, you have to set the correct display property. Look at [the doc](https://getbootstrap.com/docs/4.0/utilities/display/) for more information.

- Find: `hidden-xxs-down`
- Replace `d-none d-xs-{display property}`

- Find: `hidden-xs-down`
- Replace `d-none d-sm-{display property}`

- Find: `hidden-sm-down`
- Replace `d-none d-md-{display property}`

- Find: `hidden-md-down`
- Replace `d-none d-lg-{display property}`

## Update [nav-horizontal](http://dsi-vd.github.io/foehn/components/detail/nav-horizontal)

[Navbar](https://getbootstrap.com/docs/4.0/components/navbar/) have been
updated.

- `.navbar-toggleable-*` class is replaced bay `.navbar-expand`.
- The brand come before the toggle button.

```html
{% view '@nav-horizontal' %}
```

## Update [nav-primary](http://dsi-vd.github.io/foehn/components/detail/nav-primary)

There's some comflicts with display (`.d-*`) and `.collapse` classes in `nav-primary` component.
`.d-none` and `d-md-block` have to be moved on another `<div>`.

```html
{% view '@nav-primary' %}
```
