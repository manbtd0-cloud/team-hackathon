# Frontend / UI-UX Brief — Local Transport Discovery Platform

## 1. Product Purpose

The app helps people discover and understand **local transport routes that are normally difficult to find online**, especially when they are travelling in a new or unfamiliar area.

The platform has two main user groups:

1. **Local transport vendors** — drivers/operators who run vehicles on fixed or semi-fixed local routes.
2. **Passengers** — normal users who want to find available local transport around them.

The core value for passengers is **clarity and discoverability**.

The core value for vendors is **more visibility and more potential passengers**, which can increase their earnings.

The experience should feel very simple. A new user should be able to open the app, understand nearby transport options, and inspect a route without needing prior knowledge of the area.

---

# 2. Core Product Model

## Route

A route is the shared transport path itself.

A route contains:

- route name / label
- route category
- start point
- end point
- map path
- direction type
- one-way or two-way
- estimated duration
- stop behavior
- fare distance slabs
- vendors registered on that route

Multiple vendors may operate on the same route.

A vendor should therefore be able to either:

- **Create a new route**, or
- **Join an existing route**.

This distinction must be very clear in the vendor UI.

---

# 3. User Types

## A. Passenger

A passenger does not need to manage routes.

Their main goals are:

- see local transport routes near them
- choose how large an area to search
- inspect where a route goes
- choose the correct direction for a two-way route
- see approximate travel time
- understand expected fare
- see which vendors are currently active on that route
- see registered vendors even when they are currently inactive

The passenger experience should be **map-first, fast, and low-friction**.

## B. Vendor

A vendor needs an authenticated account.

Their main goals are:

- register as a transport vendor
- create or join a route
- enter vehicle/operator information
- publish useful transport details
- start a journey when they begin operating
- end a journey when they stop
- become visible to nearby passengers while active

---

# 4. Authentication Rules

Authentication is required for vendor actions.

A vendor must be logged in before they can:

- create a route
- join a route
- register vehicle/operator details
- start a journey
- end a journey
- modify their route association

Passenger browsing should be kept as frictionless as possible. If the product does not strictly require passenger accounts, the UI should avoid forcing login before route discovery.

---

# 5. Route Categories

Routes should be categorized so passengers can understand the type of local transport available.

The exact categories can be finalized later, but the frontend should support a category field/filter.

Possible examples:

- Wagon
- Van
- Coaster
- Rickshaw route
- Shuttle
- University transport
- Other local transport

The UI should not hard-code the product around only one vehicle type.

---

# 6. Vendor Flow

## Step 1 — Vendor Entry

Vendor enters the vendor side of the app.

Primary options:

- **Create New Route**
- **Join Existing Route**

This should be one of the clearest decisions in the vendor experience.

---

## Step 2A — Create New Route

If the vendor creates a route, they enter an **interactive map editor**.

The vendor should be able to define the route directly on the map.

The UI should support:

- selecting route start point
- selecting route end point
- adding/editing the route path
- viewing the route visually before saving
- setting whether the route is one-way or two-way

### One-way route

Only one operating direction exists.

Example:

A → B

### Two-way route

Transport operates in both directions.

Example:

A → B

and

B → A

The route visualization should make the direction obvious.

---

## Step 2B — Join Existing Route

Vendor searches/browses existing routes.

Each route card should provide enough information to avoid joining the wrong route:

- route name
- start point
- end point
- category
- map preview
- one-way / two-way indicator

Vendor selects the route and joins it as an operator.

The shared route geometry belongs to the route, while the vendor has their own vehicle/operator data and active journey state.

---

# 7. Vendor Registration Details

When a vendor registers themselves to a route, collect at least:

- vendor / driver name
- contact information
- vehicle registration number
- vehicle details where needed
- selected route
- estimated route duration
- stop type
- fare distance slabs

The form should be broken into small, understandable steps rather than one large form.

---

# 8. Stops

A vendor/route must indicate whether stops are:

## Fixed Stops

Passengers are expected to board or leave at defined locations.

