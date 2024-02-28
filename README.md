# Ultrafalcon - when learning doesn't want to hold hands with success
Let's start with a question: 

`How do you model learning that is accompanied by 'perceived failure'?`

As a parent, I'm constantly trying to ingrain my kids with a love of learning.  In learning, we can show thankfulness for what we have, and it's a way we can grow in perseverance and patience.  Knowing that children innately copy their parents in many things, including mannerisms, how are they copying my response to failure?  Do they ever see me fail?

Well, internet: here, see me fail...

### This learning experience has been generously sponsored by...
<a href="https://pcbway.com/"><img src="images/PCBWay.svg"  width="400"></a>

...my thanks and gratitude!

## Sponsorship details
This came into being when PCBWay offered to sponsor an entire PCB + PCBA order in exchange for me writing up a review of my experience on my blog.  After all was said and done, they paid for $140USD of product/shipping, I paid $45CAD import duties.

While I've usually gone to JLCPCB, when someone offers you a PCB sponsorship, you try not to look that gift horse over too closely - PCB costs add up!

I had just finished and submitted the mk19-pcb rev1 order, so something else was needed.  The only project I had come up with but dismissed was an expanded 'Falcon' PCB...

## Falcon EC11
Casuanoob's [Falcon EC-11 PCB](https://github.com/Bastardkb/Charybdis-EC11) rather blew me away when I was looking around for ideas.  I saw it in passing on the BKB discord's showcase channel - an encoder surrounded by LEDs!  Super cool.  

I ordered a stack of them, intending to make them a staple in my builds.  And indeed, they were introduced in the mk15 - one on each half - and I doubled down on the mk17, with each half having two!  The mk19 was going to get the same treatment.

This is what you get with a Falcon, seen on the mk17 & mk15:

<a href="https://i.imgur.com/iVyflip.jpg"><img src="https://i.imgur.com/iVyflip.jpg" width="400"></a>
<a href="https://i.imgur.com/7JUdEol.jpg"><img src="https://i.imgur.com/7JUdEol.jpg" width="400"></a>


## Designing the Ultrafalcon
As with most creative ventures (_well, for me_), there was a certain amount of 'sky's the limit' paired with 'standing on the shoulders of giants'.

**What if you could have a giant clacky center button on your giant encoder wheel that's an LCD and surrounded by LEDs?**

So I sketched something up in Fusion360...

<a href="https://i.imgur.com/hsWzCw7.jpeg"><img src="https://i.imgur.com/hsWzCw7.jpeg" width="1200"></a>

Immediate feedback was that I had used far too few LEDs.  The original Falcon has 12 - the first iteration of the Ultrafalcon had 18 - final has 30.  Still complaints about too few LEDs.  The internet community is always there to help.

'But why?', you ask...

1. Why not?
2. The existing Falcon uses a small-footprint EC11 encoder that frankly is not designed for huge wheels to be attached.
3. How cool is a button that's also an LCD screen??
4. Using a PER-series encoder wheel requires a PCB, so, "while I'm in there".

