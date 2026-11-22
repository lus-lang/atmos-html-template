# html_template

`html_template` renders HTML from templates with the syntax of Handlebars. `{{name}}` inserts an escaped value and `{{{name}}}` an unescaped one. The block helpers `if`, `unless`, `each`, and `with` choose and repeat parts of a template. An environment holds helpers and partials and may load templates from files.

The following example renders the heading and the dishes of a menu, escaping the ampersand in the title.

```lus nocheck
local template = require("https://atmosp.here/2.0/html_template.lus")

local page = template.compile("<h1>{{ title }}</h1><ul>{{#each items}}<li>{{ name }}</li>{{/each}}</ul>")
print(page({ title = "Fish & Chips", items = { { name = "Cod" }, { name = "Haddock" } } }))
--> <h1>Fish &amp; Chips</h1><ul><li>Cod</li><li>Haddock</li></ul>
```

The package requires Lus 2.0 and declares the permission `fs:read`, which only an environment that loads template files from its root directory uses. It never calls `pledge`, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `html_template.lus`, which `lus doc html_template.lus` prints.
