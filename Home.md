# Digital Garden

Welcome to the digital-garden wiki. The contents of this wiki are classified as [PUBLIC](PUBLIC).
This is hosted in one of two ways:

- As a [GitHub Wiki](https://github.com/jordanofoster/digital-garden/wiki)
- As a statically generated [website](https://digital-garden.jordanofoster.repl.co) on `repl.it`.
[[Home]]

[Source here](https://replit.com/@jordanofoster/digital-garden), but the setup is basically this:

1. Run a bash script on boot.
2. Clone this wiki into `/tmp` on the repl.
3. Copy specific directories (as of current, `/assets`) into the repl.
4. For each file in the repository:

    1. Extract its 'name' and extension.
        - If these are the same, it's a directory - skip it.
    2. If the title is "Home" (this page!) the resultant filename is `index.html`.
        - Otherwise, it's `'name'.html`.
    3. Run pandoc with the following arguments:
        - `--standalone`
        - `--to html5`
        - `--data-dir ./_pandoc`
        - `--css ./styles/wiki.css`

## Further work...? (repl.it)

- It'd be nice to support adding format-agnostic metadata through `--metadata-file`.
    - However, it seems that pandoc only supports 'metadata' (read: its pre-defined *format-specific* variables) through this option, rather than the 'variables' (anything I want) I was hoping for.
    - This is in contrast to how YAML frontmatter in markdown files seems to be parsed... shame 😞 