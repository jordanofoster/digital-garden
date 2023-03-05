**NOTE: this does *not* consider support for using other language's markup (i.e., HTML, or LaTeX math expressions) as supported; such cases are still marked as ❌**

# Key:

| Emoji | Meaning |
| :---: | :-----: |
| ❌ | Not supported |
| ⬆️ | Same syntax as previous entry |

## Text Formatting 

| | asciidoc | markdown | mediawiki<sub>[1]</sub> | org-mode | textile | restructuredtext |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| bold | `*bold*` | `**bold**` | `'''bold'''` | `*bold*` | `**bold**` | `**bold**` |
| italic | `_italic_` | `*italic*` | `''italic''` | `/italic/` | `__italic__` | `*italic*` | 
| bold+italic | `*_bold+italic_*` | `***bold+italic***` | `'''''bold+italic'''''` | ❌ | `*_bold+italic_*` or `bold[*+*]italic` | ❌ |
| underline |  `[.underline]#underline` | ❌ | ❌ | `_underlined_` | ❌ | ❌ |
| highlight | `##highlight##` or `#highlight#` | `==highlight==` | ❌ | ❌ | ❌ | ❌ |
| strikethrough | `[.line-through]#strikethrough` | `~strikethrough~` | ❌ | `+strikethrough+` | `-strikethrough-` | ❌ |
| monospace | \`monospace\` | \`monospace\` | ❌ | `=monospace=` | `pre. monospace` | \`\`monospace\`\` |
| superscript | `^super^` | `^super^` | ❌ | `^{sup}` or `^sup^` | ❌ | ❌ |
| subscript | `~sub~` | `~sub~` | ❌ | `_{sub}` or `_sub_` | ❌ | ❌ |

## Linking/embedding

| | asciidoc | markdown | mediawiki | org-mode | textile | restructuredtext |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| hyperlinks | `link[text]` | `[text](link)` | `[[link\|text]]` or `[[link]]` | `[[link][text]]` or `[[link]]`| `"text":link` |  \`text \<link\>\`_ |
| internal links | ⬆️ | ⬆️  | `[link]`, `[link text]` or `link` | ⬆️ | ⬆️ | `text_`<sub>[2]</sub> |
| embedded media | `audio/video/image::file[params]`<sub>[3]</sub> | `![alt text](file)`<sub>[4]</sub> | `[[File:filename.extension\|options\|caption]]` | ❌<sub>[5]</sub> | `!/image.ext!`<sub>[6]</sub> | `.. type:: path`<sub>[7]</sub> |

###### Footnotes: 

1. No consistent spec appears to be defined for MediaWiki syntax. Many flavors of wikitext will also follow their own format.
2. Place your target at the bottom in the following syntax:
```rst
.. _text: link  
```
3. See the [image](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#images), [audio](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#audio) and [video](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#videos) syntax.
4. The official markdown syntax supports [images](https://www.markdownguide.org/basic-syntax/#images); any other embed support is implementation specific.
5. Since emacs is text-based, this is not supported by default. Some plugins allow inline media embeds, however.
6. Only [images](https://textile-lang.com/doc/images) are supported by textile.
7. Embedded media is supported through reStructuredText's [directive](https://docutils.sourceforge.io/docs/ref/rst/directives.html) syntax.