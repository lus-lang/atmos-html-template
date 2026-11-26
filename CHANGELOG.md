# Changelog

## 1.0.0

**Release date:** TBD

Version 1.0.0 is the first release of `html_template`, which renders HTML from templates with the syntax of Handlebars.

- Added `html_template.compile`, `html_template.env`, `html_template.helper`, `html_template.register_partial`, `html_template.escape`, `html_template.safe`, and `html_template.iserror`.
  - `html_template.compile`: Compiles a template with the default environment.
  - `html_template.env`: Returns a new environment of helpers and partials that may load templates from a directory.
  - `html_template.helper`: Registers a helper in the default environment.
  - `html_template.register_partial`: Registers a partial in the default environment.
  - `html_template.escape`: Escapes a value for HTML.
  - `html_template.safe`: Marks a string as HTML that `{{ }}` inserts without escaping.
  - `html_template.iserror`: Tests whether a value is an error object that compiling or rendering a template raised.
- Added the environment methods `compile`, `helper`, `register_partial`, and `render`.
  - `env:compile`: Compiles a template with the helpers and partials of the environment.
  - `env:helper`: Registers a helper.
  - `env:register_partial`: Registers a partial.
  - `env:render`: Loads, compiles, caches, and renders a template file from the root directory.
