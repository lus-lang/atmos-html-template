# AGENTS.md

`lus-lang/atmos-html-template` is the repository of the `html_template` package of the atmosphere registry. Programs load the package with `require("https://atmosp.here/2.0/html_template.lus")`.

## Scope

`html_template` renders HTML from templates with the syntax of Handlebars. `{{name}}` inserts an escaped value and `{{{name}}}` an unescaped one. The block helpers `if`, `unless`, `each`, and `with` choose and repeat parts of a template. An environment holds helpers and partials and may load templates from files. The public API is every function that `html_template.lus` returns in its module table. A change to that API needs a new entry in `CHANGELOG.md` and a version change in the header.

## Layout

- `html_template.lus` is the whole package. Its header doc comment contains the package metadata and the declared permissions.
- `tests/*_test.lus` are the tests. They load `html_template.lus` from the parent of `TEST_DIR`, the directory that holds the test file.

## Commands

Run these commands from the root of the repository.

```sh
lus test tests          # run the tests
lus check html_template.lus     # lint, including the package codes
lus doc html_template.lus       # print the reference
```

## Rules

- Every public function has a doc comment that states each result and each error, following `spec/design/style.md` of the Lus repository.
- The package never calls `pledge`. A new permission is declared in the header and in the README.
- Prose follows the `lus-writing` skill, which `lus agents init` installs and https://lus.dev/agents/skills/lus-writing/SKILL.md serves. In particular, prose has no dashes or semicolons and never names the Roblox Lua dialect.
- Every bug fix comes with a test that fails without it.
