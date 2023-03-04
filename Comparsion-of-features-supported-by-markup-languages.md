# Text Formatting 

| | asciidoc | markdown | mediawiki<sub>[1]</sub> | org-mode | textile | restructuredtext |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| bold | `*bold*` | `**bold**` | `'''bold'''` | `*bold*` | `**bold**` | `**bold**` |
| italic | `_italic_` | `*italic*` | `''italic''` | `/italic/` | `__italic__` | `*italic*` | 
| bold+italic | `*_bold+italic_*` | `***bold+italic***` | `'''''bold+italic'''''` | ❌ | `*_bold+italic_*` or `bold[*+*]italic` | ❌ |
| underline |  `[.underline]#underline` | ❌ | ❌ | `_underlined_` | ❌ | ❌ |
| highlight | `##highlight##` or `#highlight#` | `==highlight==` | ❌ | ❌ | ❌ | ❌ |
| strikethrough | `[.line-through]#strikethrough` | `~strikethrough~` | ❌ | `+strikethrough+` | `-strikethrough-` | ❌ |
| superscript | `^super^` | `^super^` | ❌ | `^{sup}` or `^sup^` | ❌ | ❌ |
| subscript | `~sub~` | `~sub~` | ❌ | `_{sub}` or `_sub_` | ❌ | ❌ |

# Other features

| | asciidoc | markdown | mediawiki | org-mode | textile | restructuredtext |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| internal links | `link[text]` | `[text](link)` | `[[link|text]]| ✔️<sub>[2]</sub> |  
###### Footnotes:

1. No consistent spec appears to be defined for MediaWiki syntax.
2. Too complex to list in a table; [look at the documentation.](https://orgmode.org/manual/Hyperlinks.html)