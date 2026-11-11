# CityScape

## The AI
First off, full disclosure:
This project was created almost entirely with the use of AI, using absolutely god-awful
multi-shot prompting methods that no self-respecting AI expert/professional/slopper would ever
use. It wasted my Co-Pilot basic paid monthly allowance twice. It felt like managing a a
yes-man programmer more than a brilliant tool.

The intention of AI use in this project was to learn from it, and create proofs of concept for
some of my more ambitious ideas. Eventually, this entire project will be rewritten with human
hands and no AI. Until that happens, this project stands as a proof of concept.

Was that too long?


## The Pitch
Experience the cities of Bitburner like never before! As 3-Dimensional, neon af maps!
**Buildings**!
**Roads**!
**_TRAINS_**!
Let the world of bitburner come to life on your screen!

Stay out of the fog...

## The Vision
After playing Bitburner for a couple of years and learning a lot about... the early game...
and JS/TS, I began to yearn for something past the ascii art. I imagined the city maps as
actual cities, like Night City, bustling with life, filled with light, each location a
building in a tangible world.

Don't get me wrong. I love the ascii art. But I yearn for the... cities.

This is the first step toward fulfilling that yearning.


## The Bits
I had heard a while back, during my early forays into Bitburner, that you could manipulate the
UI. And about two months ago, I disovered [this post](https://steamcommunity.com/sharedfiles/filedetails/?id=2727778218) on the Steam forums, showing how
they created a basic file explorer script. Then I found various posts on some exploits after I
finally left proper "early-game". At that point, I began pondering what would be possible. I
wondered if I could use that method to create graphics for the game, but without assets.

This script does just that. By hooking WebGL and hijacking the city pages (and utilizing a
really stupid AI because I'm even stupidlier and don't know how to use WebGL yet) it reads
each city map and procedurally generates a 3D representation. It reads /,\, +, o, and x as
segments of a metro line (initially it was a road network, but I decided later I would prefer
a monorail), generates a railway in the same layout (smooths it out to appear as a connected
mesh), arbitrarily offsets the interactible locations and generates color coded buildings.
The railway is linked to your chosen theme's primary color, so it always matches your 
**_a e s t h e t i c_**. It places (hopefully) sensible monorail platforms near buildings.

When clicking on any building (that isn't one of the tiny insignificant ones), a card pops up
with all of its options, and most options are handled in the city map itself. Options with
extra text cards on hover in the original location pages also show a version of that card when
hovering over the option.
Right now, it doesn't always fit. That's okay, I can fix that later.

Protected buttons ({isTrusted?}) are handled by physically moving the original button into
place. Neither the AI nor myself could figure out a better way.

Streets and small buildings are generated through some witchcraft I have yet to decipher 
(but you can bet I'mma figure it out and use it in a game), and the fog is a shader.

Tiny cars roam the roads (not a lot rn), and trains ferry (as of yet non-existent) people between stations.

Since this largely uses procedural generation, there's no assets involved.


## The Install
Copy and paste this into your terminal:
> wget https://raw.githubusercontent.com/EphyMusic/Bitburner-CityScape/refs/heads/main/install.ts CityScape/install.ts

Then run the installer file.
> CityScape/install.ts

Quick alias:
> alias city="home;CityScape/main.ts"


## The Use
- Run the main typescript file!
> alias city="home;CityScape/main.ts"

> city

- Open the City tab!
- Hover over the buildings to see which location it belongs to!
- Click a building to open its location options!
- Click an option to do the option!
- Left-click and drag to rotate the map!
- Right-click and drag to move the map!
- Scroll to zoom in!
- A minimized tail is available to quickly shut down the script if needed. The tail will close itself when you press the stop button.
- Watch the trains!!!!!
- Also some tiny cars, but TRAINS!!!!!