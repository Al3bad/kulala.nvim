# Setup Options

The following options can be set in the setup function:

### Full example

Here is a full example of setting up the Kulala plugin with the `setup` function:

```lua title="setup.lua"
require("kulala").setup({
  -- default_view, body or headers
  default_view = "body",
  -- dev, test, prod, can be anything
  -- see: https://learn.microsoft.com/en-us/aspnet/core/test/http-files?view=aspnetcore-8.0#environment-files
  default_env = "dev",
  -- enable/disable debug mode
  debug = false,
  -- default formatters for different content types
  formatters = {
    json = { "jq", "." },
    xml = { "xmllint", "--format", "-" },
    html = { "xmllint", "--format", "--html", "-" },
  },
  -- default icons
  icons = {
    inlay = {
      loading = "⏳",
      done = "✅",
      error = "❌",
    },
    lualine = "🐼",
  },
  -- additional cURL options
  -- see: https://curl.se/docs/manpage.html
  additional_curl_options = {},
})
```

### default_view

Default view.

Possible values:

- `body`
- `headers`

Default: `body`

Example:

```lua
require("kulala").setup({
  default_view = "body",
})
```

### default_env

Default environment.

See: https://learn.microsoft.com/en-us/aspnet/core/test/http-files?view=aspnetcore-8.0#environment-files

Possible values:

- `[any string]`

Default: `dev`

Example:

```lua
require("kulala").setup({
  default_env = "body",
})
```

### debug

Enable debug mode.

Possible values:

- `true`
- `false`

Default: `false`

Example:

```lua
require("kulala").setup({
  debug = false,
})
```

### formatters

Default formatters for different content types.

Possible values:

- `json = [command-table]`
- `xml = [command-table]`
- `html = [command-table]`

Default:

```lua
formatters = {
  json = { "jq", "." },
  xml = { "xmllint", "--format", "-" },
  html = { "xmllint", "--format", "--html", "-" },
}
```

Example:

```lua
require("kulala").setup({
  formatters = {
    json = { "jq", "." },
    xml = { "xmllint", "--format", "-" },
    html = { "xmllint", "--format", "--html", "-" },
  },
})
```

### icons

Default icons.

Possible values:

- `inlay = { loading = [string], done = [string], error = [string] }`
- `lualine = [string]`

Default:

```lua
icons = {
  inlay = {
    loading = "⏳",
    done = "✅"
    error = "❌",
  },
  lualine = "🐼",
}
```

Example:

```lua
require("kulala").setup({
  icons = {
    inlay = {
      loading = "⏳",
      done = "✅"
      error = "❌",
    },
    lualine = "🐼",
  },
})
```

### Additional cURL options

Additional cURL options.

Possible values:

- `[table of strings]`

Default: `{}`

Example:

```lua
require("kulala").setup({
  additional_curl_options = { "--insecure", "-A", "Mozilla/5.0" },
})
```

