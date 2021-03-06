Paradox
=======

Paradox is a Markdown documentation tool for software projects.
The GitHub repo is [lightbend/paradox][repo].

**Paradox is NOT supported under the Lightbend subscription.**

### Setup

Find [the latest](https://github.com/lightbend/paradox/releases) version, and create `project/paradox.sbt`:

@@@vars
```scala
addSbtPlugin("com.lightbend.paradox" % "sbt-paradox" % "$version$")
```
@@@

Inside `build.sbt`, add `ParadoxPlugin` to a subproject:

```scala
lazy val root = (project in file(".")).
  enablePlugins(ParadoxPlugin).
  settings(
    name := "Hello Project",
    paradoxTheme := Some(builtinParadoxTheme("generic"))
  )
```

Then call `paradox` which will generate the site in `target/paradox/site/main`.

Your markdown documentation will go inside `src/main/paradox/`. For example, you can start with `src/main/paradox/index.md`.

### Key features

- Supports Multi-configuration.
- Supports @ref[GitHub flavored Markdown](features/markdown.md).
- Principled markdown extension using generic directives syntax.
- GitHub-friendly Markdown source (links work).
- Code snippet inclusion for compilable code examples.
- Templating and theming.
- Documentation overlay.

### Generic directive

Paradox extends Markdown in a principled manner called generic directives syntax,
which basically means that all of our extensions would start with `@` (for inline), `@@` (leaf block), or `@@@` (container block).

### License and credits

- Copyright 2015-2018 Lightbend, Inc. Paradox is provided under the Apache 2.0 license.
- The markdown engine is based on Mathias's [Pegdown][].

@@@ index

* [Multi Configuration](features/multi-configuration.md)
* [Markdown flavour](features/markdown.md)
* [Organizing pages](features/organizing-pages.md)
* [Linking](features/linking.md)
* [Groups](features/groups.md)
* [Snippet inclusion](features/snippet-inclusion.md)
* [Callouts](features/callouts.md)
* [Library dependencies](features/dependencies.md)
* [CSS Friendliness](features/css-friendliness.md)
* [Templating](features/templating.md)
* [Version warning](features/version-warning.md)
* [Theming](features/theming.md)
* [Documentation Overlay](features/overlay.md)

@@@

  [Pegdown]: https://github.com/sirthias/pegdown/
  [repo]: https://github.com/lightbend/paradox
