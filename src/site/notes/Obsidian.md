---
{"dg-publish":true,"permalink":"/obsidian/"}
---

[[Excalidraw/Obsidian\|Obsidian]] - my Excalidraw guide on the tool to the BGSA meeting, 2023

## Obsidian basics
[Obsidian Forum](https://forum.obsidian.md/)
 
There's also a lot on youtube!
[Nick Milo](https://www.youtube.com/watch?v=QgbLb6QCK88&list=PL3NaIVgSlAVLHty1-NuvPa9V0b0UwbzBd)
[Visual note templates](https://www.youtube.com/watch?v=zmgqMZi6QL8)
[Excalidraw](https://www.youtube.com/watch?v=vlC1-iBvIfo&list=PL6mqgtMZ4NP1o3urKVf0j-s6sjP7yPE1R)
Linking your Thinking - Nick Milo
[Zsolt's Visual Personal Knowledge Management - YouTube](https://www.youtube.com/@VisualPKM)
[Eleanor Konik - YouTube](https://www.youtube.com/@eleanorkonik4704)
[Digital Garden](https://dg-docs.ole.dev/)
[kepano (@kepano)](https://twitter.com/kepano) - One of the creators
[Ilya Shabanov (@Artifexx)](https://twitter.com/Artifexx)
[The Effortless Academic | Ilya Shabanov | Substack](https://ilyashabanov.substack.com/)
## Excalidraw
- exporting a region of the drawing as a group will allow updates to go smoothly on the note it's inserted in!

## Calendar
[Calendar Cheatsheet](https://github.com/liamcain/obsidian-calendar-plugin/blob/master/README.md)

## Templater
[Introduction - Templater (silentvoid13.github.io)](https://silentvoid13.github.io/Templater/)

## Callouts

[Callouts Cheatsheet](https://help.obsidian.md/Editing+and+formatting/Callouts)

> [!abstract]

> [!note]

>[!info]

> [!todo]

> [!tip]

> [!success]

> [!question]

> [!warning]

> [!failure]

> [!danger]

> [!bug]

> [!example]

> [!quote]

## Dataview

[Dataview Cheatsheet](https://github.com/seburbandev/obsidian-dataview-cheatsheet)
[Dataview Query Builder](https://s-blu.github.io/basic-dataview-query-builder/)

## Checkbox

![Obsidian Menu.png](/img/user/Files/Obsidian%20Menu.png)![Obsidian Menu-1.png](/img/user/Files/Obsidian%20Menu-1.png)

## Zotero tag import snippet
{% if tags.length > 0 -%}{% for t in tags -%}#{% if t.tag == "secondary" %}source/secondary{% if not loop.last %}{% endif %}{% elif t.tag == "primary" %}source/primary{% if not loop.last %}{% endif %}{% elif "-project" in t.tag %}project/{{t.tag | lower | replace(" ", "-") | replace("-project", "")}}{% else %}subject/{{t.tag | lower | replace(" ", "-")}}{% endif %}{% if not loop.last %} {% endif %}{%- endfor %}{%- endif %}

## Transform tags into links
cd to your vault folder and execute the following command:

`sed -i 's/#MYTAG/\[\[MYTAG\]\]/g' *.md`

Replace `MYTAG` with the name of the tag you want to convert to a link.

The above command will replace all occurrences of `#MYTAG` with `[[MYTAG]]` in all of your markdown files in the current directory.