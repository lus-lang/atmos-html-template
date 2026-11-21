# html_template

Renders HTML from templates with the syntax of Handlebars.

```lus nocheck
local template = require("https://atmosp.here/2.0/html_template.lus")

local page = template.compile("<h1>{{ title }}</h1>{{#each items}}<li>{{ name }}</li>{{/each}}")
print(page({ title = "Lus & co", items = { { name = "a" }, { name = "b" } } }))
--> <h1>Lus &amp; co</h1><li>a</li><li>b</li>
```

The package requires Lus 2.0. It declares the permission fs:read, which only environments that load template files use. It calls no `pledge` of its own, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `html_template.lus`. Run `lus doc html_template.lus` to print it.
