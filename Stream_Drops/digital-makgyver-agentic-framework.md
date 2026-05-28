
# Rapid prototyping and innovation with constrained resources
	(Agentic tool adaptation framework. Speed run the rapid prototying/design graph space (and more))
Fleshing out an idea that has been forming.  





## General concept:
* Tools and materials get tagged use instructions and technical information
* Ultra extensible and continually expanding with process innovations and tools
	* adding tools/materials/processes to inventory opens up additional combination graphs
* Toss tools/materials/problem in a bag and let agents go to town 
	* bounds set by low token simple input
		* targeted use scope
		* depth of search very scaleable
	* Intent based and goal oriented
# Implementation details
* vector/graph based, requirement and cost function driven
	* ex. precision machined titanium or hot glue and foam core?
	* ex. in house/on hand vs source etc. 
	* ex. krytox or mineral oil
* Parallel agent tree
	* scale/shape based on compute available 
	* dynamic refine based on cost functions
		* explore based on combinatorial cost functions and optimize path
		* ex. tool/fixture/process reuse cost function (with serial and parallel resource planning)
	* multi agent spinup based on figuring out sub task
		* keep contexts small for tasks at hand
		* ex. need revolute motion
			* bearing types and critical to specific application characteristics (low friction(rank), low cost (rank), light load (20N), tolerance (), need now or tomorrow (prioritize), 
				* bearing/plain
					* low friction
						* plastics
							* raw stock on-hand, needs machining, lathe not available, drill operation good enough for this application, needs to be at least 8mm thick to give okay angular constraint for intended shaft. 
						* bronze
							* none on hand, available next day from Amazon and McMaster (links)
				* bearing/roller/ball
					* 608 on hand
						* open sealed shielded option analysis
				* bearing/roller/cylindrical
					* none on hand for shaft size, bubble up design change option available with size change on shaft size and prep context/requirements specific info project specific temporary file. 
				* bearing/other
					* ferrofluid
					* (link) "use of novel material in novel configuration as bearing" (tag) (features: high temp, low cost)
* Activation function branch exploration weighting 
	* Proceed down lowest cost function path, but explore/think a few stages deeper
	* keep concise local decision tree reasoning associated with project graph expansion.
		* probably .files that mainly have pros/cons, reasoning and resultant parameters from decisions
		* likely include criticality and stickyness parameter to decisions and planning stage
			* cost function vector (you can't drill a hole smaller, but you could (if cost function permits) start over with new material, sleeve the hole, change hole function or change the location of the hole, but there are several cost function impacts from each)
* Post annealing from results
	* anneal design decisions based on achieved results or cost function minimization/change
	* anneal away steps if things changed during implementation/build
* script/toolify as much as possible
	* Reduce Token use over time

# Key Agents

## Protocol extractor/abstractor agent(s)
* extract steps
	* discretize steps
	* ex. install bearing
* abstract to general
	* remove tool/material specific aspects
	* ex. using 1/2 ton arbor press press in chilled bearing into side plate B
* track requirements/implementation
	* ex. there is a located revolute joint. 
		* it is on a side plate (there is a side plate, and a coresponding matching hole, it is )
		* it is a retained bearing
			* it is a ball bearing
			* it is interference press fit
				* chill required interference
				* hole needed
					* hole precision requirement
	* feature: flag for reconsider choice/evaluate alternatives
	* feature: link/flag dependencies for faster change search tree
## Accountant
* track path costs, cost functions and nudge exploration directions
## Solver
* explore graph space via combinatorial mix and match of tools, capabilities to hit goals/requirements
## Builder
* writes instructions to execute plan
	* step wise but use parallelism if resources/cost functions permit 
* uses tools directly where available
## Inspector
* checks outputs
* decides if as built is good enough or plan change is needed
* different QA tasks for different agents 
# Fixer
* loops in and coordinates hotfixes/corrective actions with user and other agents
* Leans heavily on Solver agent, but provides a nicer user interaction and coordination. 
# Extensions and other uses:
* QR / NFC tags on tools and materials feed data set into agent as available context
	* Pick up a thing and scan to get host of data context (like best user manual ever, context aware and natural language search!)
		* User overlay section to allow customized view port
		* Context aware for current projects
			* ex. epoxy scan checks for temperature suitability, outdoor use applicability and checks against current material combination compatibility in project. 
			* ex. soldering iron scan cross references available and on hand solders vs. checks threaded insert recommended temperatures for FDM plastics based on project. 
	* Ultra low barrier POC: link to notebookLLM curated for each item
		* Drop in manuals, technical datasheets, techniques, external links etc. 
	* Better grep or vector search document store based on items
		* Cross links and references possible
* Why yes, I would download a protocol 
	* Transform lab protocols to intent and utilize tools and materials on hand
	* Generic process extraction (ex. heat to 75C) to detailed setting instructions or digital control of specific hotplate
		* feedback and monitoring hooks 
			* 'is this going as expected' guardrails
				* nope, I'm needing to deliver way too much heat to hit temp
				* nope, it turned brown (or specifically the uv-vis-ir spectrum is not moving correctly)
				* nope, it is getting hotter with no added heat (trigger: cool down, on deck: emergency quench)
* Graph based identification of 'what tool should I add to my toolbelt?'
	* Analyze maximal graph capability expansion in specified vector via minimal cost function additions.
* Extend design space to phase diagram like vector space. 
	* precision or characteristic based Ashby like arbitrary axis phase spaces
		* tool/material regions
* external protocol/procedure feasibility research from papers (etc) in current resource contexts
	* subdivide larger protocols into discrete steps for reuse and modular adaptability.
		* likely store limiting factors based on current resources to make tool updates faster. 
* add tool control/readout
	* SAO style simple universal interface to allow generic wired or wireless control. 
		* get tool id or local info from tool eeprom
		* could do local use/skill storage if desired
		* could describe generic UI (to be layered with user UI style overlay) for standalone or web interface
			* likely just describe as setting (range), reading(range), macro type and let higher up decide implementation

Copyright Andrew Harmon 2026 (see commit history)