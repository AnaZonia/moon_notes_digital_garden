---
{"dg-publish":true,"permalink":"/obsidian/"}
---


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/excalidraw/obsidian/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">

<div class="markdown-embed-title">

# Obsidian

</div>



==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
But what is most useful is... 
Excalidraw 
Canvas 
Flow of ideas 
[[Remote Sensing\|Remote Sensing]] 
Easy Sharing 
Graph View 
- Free
- Open Source
- Large Community
- Many plugins (including one
that allows running R!)
- Markdown base (supports LaTeX!)
- Much customization! 
- Research Log
- Lit reviews
- Brainstorming
- Data sources, research networks 
So, what kind of note-taker are YOU? 
Oldschool Notetaking 
but then... 
LINKED NOTES! 
...And potentially a full "second brain"? 
Traditional - "simple text is enough!" 
Visual - "graphs, flowcharts and links, oh my!" 
All-in-One 

# Embedded files
f4d245ebac1fd5c0665b3c6697759db57ba75418: [[Pasted Image 20231110005256_953.jpg]]
e8cf95bf5be55336f61eb0b3e655ca9f951b121e: [[Pasted Image 20231110010750_080.png]]
f96494660b93e041e146ca5412fcfbbf57f64b24: [[Pasted Image 20231110011420_363.jpg]]
4b2f694fd2b665056112a9eb590896cf9076c6b2: [[Pasted Image 20231110013105_019.png]]
e3aac69e367b326a1a998805de44d9dbc240e1e5: [[Pasted Image 20231110013650_299.png]]
da41045ff023fb967aa94d3874d715556ada8d13: [[Pasted Image 20231110103335_997.jpg]]
932c0622adc0835282a5e4bdafcf005e20dde3ad: [[Pasted Image 20231110104222_291.jpg]]
806cfd3b49ce422c44bdce303f870f07484137ee: [[Pasted Image 20231110105425_134.jpg]]
b750a457dad9eb2ce18d5b7f0b378d8b01df7924: [[Pasted Image 20231110105455_142.png]]
128f6c7de23058fae8a42da3bf2f7ef23338c7e8: [[Pasted Image 20231110110524_752.png]]



</div></div>
 - my Excalidraw guide on the tool to the BGSA meeting, 2023

![](https://i.imgur.com/lyNDIxT.png)

## Where to learn more about Obsidian?
### If you have questions:
- [Obsidian Forum](https://forum.obsidian.md/)
- [r/ObsidianMD](https://www.reddit.com/r/ObsidianMD/)

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