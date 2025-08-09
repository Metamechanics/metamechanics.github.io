alias:: mmls, mm-ls, mm-ecosys, MMM, mm-mycelium
tags:: #myApp #[[metamechanic mycelium back-end]]  
project:: [[allProjects]], [[Coding with AI]]
see-also:: [[Metamechanic Portfolio]], [[MetaWeb]]

- [[mycelium database schema]]
-
-
- the knowledge base underlying all MetaMechanic projects, books, works
  collapsed:: true
	- a network of notes underlying all mm projects
		- notes reused across multiple projects, publications and products
	- all projects can draw on notes that are used primarily in other projects
		- format and style them according to project and page needs
- What is [[mycelium]]?
  collapsed:: true
	- fungus as metaphor
	  collapsed:: true
		- underlies the forest
		- essential for life of forest
		- psychedelic, magical properties
		- medicinal properties
		- some toxic
		- its own unique kingdom of organisms
		- least regarded of the kingdom of life, but fundamentally important
	- The world doesn't see the mycelium. It sees above the surface, to what the mycelium feeds.
-
- contrast with [[Metamechanic Portfolio]]; portfolio is front-facing; mycelium is underlying.
- How do the entitites relate? Projects, books, websites, organisations, concepts, themes, messages
  collapsed:: true
	- Projects and books do things that can be categorised in terms of the relationships with each other. What are these categories?
		- Explore and investigate
		- Apply
		- Promote, expound, popularise message
		- Facilitate, allow, encourage
	- Understand this: the projects and books explore and expound the central pillars and principles of metamechanica. Thus, I need to define, decide, distinguish some central ideas. These are the pillars of [[Metamechanica]]
	- [[mycelium database schema]]
	-
	- see: [[Metamechanica Atlas]]
- Portfolio = multiple front-ends, MVPs; sub-domains for each project
	- These will expand to their own domains in time
- Mycelium = single, universal back-end
-
-
- Tech specs
	- single back-end
	  collapsed:: true
		- SQlite, because Logseq uses this, and it being universal ?
		- Supabase, Tadabase, or similar?
		- Baserow, AirTable or something similar
		- PostgreSQL
		- Neo4j or other graph database?
	- multiple front-ends; 1 for each project; or single front-end with sub-landing pages, all themed similarly for familiarity
	  collapsed:: true
		- multiple apps?
			- how is this different to front-end?
	- multi-player; wiki
	  collapsed:: true
		- permissions
			- levels of access to notes; both breadth (how many projects) and depth (admin, editor, author, commentator, reader)
	- frictionless data entry
		- writing
		- database entries
			- forms, defined by schema
	- Mechanism/platform of MM Mycelium
	  collapsed:: true
		- neo4j database?
		- how to enter data as readily as Logseq?
		- how to table and template like Notion, Tana, Capacities
		- how to view Knowledge Graph
		- how to view argument map
	- AI
		- use to create back-end and front-end
		- integrate into service ? -> [[Metamechanical AI]] with roles & personas, trained on internal data
-
- Github or Wiki? (or similar eg. GitPages) Community editing, forking etc #[[Questions To Self]]
-
- Every note needs a unique name
  collapsed:: true
	- This could relate to project or book its used for
		- eg. Note name is "Money in AMT framework" but is referenced by a "Money"-aliased link-label
		- "money" instead would be a general tag
		-