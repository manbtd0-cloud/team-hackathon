# Kimi Pitch Deck Generation Brief

## Working Product Name

**RouteMesh** — working name only; replace later if final branding changes.

## Objective

Create a polished 5-slide hackathon pitch deck for a mobile platform that makes informal/local transport routes discoverable.

The deck must be designed for a **live hackathon pitch**, not as a business report. It should be highly visual, immediately understandable, and easy to present quickly.

The core story is:

> Local transport exists everywhere, but much of it is digitally invisible. RouteMesh lets local transport vendors publish the routes they operate and lets travelers discover nearby routes, directions, fares, estimated duration, stop behavior, and which vendors are currently active.

## Product Model

There are two user types:

### Local Transport Vendor
- must register/login
- can create a new route or join an existing route
- new route is created through an interactive map
- route can be one-way or two-way
- vendor provides name, contact, vehicle registration and vehicle details
- vendor provides estimated route duration
- vendor marks stops as fixed or flexible
- vendor sets estimated fares using distance slabs
- vendor taps **Start Journey** when operating
- for two-way routes, vendor chooses current direction
- vendor taps **End Journey** when finished
- active journey status determines whether the vendor appears as active to passengers

### Passenger
- should be able to browse with minimal friction
- opens a map-first experience
- chooses a search radius around the current location
- sees nearby routes
- selects a route
- selects direction if the route is two-way
- sees the entire route on the map
- sees estimated route duration
- sees estimated fare / distance-based fare information
- sees whether stops are fixed or flexible
- sees active vendors separately from registered but inactive vendors

## Main Purpose

The main purpose is to help travelers in an unfamiliar area answer:

> **What local transport around me can actually take me where I need to go?**

The vendor incentive is simple: becoming discoverable to nearby passengers can bring more riders and therefore more earnings.

## What Makes It Different

Do not position this as another Uber/Careem clone or another formal public-bus timetable app.

The key gap is **informal and local fixed/semi-fixed transport that exists physically but is poorly represented online**.

Existing systems usually have one or more of these weaknesses:
- focus on formal/official transit
- depend on transport data already existing digitally
- do not show the local operator ecosystem
- do not clearly show whether a vendor is currently active
- do not expose local fare expectations, flexible stop behavior, or route-specific operator information

RouteMesh digitizes the routes that normally live only in local knowledge.

---

# Design Direction

Create a premium, modern, map-native visual identity.

Avoid:
- generic startup gradient decks
- cliché AI imagery
- stock photos of smiling commuters
- crowded bullet-heavy slides
- fake app screenshots
- excessive text

Prefer:
- dark charcoal / deep navy base
- off-white typography
- one strong route accent color such as vivid green, electric teal or lime
- a secondary warm accent for **ACTIVE** status
- thin map lines, nodes, direction arrows and route geometry
- large typography
- strong contrast
- subtle geographic/grid textures
- elegant route cards
- simple iconography
- clean native-mobile feeling

Use a 16:9 presentation format.

Each slide should communicate one idea within roughly 5 seconds of being seen.

Any UI screenshots are NOT available yet. Wherever screenshots will eventually appear, create clean empty device/frame placeholders labeled only:

**[APP SCREENSHOT PLACEHOLDER]**

Do not invent or fake application screenshots.

---

# Slide 1 — Hook / Problem

## Headline

**Every road is mapped. The ride you actually need isn’t.**

## Supporting idea

Local vans, wagons, coasters, shuttles and route-based transport move people every day — but a traveler entering a new area often has no digital way to know:

- what route exists nearby
- where it goes
- what it costs
- where they can board
- whether anyone is currently operating it

## Visual

Make this primarily visual.

Show an elegant abstract city map. Roads and landmarks are visible, but the local transport layer is initially absent/faded. A single bright route line should emerge across the map with a small local-transit vehicle marker.

Use one small human-style question somewhere on the map:

**“Bhai, yahan se F-10 ki koi wagon jati hai?”**

Do not overload the slide with bullets. The emotional idea is **transport exists physically, but digitally it is invisible**.

---

# Slide 2 — Why Existing Systems Miss It

## Headline

**The transport isn’t missing. The data is.**