The frontend should show these stops directly on the route map.

## Flexible Stops

The vehicle may pick up/drop off passengers along the route rather than only at predetermined stops.

The UI should communicate this clearly to passengers, for example:

**Flexible Stops — board/drop off along the route where permitted.**

Do not make a passenger assume that every route operates like a formal bus service.

---

# 9. Fare System

Vendors provide **estimated fares using distance slabs**.

Example concept:

- 0–3 km → Rs 50
- 3–6 km → Rs 80
- 6–10 km → Rs 120

The exact values are vendor-entered.

The passenger UI should display these as **estimated fares**, not guaranteed final prices unless the product later introduces fixed pricing.

On a selected trip, the frontend may calculate/show the expected slab based on the passenger's relevant travel distance.

---

# 10. Journey State

A registered vendor is not automatically considered active.

They must explicitly start and end journeys.

## Start Journey

When beginning a route journey, vendor taps:

**Start Journey**

The vendor becomes active for that route/direction.

For a two-way route, the vendor must select the direction they are currently travelling.

Example:

- FAST → F-10
- F-10 → FAST

## Active Journey

While active, the vendor should have a simple journey screen showing:

- route
- current direction
- journey status: ACTIVE
- start time
- estimated route duration
- clear **End Journey** action

The UI should prioritize readability while driving/working and avoid unnecessary interaction.

## End Journey

Vendor taps:

**End Journey**

Their current journey becomes inactive and passengers should no longer see them as an active vehicle for that journey.

---

# 11. Passenger Discovery Flow

This is the most important frontend experience.

## Passenger Home

The home screen should immediately answer:

> What local transport is available around me?

Recommended primary UI:

- current-location map
- search destination / area field
- radius selector
- nearby route markers/lines
- route list/cards below or over the map

The user should not need to understand transport terminology first.

---

# 12. Search Radius

Passengers can choose how far around their location they want to discover routes.

Example UI:

**Search within:**

- 1 km
- 3 km
- 5 km
- 10 km

or a slider.

Only routes relevant to the selected radius should be surfaced.

The designer should make the radius visible on the map where practical.

---

# 13. Route Cards

Nearby routes should have compact cards containing the most useful information.

Suggested contents:

- route name
- transport category
- start → destination
- distance from passenger to nearest relevant part/pickup point
- estimated duration
- estimated fare / fare starting point
- number of active vendors
- one-way / two-way indicator

Example:

**FAST ↔ F-10**

Wagon · Two-way

350 m away

~25 min · Fare from Rs 80

**3 vendors active**

---

# 14. Route Selection

When a passenger selects a route, open a detailed route screen.

If the route is two-way, they must select the direction they want.

Example segmented control:

**FAST → F-10** | **F-10 → FAST**

Changing direction should update:

- direction arrows on map
- start/end labels
- active vendors
- relevant fare/duration information

---

# 15. Route Detail Screen

This screen should contain:

## Map

- complete route line
- start point
- end point
- fixed stops, if applicable
- clear direction
- user's current position

## Route Information

- category
- estimated duration
- fixed/flexible stop behavior
- fare slabs / expected fare

## Vendor Information

Separate vendors into:

### Active Now

Vendors who currently have an active journey in the selected direction.

Show useful details such as:

- vendor name
- vehicle information
- contact option
- vehicle registration where appropriate
- current active status
- journey start time

### Registered / Currently Inactive

Vendors registered to the route but not currently running a journey.

This distinction must be visually obvious.

A passenger should never confuse a registered vendor with a vehicle that is currently operating.

---

# 16. Active vs Inactive Vendor UI

Suggested visual states:

## Active

**ACTIVE NOW**

Currently operating on this route.

## Inactive

**Not currently running**

Registered operator for this route.

The interface should prioritize active vendors at the top.

---

# 17. Core Navigation

Keep navigation small.

Possible passenger-first navigation:

- **Explore**
- **Routes**
- **Profile**

When the account is registered as a vendor, expose vendor functionality such as:

- **My Routes**
- **Journey**

