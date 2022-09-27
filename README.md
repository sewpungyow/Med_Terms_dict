# Med_Terms_dict
Medical terminology Obsidian demovault

The content of this interactive dictionary is taken from Dunmore and Fleischer's *MEDICAL TERMINOLOGY Exercises in Etymology Edition III^[Walker-Esbaugh, Cheryl, Laine H. McCarthy, Rhonda A. Sparks, and Charles William Dunmore. _Dunmore and Fleischer’s Medical Terminology: Exercises in Etymology_. Ed. 3. Philadelphia, PA: F. A. Davis Co, 2004.]* (The book actually explains how to interpret and use this info.)
This interactive dictionary is made using the free program, [Obsidian.MD](https://obsidian.md/)^[https://obsidian.md/]

### About:
1. The **main use** of this database is to help break down medical terms that you might come across while taking notes for med school.
	- For example: [[achlorhydria]] can be parsed if you know how to identify the roots:
		- [[a-]] + [[chlor-]] + [[hydr-]] + [[-ia]] (to query for those roots, just type square bracket twice, and then type the root)
	- You can hover over the wikilink while holding either "ctrl" or "cmd" to view the definition of each individual root. It's all automated!
2. If you go into the global graph view, or if you activate the local graph view, you can see all of the relationships between each root. Global gives a birds-eye view. Local graph view will allow you to more directly see the most pertinent relationships. 
	- You can activate global graph view by clicking on the "open graph view" icon on the left sidebar.
		- This helpful search operator string will only show the medical roots. Enter this into the filter searchbar in the graph view: `#medroot -file:"Root_med template" -file:"exampleroottemplate" -file: "Appendix A Prefixes" -file:"READ THIS FIRST (Med terms dictionary)" -file:"Appendix B Combining Forms" -file:"Appendix C Combining Forms"`
		- You can also add: `-file:"Med Roots Dictionary"` to the previous filter
	- You can activate local graph view by clicking on the triple dot on the relevant page panel, then selecting "local graph". It's fun following the connections and seeing where they'll lead.
		- This is even cooler, because you can choose parameters that allow you to see direct siblings and cousins of that word. To do this, open up the filters tab in the local graph and type in: ```-#exclude``` (this excludes the central node), and then you can adjust the depth (this is "how related" they are). I like to also ensure "Incoming links", "Outgoing links", and "Neighbor links" are enabled in order to get the most holistic overview. Alternatively, you can type in: `-file: Med roots dictionary`
3. Some cool extra features included in each root's page:
	1. You can see all the medical terms that are derived from each root by looking in the derivations section.
		1. In order to take advantage of this extra feature (this isn't necessary but it's fun), you need to add metadata so that the database query detects it.
		2. There are two ways of adding the needed metadata ([tutorial](https://www.youtube.com/watch?v=rAoFGGMG-0g)).
			1. The first is what I use: it's YAML frontline metadata. At the very top of the page, you surround the labeled metadata with **three dashes**. The label you absolutely need to use is: ```roots: [root1, root2, root3]``` but you can also include the definition by adding ```definition: [definition]```. It's case-sensitive I believe. The frontmatter *must* be at the top (i.e. *front*) of he page.
			2. The second option is to use inline metadata. Instead of having the metadata at the top of the page surrounded by triple dashes, you simply type the variable name followed by two colons, a space, and your value. It's a little clunkier because you can't use multiple values enclosed in square brackets (this is called an array). The workaround is to have multiple inputs:
				1. `roots:: root1`
				2. `roots:: root2`
				3. `roots:: root3`
				4. `definition:: definition`
	2. You can also utilize the Query Functionality to bring up other bits of information, to help categorize and compare certain roots. (requires knowledge of Obsidian Dataview syntax)
		- (Dataview was also used to make the indices and compile the dictionary into the alphabetical format)
			- You can search for any metadata; if you use the template Dataview queries in the indices (eg to look for diminutives) you can copy the code. All you need to do to change all the queries at once via copy-paste is to enable VIM mode (settings > editor > vim key bindings) and type: ```:%s/word1/word2/``` where word1 = the word you want to find and where word2 = the replacement word. You can also use whatever other text editor, but every time I copy-pasted back into the file, it would add linebreaks which ruin the query.
4. This dictionary is designed more as a database, not a reference (although it still is useful as a reference). 
	- One issue is it uses aliases when a root word has multiple forms, which means if you use the traditional alphabetical search provided by the Dataview appendices rather than the searchbar, you may not find it.
	- Another issue in the same vein is that you can't predict which form will be listed in the alphabetical reference. There were limitations in how aliases work.
	- As long as you use the in-line links (enclose your word of interest in double square brackets: ```[[word_of_interest]]```) you will be able to locate that word, given it has been put into the dictionary. If it has not been put in the dictionary, you will need to add it to the dictionary. See section 5 for more info on adding words to the dictionary.
5. In order to add more terms and maintain all the functionality in this database, you will need to ensure that the metadata includes the tag: `#medroot`. See section 3.1.2 for info on adding metadata. I also recommend using the core plugin: [Templates](https://help.obsidian.md/Plugins/Templates)^[https://help.obsidian.md/Plugins/Templates]. I will include the template in this folder: [[exampleroottemplate]]

### More information:
Required plugins: Dataview
Optional plugins: Advanced Tables, Templates, Templater, Various Complements
- To implement these plugins, go to Settings > Options > Community Plugins. Turn off Restricted Mode, search the plugin name, download, then activate the plugin. For the Templates plugin, there's no need to download anything; you just need to activate the Core Plugin.
- If you're curious about learning more about Dataview, here is the [documentation](https://blacksmithgu.github.io/obsidian-dataview/data-queries/)^[https://blacksmithgu.github.io/obsidian-dataview/data-queries/]
Other plugins I used: Minimal theme, Hover Editor, Sliding Panes

### Possible (improbable) future plans:
1. Add synonym compare/contrast tables (completed)
2. Add less high-yield roots found in the [wikipedia](https://en.wikipedia.org/wiki/List_of_Greek_and_Latin_roots_in_English/A%E2%80%93G) page
3. Re-order tables so that more similar terms are grouped, rather than it being alphabetical
4. ???