## Structure

Use a clean side-by-side comparison.

### Existing digital maps / formal transit systems
- great when official route data already exists
- weak for informal/local operators
- often no local fare context
- no clear active/inactive operator state
- local route knowledge remains word-of-mouth

### What actually happens locally
- people ask drivers, conductors, shopkeepers or strangers
- vendors operate routes repeatedly but remain digitally invisible
- new travelers do not know which route to trust or where to board

## Visual

Show a polished map with a faded **digital blind spot** layer versus a bright community/local route network.

No logos of competitors are necessary unless later added intentionally.

---

# Slide 3 — The Solution

## Headline

**RouteMesh makes local transport discoverable.**

## Core visual

Show a two-sided system:

### Vendor side
**Create or join a route → register vehicle → start journey → become visible**

### Passenger side
**Open map → discover nearby routes → choose direction → see active vendors**

Connect both sides through one central route/map network.

## Feature callouts

Use short labels only:
- Interactive route creation
- One-way / two-way routes
- Fixed / flexible stops
- Distance-based fare slabs
- Search by radius
- Active vs inactive vendors
- Start / end journey state

Place **two clean [APP SCREENSHOT PLACEHOLDER] frames** on this slide or slide 4, whichever produces the better composition.

The slide should make it obvious this is a two-sided local transport network, not a taxi-booking app.

---

# Slide 4 — How It Works / Demo Flow

## Headline

**One route. Two sides. Live visibility.**

## Show a four-step horizontal or map-connected flow

### 1. Vendor publishes
Creates a new route on the interactive map or joins an existing route.

### 2. Vendor defines service
Adds duration, vehicle information, stop type and distance-based fare slabs.

### 3. Journey goes live
Vendor taps **Start Journey** and chooses direction when required.

### 4. Passenger discovers it
Nearby passengers can see the route, direction, estimated fare, duration, stops and the vendor under **Active Now**.

Then show a small final state:

**Vendor ends journey → active status disappears/changes immediately.**

## Visual

This should look like the actual live demo storyboard.

Use 2–3 phone/device placeholders labeled **[APP SCREENSHOT PLACEHOLDER]** connected by a route line.

Do not fill placeholders with fabricated UI.

---

# Slide 5 — Impact / Closing

## Headline

**Turn invisible transport into a digital network.**

## Passenger value

**For travelers:**
Know what runs nearby before asking strangers or guessing.

## Vendor value

**For vendors:**
More discoverability → more potential passengers → more earnings.

## Network effect

Every new route/vendor makes the map more useful for passengers.
More passengers make registration more valuable for vendors.

## Future expansion

Keep this subtle, not as a giant roadmap:
- more cities
- community route verification
- smarter multi-route journey planning
- live vehicle location where appropriate
- operator analytics / promoted visibility

## Final closing line

Large and memorable:

> **If a route exists on the street, it should exist on your map.**

End with the RouteMesh logo and a clean map/network visual.

---

# Presentation Rules

- Optimize for a 2–3 minute hackathon pitch.
- Do not turn slides into documentation.
- Use very little text per slide.
- Headlines should carry the narrative.
- Slides should look coherent as one visual system but each slide should have a distinct composition.
- Prioritize the actual problem and live product experience over speculative market-size numbers.
- Do not fabricate statistics.
- Do not fabricate user testimonials.
- Do not fabricate screenshots.
- Do not overuse the word AI unless a real AI feature is later added and demonstrated.
- The presentation must feel like a real mobility product, not an academic university project.
- Keep map visuals and route geometry as the main visual language throughout the deck.

# Logo Direction

Create a clean, scalable identity for **RouteMesh**.

The logo mark should combine the idea of:
- a route/path
- two or more connected map nodes
- movement/direction
- a network

Avoid literal clip-art buses, cars, steering wheels or generic map-pin logos.

Preferred concept: a minimal continuous route line connecting 2–3 nodes, subtly forming an **R** or forward-moving arrow. It should work both as a mobile app icon and beside the RouteMesh wordmark.

Style:
- geometric
- modern
- simple
- memorable at small size
- flat vector appearance
- no gradients required
- no excessive detail

Use the same accent color as the presentation route lines.