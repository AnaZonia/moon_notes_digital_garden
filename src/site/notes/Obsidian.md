---
{"dg-publish":true,"permalink":"/obsidian/"}
---

[[Excalidraw/Obsidian\|Obsidian]] - my Excalidraw guide on the tool to the BGSA meeting, 2023
[[Templates/Research Article - Legacy\|Research Article - Legacy]]

![](https://i.imgur.com/lyNDIxT.png)

## Where to learn more about Obsidian?
### If you have questions:
- [Obsidian Forum](https://forum.obsidian.md/)
- [r/ObsidianMD](https://www.reddit.com/r/ObsidianMD/)
- [Obsidian Help](https://help.obsidian.md/Home)
^note that obsidian sync and publish are paid services - alternatives are [Syncthing](https://syncthing.net/) and the Digital Garden plugin (listed below)
- or email me! ana.avila@mail.mcgill.ca - if there's enough people trying to get started with Obsidian, we can start a little support group to share resources

### Youtube tutorials
- [Nick Milo](https://www.youtube.com/watch?v=QgbLb6QCK88&list=PL3NaIVgSlAVLHty1-NuvPa9V0b0UwbzBd)
- [Visual note templates](https://www.youtube.com/watch?v=zmgqMZi6QL8)
- [Excalidraw](https://www.youtube.com/watch?v=vlC1-iBvIfo&list=PL6mqgtMZ4NP1o3urKVf0j-s6sjP7yPE1R)
- [Eleanor Konik - YouTube](https://www.youtube.com/@eleanorkonik4704)
- [Pandoc for Word and references](https://www.youtube.com/watch?v=yYZiO6CVtj8)

### Other creators
- [kepano (@kepano)](https://twitter.com/kepano)
- [Ilya Shabanov (@Artifexx)](https://twitter.com/Artifexx)
	- [The Effortless Academic | Ilya Shabanov | Substack](https://ilyashabanov.substack.com/)
^no need to buy courses or templates - I've just looked around for general ideas!
### Other main community plugins
- [Digital Garden](https://dg-docs.ole.dev/)
- [elias-sundqvist/obsidian-annotator: A plugin for reading and annotating PDFs and EPUBs in obsidian. (github.com)](https://github.com/elias-sundqvist/obsidian-annotator)
- [obsidian-tasks-group/obsidian-tasks: Task management for the Obsidian knowledge base. (github.com)](https://github.com/obsidian-tasks-group/obsidian-tasks)
- [Calendar Cheatsheet](https://github.com/liamcain/obsidian-calendar-plugin/blob/master/README.md)
- [Introduction - Templater (silentvoid13.github.io)](https://silentvoid13.github.io/Templater/)
- [Dataview in Obsidian: A Beginner's Guide - Obsidian Rocks](https://obsidian.rocks/dataview-in-obsidian-a-beginners-guide/)
- [Dataview Cheatsheet](https://github.com/seburbandev/obsidian-dataview-cheatsheet)
- [Dataview Query Builder](https://s-blu.github.io/basic-dataview-query-builder/)

## Callouts Cheatsheet
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

## Tasks Cheatsheet

![Obsidian Menu.png](/img/user/Files/Obsidian%20Menu.png)![Obsidian Menu-1.png](/img/user/Files/Obsidian%20Menu-1.png)

## Zotero tag import snippet
{% if tags.length > 0 -%}{% for t in tags -%}#{% if t.tag == "secondary" %}source/secondary{% if not loop.last %}{% endif %}{% elif t.tag == "primary" %}source/primary{% if not loop.last %}{% endif %}{% elif "-project" in t.tag %}project/{{t.tag | lower | replace(" ", "-") | replace("-project", "")}}{% else %}subject/{{t.tag | lower | replace(" ", "-")}}{% endif %}{% if not loop.last %} {% endif %}{%- endfor %}{%- endif %}

## Transform tags into links
cd to your vault folder and execute the following command:

`sed -i 's/#MYTAG/\[\[MYTAG\]\]/g' *.md`

Replace `MYTAG` with the name of the tag you want to convert to a link.

The above command will replace all occurrences of `#MYTAG` with `[[MYTAG]]` in all of your markdown files in the current directory.