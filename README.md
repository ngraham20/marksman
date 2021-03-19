# Zeta Note 

_Delightful note taking in markdown..._

[![Build & Test](https://github.com/artempyanykh/zeta-note/actions/workflows/push.yml/badge.svg?branch=main)](https://github.com/artempyanykh/zeta-note/actions/workflows/push.yml)

**OBLIGATORY DISCLAIMER:**
Zeta Note is a _work-in-progress_. For me it works fine, but there wasn't
much testing and stability in general isn't guaranteed.

---

Zeta Note is a language server that helps you write and manage notes. The
primary focus is to support [Zettelkasten-like][zettel-wiki]<sup>[1](#fn1), [2](#fn2)</sup> note
taking by providing an easy way to **cross-reference notes** (see more about
features below).

But you don't have to go all-in on Zettelkasten method to benefit from Zeta Note:
1. Write your notes that way you like.
2. Cross-reference notes using _reference_ links:
   - `[:another-note]` - a reference to another note.
   - `[:another-note@##Subsection]` - a reference to a subsection of a note.
   - `[:@##Inner subsection]` - a reference to a subsection of the current note.

   Auto-completion provided by Zeta Note makes this process quick and easy.
3. **Go To Definition**, **Hover** preview, **Code Lenses**, and
   **Diagnostics** simplify navigating and maintaining notes.

Existing editor integrations<sup>[3](#fn3)</sup>:
- VSCode via [Zeta Note VSCode][zn-vscode].


## Screenshots

- Hover preview:
  ![Hover](assets/readme/hover.png)
- Completion (note):
  ![Completion for note](assets/readme/completion-note.png)
- Completion (heading):
  ![Completion for heading](assets/readme/completion-heading.png)
- "Show References" Code Lens:
  ![Show references code lens](assets/readme/code-lens-show-refs.png)
- Project-wide diagnostics for broken references:
  ![Diagnostics](assets/readme/diagnostics.png)

## Features and plans

✅ - done; 🗓 - planned.

- ✅ Completion for references.
- ✅ Go to Definition for references.
- ✅ Hover prevew for references.
- ✅ Diagnostics about broken references.
- ✅ Code Lens with "# references" on headings.
- 🗓 Rename refactor.
- 🗓 Support for Jupyter notebooks.
- 🗓 Custom parser for more fine-grained note structure.
- 🗓 Support heading slugs.
- 🗓 Add "check" command for standalone workspace checking.
- 🗓 Add "build" command that rewrites all cross-references into proper
  relative markdown links for further embedding into a static site generator
  such as Jekyll or Hakyll.
- 🗓 Add support for _regular_ links (diagnostics, completion, goto).
- 🗓 Add support for images (diagnostics, completion, goto).

---

<span id="fn1">\[1\]</span>: You may have heard about [Roam Research][roam]. This is a commercial
implementation of the Zettelkasten method and another point of reference for
what Zeta Note is about. However, unlike a proprietary Roam Research, Zeta
Note is free, open-source and integrated into your favourite editor (albeit
for not not as feature rich as Roam Research).

<span id="fn2">\[2\]</span>: There is an excellent VSCode extension called [Markdown
Memo][md-memo]. You definitely need to check it out if you're primarily using
VSCode as it has some features that are missing in Zeta Note and [Zeta Note
VSCode extension][zn-vscode]. However, Markdown Memo is VSCode specific while
Zeta Note is a generic language server, so can be used with any editor that
has LSP support: Emacs, Vim, Neovim, etc.

<span id="fn3">\[3\]</span>: Since Zeta Note is a regular Language Server most of the functionality
works out of the box with any LSP client. The only thing that requires custom
handling is "Code Lenses" due to how these are defined in LSP spec.

[zettel-wiki]: https://en.wikipedia.org/wiki/Zettelkasten
[roam]: https://roamresearch.com
[md-memo]: https://github.com/svsool/vscode-memo
[zn-vscode]: https://github.com/artempyanykh/zeta-note-vscode