# Github Wiki and `pandoc` Compatible Markup/File Formats

The *GitHub/GitLab* and *[Gollum](https://github.com/gollum/gollum)* wikis use the same underlying [ruby library](https://github.com/github/markup#markups) - meaning they all support the same set of markups. `pandoc` supports a [superset](https://github.com/jgm/pandoc/blob/main/src/Text/Pandoc/App/FormatHeuristics.hs#L38) of this, including various markdown dialects - but for the purposes of interoperability, it is best to stick to the following as shown in the below table:

| Markup Language | File Extension | GitHub/GitLab/Gollum? | `pandoc`? |
| :---: | :---: | :---: | :---: |
| [Markdown](http://daringfireball.net/projects/markdown/) | `.markdown`, `.mdown`, `.mkdn`, `.md` + others | Yes, [`gfm`](https://github.github.com/gfm/) | Yes (+others, all dialects) |
|  [Textile](https://www.promptworks.com/textile) | `.textile` | Yes | Yes |
| [RDoc](https://ruby.github.io/rdoc/) | `.rdoc` | Yes | No |
| [Org Mode](http://orgmode.org/) | `.org` | [Partially](https://github.com/wallyqs/org-ruby#current-status) | [Partially](https://pandoc.org/org.html) |
| [Creole](http://wikicreole.org/) | `.creole` | Yes | One-Way → [Creole](https://pandoc.org/) |
| [MediaWiki](http://www.mediawiki.org/wiki/Help:Formatting) | `.mediawiki`, `.wiki` | Yes | Yes (only `.wiki` automatically)|
| [reStructuredText](http://docutils.sourceforge.net/rst.html) | `.rst` | Yes | Yes |
| [AsciiDoc](https://asciidoc.org) | `.asciidoc`, `.adoc`, `.asc` | Yes | Yes (only `.asciidoc`/`.adoc` automatically) |
| [Pod](http://search.cpan.org/dist/perl/pod/perlpod.pod) | `.pod` | Yes | No |

## Summarization of Findings

- For *Markdown,* stick to [CommonMark](https://commonmark.org/) or [GitHub-Flavored Markdown](https://github.github.com/gfm/).
    - This means no pandoc citations.

- Stick to the following in *Org-Mode*:
    - Tables
    - Blocks:
        - `#+BEGIN/END_SRC`
        - `#+BEGIN/END_QUOTE`
        - `#+BEGIN/END_EXPORT html`
    - Links
    - Footnotes

- Ensure that your file extensions are as follows:
    - *MediaWiki* → `.wiki`
    - *AsciiDoc* → `.asciidoc` or `.adoc`

- Do **NOT** use the following formats:
    - *RDoc*
    - *Pod*
    - *Creole*

The current implementation of *make.sh* (see [Home](Home.md)) involves `pandoc` hueristically determining the input file format; this means that special options *cannot be enabled.*
## Metadata

Generally, metadata is not supported by GitHub/GitLab wiki. inline *YAML* metadata on markdown files *is* supported by Gollum, however.

Pandoc is more flexible with this, and supports inline metadata on most markup languages that include support for it (or attributes) within its spec. However, such inline markup is likely to be misrendered by GitHub/GitLab.

Therefore, best practice is to provide a JSON/YAML file in the format of `original_filename.ext.json/yaml` inside the *metadata* folder, so that `pandoc` can add it accordingly with the `--metadata-file` option, so long as a template that references the variable is passed to `--template`.