## JLCPCB & PCBWay
During this sponsorship trial I noted some of the benefits of choosing [PCBWay](https://www.pcbway.com) over [JLCPCB](https://www.jlcpcb.com) are...
- a lot more customization and options available (_e.g. 14 copper sizes, 15 board thicknesses, more colours, etc_)
- full "white glove" turnkey assembly (_they source the parts for you - just provide a BOM_)

There is obviously a cost to the variety of choice (_production lines are not cheap!_), but if you really just want nothing to do with figuring out which parts are in stock, backporting that to your design, and the back and forth - it's a very tempting value proposition.

Practically, however, it means you're paying (_this is my observation based on my use cases_) ~50% more at PCBWay.  Apples to apples, I compared the pricing:
- Cost to make pcb (_JLC vs. PCBWay_): $5 +shipping vs. $45 +shipping
- Cost to PCBA (_JLC vs. PCBWay_): $40 (no PER60 encoders) vs. $95 (_incl. PER60 encoders_)
- Total cost, all-in (_JLC vs. PCBWay_): **$120CAD vs. $245CAD** (_$145USD = $200CAD + $45CAD duties_) (_JLC total includes price for mouser.ca to ship me the PER60 encoders_)

Is `time=money` true for you?  Then maybe PCBWay makes more sense.  

A hindsight note is that if you are coming from experiences with JLCPCB, you will be very confused about the process at PCBWay.

JLC expects you to do a certain amount of legwork:
1. browse the parts catalogue, figure out what is in stock
2. add them to your local design tool
3. submit BOM (_before the parts go out of stock!_) (_BOM = bill of materials_)

Accordingly, JLC's parts inventory/selection is seemingly infinite.

PCBWay has taken a different approach:
1. add whatever parts you fancy to your BOM
2. submit BOM
3. PCBWay sources the part or its analogue

The challenge for JLC regulars is that you expect to find parts in their catalogue that just aren't there - simple things like RGB LEDs!  So rather than browsing, you literally just jam in the manufacturer part number to your BOM and go about your day.
e.g. `SW1,1,,PER60,Bourns,PER601-P117-N0015,tht`

Amusingly, I used JLC's catalogue to source many of my part numbers.

So, there are some warts with both processes, but frankly the outcome is you can create custom PCBs for what amounts to peanuts, enlarging the sphere of what you can accomplish creatively.  So even with some bumps along the road - you are enabled to reach into previously unattainable levels of craftsmanship and execution.  "The future is now." as they say.

## Kicad learnings
Without boring the casual reader, suffice to say that the discipline of electronics/PCB design is a lot more rigid than software work, so the process you have to follow is somewhat non-negotiable.

1. Supply all of your schematic symbols and PCB footprints.
2. Lay out your schematic.
3. Draw the PCB, meeting the manufacturer's [specifications](https://www.pcbway.com/pcb_prototype/PCB_assembly_Capabilities.html) for [tolerances](https://jlcpcb.com/capabilities/pcb-capabilities).
4. Export the necessary files for production.

<a href="https://i.imgur.com/urC7fgO.jpeg"><img src="https://i.imgur.com/urC7fgO.jpeg" width="500"></a>

*(click for higher resolution)*

No big deal, right?

Well.  Ok, so this was a huge learning curve.  But, once you get the hang of it - remembering that this is an established discipline, with a high googl-a-bility factor - it's just a matter of searching and gluing things together.

<a href="https://i.imgur.com/oK5EKrX.jpeg"><img src="https://i.imgur.com/oK5EKrX.jpeg" width="500"></a>

*(click for higher resolution)*

Some foreshadowing.  I initially had trouble sourcing the symbol/footprint of the LED pacakge, so ended up copying it from someone else who had successfully ordered with that design.

<a href="https://i.imgur.com/PuWn5U7.jpg"><img src="https://i.imgur.com/PuWn5U7.jpg" width="500"></a>

Can you spot the error?  Yeah, nobody else could, either.

## From Kicad to Fusion
Kicad has a super handy feature: `Export -> STEP file`

This provides you with a file you can directly import into Fusion 360, which means you can model around a real-life representation of your PCB, including all the components like connectors, LEDs, encoder wheels, etc.  Pictured is a work-in-progress view of the "LCD screen button" design.

<a href="https://i.imgur.com/R71jhLE.jpg"><img src="https://i.imgur.com/R71jhLE.jpg" width="800"></a>

<a href="https://i.imgur.com/Od7HjOc.jpg"><img src="https://i.imgur.com/Od7HjOc.jpg" width="800"></a>

Refactoring the mk19 model thankfully wasn't too bad - there was just enough room for the new PCB size.

## The order
My particular needs for the Ultrafalcon required the Bourns PER60 encoder, unfortunately only available via US sources.  This required an additional two to three weeks of processing time on their end - order the part from the US to China, get it on the bench, manually solder in place - and the parts themselves are $10CAD a piece.

When I mentioned warts earlier, this is where a particular oddity comes into play.  After submitting the parts and the engineering department finally gets to auditing them, the BOM I submitted is transformed into an XLS spreadsheet on their end.  They make some adjustments and send it over to me - via email - and I have to open the file, add my comments, save, and re-email it to them.

This is very very strange given the high levels of automation everywhere else on their site.

But, it worked out okay, after I went through the rigamarole of importing the XLS into Google Sheets.

Both JLCPCB and PCBWay require some level of your effort!

### Timing
Worth calling out first that adding US-source-only components definitely slowed things down, but, it's good info:
- Jan 25 - order submitted in full
- Feb 27 - order received at my house

A 30-ish day cycle time on figuring out 'will my design actually work' is a good reality check compared to the software world of 'minutes or less'.

## Receiving day
<a href="https://i.imgur.com/KbqWxu3.jpeg"><img src="https://i.imgur.com/KbqWxu3.jpeg" width="500"></a>
<a href="https://i.imgur.com/zwLD9xN.jpeg"><img src="https://i.imgur.com/zwLD9xN.jpeg" width="500"></a>
<a href="https://i.imgur.com/gRGX0FC.jpeg"><img src="https://i.imgur.com/gRGX0FC.jpeg" width="500"></a>

Once the order was processed, PCBWay shipped it via DHL and it arrived within a week (_speaking of 'the future is now' - shipping around the globe in less than a week?_).  Packaging is impressive - everything is static-bagged and generously enfolded in bubble-wrap.

## Testing
There's another important distinction I learned between the two: 
- JLC will take your files as-is and build _whatever you have provided_.  
- PCBWay will _correct any errors behind the scenes_ to ensure maximum quality.  

This seems as if PCBWay is doing you a favour, but if you combine inexperience, "it worked over there, probably be fine over here" attitude, and silent mistake fixing, you get... **a non-functional board**.

<a href="https://i.imgur.com/iT0XjaP.jpeg"><img src="https://i.imgur.com/iT0XjaP.jpeg" width="800"></a>

After all of the work, waiting, and planning - something had gone wrong!

When supplying power/gnd to the board, it would rapidly try to emulate a space heater - not something I'd designed in!

Thanks to an ancient 30x pocket scope, the trusty `burkfers` and `GeorgeN`, and a datasheet, the issue quickly became clear: the LEDs were mounted 90-degrees clockwise from what my PCB diagram required.

<a href="https://i.imgur.com/DOxjLa1.png"><img src="https://i.imgur.com/DOxjLa1.png" width="500"></a>
<a href="https://i.imgur.com/KmsC67y.png"><img src="https://i.imgur.com/KmsC67y.png" width="500"></a>
<a href="https://i.imgur.com/wTNIBPj.png"><img src="https://i.imgur.com/wTNIBPj.png" width="500"></a>

Still more to be gleaned from this prototype, however!!


### Testing the lug assemblies
<a href="https://i.imgur.com/IMbx6Gg.jpeg"><img src="https://i.imgur.com/IMbx6Gg.jpeg" width="500"></a>

A head scratcher - not sure how this happened...but obviously some Fusion fixes to be done.  This is the 'lower lug' of the connector.

### We can test the fitment of the pcb to the case

<a href="https://i.imgur.com/ZdFhHk5.jpeg"><img src="https://i.imgur.com/ZdFhHk5.jpeg" width="500"></a>

Aha!  I undersized the print.  When we do Ultrafalcon rev2, we can shrink the pcb to fit.  Visually, the size of it is pleasing.  Chomnky.

### And how does it feel?
Very happy with the PER60's size.  It's a little stiff, but with use that should ease up.  The general wheel size - 85mm - is great, an improvement on the mk17's 57mm.  This prototype is missing the LED reflector/diffusers.

<a href="https://i.imgur.com/eFlMTY2.jpeg"><img src="https://i.imgur.com/eFlMTY2.jpeg" width="1200"></a>

# Conclusion - Lessons learned and next steps
Not all learning is accompanied by "traditional" success.  But all learning is a success in and of itself.

- Sometimes you can do everything you know to be right and still 'fail'; revelation that you still have more to know, more to learn - this is ok!
- As in so many cases, even in the same industy niche you can have very different paradigms surrounding 'accomplish the goal'; don't assume that what works for NicheCompanyA will work for NicheCompanyB.
- Corollary for the above: You can't know when you've missed something, so design slack into the system.

How do you model "learning through failure" to our colleagues?  Our peers?  Our families?  Our communities?

I got the opportunity to show my children that even daddy fails at new things, and this is okay!  I learned from it!

What's next?

Why, Ultrafalcon rev2, of course! 


# Addendum - PCB details
With this PCB you get...
- [Bourns PER60 encoder w. debounce circuit](https://www.mouser.ca/new/bourns/bourns-per60-incremental-ring-encoders/)
- MX switch cutout (_or, passthrough for whatever else you mount in the middle_)
- Fitment for large 77mm or larger encoder handwheel
- 30 programmable SK6805-ER15 LEDs (_e.g. use with QMK's rgb matrix_) w. LED signal passthrough (_DI and DO pins_)
  - 24 on the outside of the encoder (_b/c 24 is twice 12...?_)
  - 6 on the inside of the encoder (_b/c two rings of illumination are better than one?_)
- 330ohm resistor on the DI line (datasheet recommendation)
- 1uF capacitor (_help avoid capacitance_)
- JST-XH 2.54 footprint (_or, just 8 through-holes spaced at 2.54mm_)

TODO: Also included are the relevant STL and Fusion files to get you started on including this in your build.

# Addendum - Using the Ultrafalcon in your own design
Open-source, use however you want - though really of most utility to the keyboard community.

## Mounting to your shell
My current method is to use a static "interface" part that gets combined into the forms shell.  Then the rest of your important pieces locate onto the "interface" part and everything works out swell.  Usually.

<img src="images/uf-render-cutaway.jpg"  width="800">

# not-included-in-the-PCB-details
I'll be using a GC9A01 circular 1.28" TFT and QMK's quantum painter feature.  The TFT uses an 8-pin 0.5mm pitch FPC cable which I'm threading down into the keyboard base.

# PCB details
<img src="images/uf-pcb-front.jpg"  width="400"><img src="images/uf-pcb-rear.jpg"  width="422">

The goal of this design was to provide a larger encoder wheel experience, and while doing that, why not add more LEDs? ... annnd while doing that, maybe add the capability of "room for activities" inside the encoder wheel.

Some of the existing Falcon issues I have are mostly centered on the fact that the EC-11 package was never meant to mount a super huge wheel, so you get wobble and tilt, and it generally just feels not quite right.  Further, the pcb was designed to fit the wonderful Charybdis keyboard, so has some packaging constraints that are unfortunate when not using a Charybdis! (_e.g. pin headers not on same axis_)

There's also no debounce as-is, though I'm sure something could be added.  The software debounce helps but you still run into issues from time to time.

So, being new to pcb design, I gave it a shot.
- dual ground planes (_2-layer board_)
- via 'ties' to keep ground as contiguous as possible
- 0.4mm power traces / 0.25mm data traces
- avoiding running power/data together as much as possible
- datasheets provide the source of design truth
- capacitor on-board to help with capacitance issues
- M3 mounting holes w. plating
- MX-size cutout (_plus another cutout for FPC cable/mounting block locator_)

# Schematic
- PER60 debounce circuit
  - 4x 10k ohm resistors
  - 2x 0.01uF capacitors
- 1uF capacitor for LED supply
- 330 ohm resistor for LED DI pin
- NOTE: to use the MX switch, solder some wires to the pins of the MX switch and the SW_A & SW_B pins; that pair of pins links up with the SW_A & SW_B pins on the 8-pin JST connection
