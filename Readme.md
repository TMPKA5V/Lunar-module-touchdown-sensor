
## The touch down sensors of the lunar module of the early Apollo missions

![](/Images/1.jpg)

Astronauts had two lightbulbs that turned on when the LM legs touched the surface.

A very simple mechanism but very crucial because the engines had to be turned off immediately after touchdown, not earlier not later or probably the LEM and the men would have gone.
So I run some search on Google for Lunar Module Apollo and keywords along this line and landed (!) on the [Apollo Lunar Module Documentation page](http://history.nasa.gov/alsj/alsj-LMdocs.html) at [NASA History Division](http://history.nasa.gov/). I downloaded the [Apollo Operations Handbook Lunar Module part I](http://history.nasa.gov/alsj/LM10HandbookVol1.pdf). It’s a huge document, but after all it’s the handook of the Lunar Module. It could be larger, though.
I of course looked for the part related to the Lunar Contact Lights and the logic behind them : of course it could not be one switch and one lamp only.
Lunar Contact Lights (paragraph 2.10.2.2.2) reads “Both LUNAR CONTACT lights (panels 1 and 3) go on when one or more of the three lunar surface sensing probes contacts the lunar surface. When on, the lights advise the crew to shut off the descent engine.“….Makes sense.
The paragraph contains the electrical (principle) drawing of the circuit : a number of relays relay the contacts at Eagle’s probes and a few basic techniques are used to reduce the risks of false signalling or no signalling.
The circuit is this one (part II is available also at the NASA Technical Reports Server as Unclassified; No Copyright; Unlimited; Publicly available : I assume that the same applies to part I.

![](/Images/Principle-schematic.jpg)

The lights are two (top of drawing) on two different panels, namely panel 1 and panel 3. Both lamps light up when at least one of the probes touches the ground. The circuit is powered from two different sources and only when the descent engine is on – relay 3K7 controlled by switch K16B inside dotted square at left. Should the descent relay fail, switches 1K5B and 2K5B (at left) can be used to manually override switches to both supply lines. The two lamps are independently powered from the two power sources.

The circuit is redundant wherein the bulb besides being powered from two separate power sources, are controlled by two circuits. Let’s see :

Each lunar probe has two normally closed switches (n.c.). The double switch configuration at each leg prevents false signalling in case one of the switch mistakenly opens whatever the reason (say, vibrations).

Now consider Lunar Probe +Y. Both switches (bottom, center) must be activated to open the circuit and relase from ground the bases of transistors 1Q1 and 1Q2 which then go into conduction driving the relays 1K2 and 1K3. The path from ground is created through relays’ contacts 1K2A and 1K3A for panel 1′s lamp and contacts 1K2B and 1K3B for panel 3′s lamp.

The same applies for Lunar Probes -Y and -Z except that the parallel circuit at each leg are put in series : the circuit is open only when BOTH switches at EITHER probes are activated (open).

Now, should the circuit related to relay 1K2 or 1K3 or both fail, Lunar Probe +Y would not turn on the lamps, but two more Probes are there and one more driving circuit which mirrors the previous one : Lunar Probes -Z and -Y which drive transitors 2Q1 and 2Q2 and then relays 2K2 and 2K3.

It is important to note that should BOTH relay 1K2 AND 2K3 fail because the coils burns or the armatures lock or the transistors are damaged (a so-called double fault), the circuit would still work because a path to ground for the lamps could still be created through relays 1K3 and 2K2, unless one of these relays or the Probe switches also fail, a very unlucky combination.

Should BOTH relay 1K2 and 2K2′s circuits have failed (or BOTH 1K3 and 2K3) no path to ground could have been created for the lamps that would have stayed off.

A mean to make this latter double failure more unlikely might be to use different makes/models for relays 1K2 and 2K2 (and for relays 1K3 and 2K3). Or use the same high-availability relay from different batches.

Not that simple a circuit for lighting up two bulbs. A good circuit for a giant leap for the human kind.

Today it would probably still be made with discrete devices (no microcontrollers) in SIL design.

Not that I’ll read the whole document but those P&IDs (Piping and Instrumentation Diagram like the one depicting the Portable Life Support System at figure 2.11-6, top picture) and schematics are very intriguing. Definitely worth a look.

One final note : the drawing is dated 1 Feb 1970, so probably it is not exactly the same used on Eagle, nonetheless it was probably used on some subsequent mission, not less important than the first one.
