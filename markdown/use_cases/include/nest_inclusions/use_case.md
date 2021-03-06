### Nest Inclusions

An included markdown file can itself include more files.

#### File To Be Included

```includee.md```:
```markdown
Text for inclusion, and a nested inclusion.

@[:markdown](nested_includee.md)
```

#### File For Nested Inclusion

```nested_includee.md```:
```markdown
Text for nested inclusion.
```

#### Includer File

```includer.md```:
```markdown
File to do nested inclusion.

@[:markdown](includee.md)
```

#### Command

```sh
markdown_helper include --pristine includer.md included.md
```

(Option ```--pristine``` suppresses comment insertion.)

#### File with Inclusion

Here's the finished file with the inclusion and nested inclusion:

```included.md```:
```markdown
File to do nested inclusion.

Text for inclusion, and a nested inclusion.

Text for nested inclusion.
```
