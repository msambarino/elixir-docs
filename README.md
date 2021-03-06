# elixir-docs package
Finds source code docs for a namespaces and outputs the parsed markdown docs in a tool panel.

1. Hightlight you namespace you want the docs for
2. Run command (or add keymap to) 'elixir-docs:finddoc'

If you have a mix file in your project root folder the plugin loads up iex -S mix e.g. includes all your project dependencies when searching for docs. Otherwise falls back to just showing docs for Elixirs base libs.

![Screenshot1](https://gyazo.com/fd996b70a340522b07f3c267a2ba4c8d.png)

Keymaps
```javascript
'atom-workspace':
  'ctrl-alt-o': 'elixir-docs:toggle'
  'ctrl-i': 'elixir-docs:finddoc'
```

#### Common Errors

* `Failed to spawn command iex. Make sure iex is installed and in your PATH`: If you're on OS X, this happens when starting atom from Finder. Finder-started applications have no access to PATH variable. To go around that make sure to set both `Elixir Home` and `Erlang Home` in package configuration to the absolute path where elixir and erlang are installed repstectively, or start atom from the command line instead.


#### Known issues
* Does not resolve binding. E.g. you cant select a bound
  value and ask for docs. It needs the entire namespace.
* Recompilation
    - The project needs to recompile to show latest docs
      this is not taken care of by this plugin.
* on todo list: Smarter namespace selection from "carret" etc.
* on todo list: Make sure it runs on Mac -x (totally not tested)
  - Probably needs absolute path resolving to elixir iex commands