Avoid creating a large dashboard-heavy navigation structure.

---

# 18. Important Screens to Design First

The UI/UX designer should start with these screens in this order:

## Passenger

1. Passenger Home / Nearby Routes Map
2. Nearby Route Cards
3. Route Detail
4. Direction Selection
5. Active + Inactive Vendor List
6. Fare / Route Information

## Vendor

7. Login / Registration
8. Vendor Home
9. Create Route vs Join Route
10. Interactive Route Map Editor
11. Route Details Form
12. Vendor + Vehicle Registration Form
13. Fare Slab Editor
14. Join Existing Route
15. My Route / Vendor Dashboard
16. Start Journey
17. Active Journey
18. End Journey Confirmation

Design the **passenger discovery flow and vendor route creation flow first**, because they form the core demo.

---

# 19. Key Frontend States

The designer must account for more than ideal screens.

Important states include:

- location permission not granted
- no routes found nearby
- route exists but no vendor is active
- one active vendor
- multiple active vendors
- one-way route
- two-way route
- fixed-stop route
- flexible-stop route
- route currently being edited
- vendor has no joined routes
- vendor is registered but journey is inactive
- vendor journey is active
- invalid/incomplete vendor form
- loading map/routes

---

# 20. UX Principles

## Passenger-first simplicity

The main audience includes people who are new to an area. They should not need local knowledge to understand the app.

Avoid technical language such as:

- route geometry
- operator instance
- service direction
- distance matrix

Use plain wording such as:

- Where do you want to go?
- Routes near you
- Active now
- About 5 minutes away
- Flexible stops
- Estimated fare

## Map-first

Transport is geographical. The map should be a primary part of the experience rather than a decorative secondary screen.

## Clear status

A passenger should always understand:

- where the route goes
- which direction they selected
- whether a vendor is currently active
- whether stops are fixed or flexible
- approximately what the ride costs

## Low-friction vendor experience

Vendors are motivated by increased discoverability and earnings, not by maintaining complicated digital records.

Every extra form field reduces the chance that a vendor registers.

Keep onboarding short and practical.

## Local usability

Design for ordinary users and local transport operators, not only highly technical smartphone users.

Use large touch targets, strong visual hierarchy, understandable map controls, and minimal typing where possible.

---

# 21. Main Demo Flow to Design Around

The hackathon demo should be visible in the product design itself.

### Vendor phone

1. Log in
2. Choose **Create Route**
3. Define route on map
4. Mark route one-way/two-way
5. Enter vendor + vehicle details
6. Set duration, stop type, and fare slabs
7. Publish/join route
8. Tap **Start Journey**

### Passenger phone

9. Open Explore
10. See the route nearby
11. Select the route
12. Choose direction if needed
13. See the complete map
14. See estimated duration/fare
15. See the vendor under **Active Now**

### Vendor phone

16. Tap **End Journey**

### Passenger phone

17. Vendor changes from active to inactive / disappears from Active Now.

This is the core end-to-end product experience.

---

# 22. Current MVP Boundary

The frontend should focus on:

- two user types
- route creation
- joining existing routes
- map-defined routes
- one-way / two-way routes
- vendor registration
- vehicle details
- estimated route duration
- fixed/flexible stops
- distance-based fare slabs
- start/end journey state
- nearby route discovery by radius
- route/direction selection
- active/inactive vendor visibility

Do not allow secondary ideas to distract the initial UI design.

Not required for the first frontend design unless later approved:

- booking seats
- online payments
- ratings/reviews
- chat
- complex fleet management
- advanced analytics
- nationwide route planning
- loyalty programs
- subscriptions

---

# 23. One-Sentence Product Definition

> A mobile platform that makes local transport routes discoverable by letting transport vendors publish the routes they operate and letting nearby passengers see where those routes go, what they cost, and which vehicles are currently active.

---

# 24. Primary Design Goal

The UI/UX designer should optimize for one outcome:

> **A person standing in an unfamiliar area should be able to open the app and quickly understand what local transport can take them where they need to go.**

Everything else is secondary.
