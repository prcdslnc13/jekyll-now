---
layout: post
title: UGH Splines in Draftsight
published: true
---
## UGH Splines

Ever have someone send you a file created in some non-CAD software and ask you to cut it on your machine? Where do your thoughts usually go to? Mine usually jump immediately to “ugh, what am I gonna have to do to this thing to make it cuttable.”

Now you may be saying “That’s awfully pessimistic Joe”. Well no, I’m just a realist, and I’ve done this before

Most people design things in graphic design software like Adobe Illustrator, Inkscape, and sometimes even Photoshop….

Most CNC, Laser, etc CAM programs that work in 2D need vector lines to create a path from. They are typically very picky about these lines too. They need to be closed, not over lapping or duplicates, and very often they are specific on the vector types (ie. NOT splines)

But your friend, client, Mom, whoever, sent you a file entirely made up of splines. And that’s the only file they have, and they need it cut tomorrow for their brother’s, friend’s, wife’s benefit BBQ to cure world hunger (or whatever world ending thing that this thing is required for). So now its on you to figure it out how to make this thing into usable geometry.

My old go to was just redrawing it. I’m a fair hand at 2D CAD and most designs are fairly simple when you get down to it. The problem with splines is they almost never have anything to measure from or dimension, and can be really shaky on the curves. So redrawing with Polylines (Polylines, its what CAM craves!) gets tedious and eventually makes you really wonder how much you don’t want to disappoint this person and all the reasons they might not really be your friend.

The next option is the SPLINEDIT command if you happen to have AutoCAD. But if your here, you don’t have AutoCAD you have Draftsight, and for some reason this is one of the few tools that didn’t seem to port to Draftsight. We have 3D edit tools but not spline. Weird. Anywayyyyy

In Draft sight there’s a really handy hack. And Here it is:

Open your document in whatever required software it was given to you in. In my case this one was a .EPS and Im working on it in Inkscape.
Save it out as a .DXF using Polyline output (hey we can always try), and be sure to set your Base unit properly.
selection_004

Open it up in DraftSight and verify that you failed to create PolyLines

selection_005

Yup its a Spline. No dice. BUT Here’s the hack. Save the file out as an R12.dxfselection_006

Now go and find that file. Notice the file size has grown a bit:

selection_007

Open it up and check your geometry again:

selection_008

## HUZZAH!! PolyLines!!!!!!!!

Ok Your not done quite yet. Most CAM wants those Plines to be closed to. You’ll have to use the PEDIT command and Join to connect all your lines. Occasionally you may have issues with this after this little hack. Before getting too frustrated use CTRL+A to highlight all your geometry and EXPLODE the drawing. This will break your drawing apart deeper and allow you to PolyLine everything. You will end up with TONS of nodes in curves, so be patient when trimming and things of that nature. And it might still be easier to put normal arcs in those areas, but this will lessen your work significantly.

Let me know in the comments below if you have and tricks or questions you would like me to cover!
