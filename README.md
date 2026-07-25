# notes

The public half of my zettelkasten, built with [Quartz](https://quartz.jzhao.xyz) v5
and served at <https://monishver11.github.io/notes/>.

**`content/` is generated. Do not edit it by hand.**

Notes are written in a private vault at `~/Documents/zettelkasten` and reach this
repo only by running `zk publish` there, which copies over the notes flagged
`publish: true`, strips clipped and machine-captured material, and copies the
images those notes actually reference. Anything edited here directly is
overwritten on the next publish.

See the vault's own README for the workflow.

## Local

```sh
npm install
npm run serve      # localhost:8080
npx quartz build   # -> public/
```

## Config notes

Two things in `quartz.config.yaml` are load-bearing and easy to break:

- **`note-properties` must stay enabled.** It parses the frontmatter block. With
  it disabled, `---` renders as literal markdown, `tags` never populate, and no
  per-tag pages are emitted. `hidePropertiesView: true` hides the rendered block
  without disabling the parsing.
- **The fonts plugin owns typography, not `configuration.theme.typography`.**
  Left at its defaults it emits its own stylesheet with Obsidian's fonts and
  `fontOrigin: local`, which silently overrides the theme block. Both are set,
  and set to agree.
