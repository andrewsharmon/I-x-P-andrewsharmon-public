# I-x-P-andrewsharmon-public
 Laser focusing related jigs/tools

 Focus_jig_1_10.stl (see features1.png)
 	This jig holds materials (designed for low cost business card stock) at a slope 1:10 to allow easy focus optimization and measurement. 
 	The jig has a zero reference plane to allow setting focus with the given material on top of this plane.
 	The center of the jig is aligned to the laser file via peaks and troughs to give high contrast alignment feature.
 	With included file ~+-4mm can be evaluated. (more slopes could be used too)

 	To print:
 		• Choose a nice layer height to bake a scale feature in the part! (recommend 0.2mm or 0.1mm)

 	Intended use flow:
 		• Place intend test surface on 'Zero Ref' surface and adjust laser Z to top of material for base Z setting
 		• Align fixture using a preview of single vertical line
 		• Place material on sloped surface and run job
 			* Recommend center line tick and bounding box.
 			* Recommend sparse cross hatch filled rectangle for just focus finding, but can also be used for matrix parametric searches. 
 		• Examine resulting sample for ideal settings (smallest dot, desired effect etc)
 		• Measure offset from center to desired parameter location. 
 			* required focus change will be approximately 0.1 * measured distance from center 


	Other applications:
 		•Microscope/camera Depth of Field checking (use calibration slide or make one!)




