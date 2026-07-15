# UC004 — Multi-Place Service Journey

**Example:** Retail Click-and-Collect Delivery
**Document status:** Informative working draft
**Specification version:** 0.1.0-draft
**Use-case identifier:** UC004

## 1. Purpose

This use case describes a service journey in which a service agent interacts with more than one Place in order to complete a single service outcome.

The primary example is a retail click-and-collect delivery:

1. a user places an order with a retailer;
2. the retailer prepares the order at a collection Place;
3. a delivery agent collects the order;
4. the agent transports it to the user’s Place;
5. the order is deposited or handed over;
6. the journey is completed and evidence is recorded.

This use case is broader than shopping delivery. The same journey pattern may also support:

* medication collection from a pharmacy and delivery to a residence;
* community equipment collection from a depot and delivery to a care recipient;
* laundry collection from a service location and return to a customer;
* collection of library materials and delivery to a user;
* collection of food from a restaurant and delivery to a Place;
* transfer of an item from one user’s Place to another;
* collection of repaired equipment and return to its owner.

The intended outcome is that one service journey can coordinate several related Place interactions without requiring the participating Places to share the same technology, operator, capabilities, or access policy.

## 2. Example scenario

A user places an online grocery order with a retailer and selects collection by an authorised delivery service.

The user provides or confirms:

* the retailer;
* the collection location;
* the order reference;
* the intended delivery Place;
* the requested collection or delivery time;
* any delivery preferences;
* whether unattended delivery is permitted.

The retailer prepares the order at a click-and-collect location.

The retail Place supports:

* collection-bay identification;
* order-reference validation;
* agent arrival reporting;
* collection instructions;
* staff-assisted handover or locker release;
* collection confirmation.

The user’s Place supports:

* an external gate;
* a secure delivery area;
* a delivery box;
* arrival notifications;
* temporary access;
* optional camera evidence.

A delivery provider accepts the journey and assigns an agent.

The agent travels to the retail Place, reports arrival, identifies the order, and receives the goods.

After confirming custody, the agent travels to the user’s Place.

The user’s Place validates the delivery assignment and grants only the access necessary to reach the permitted delivery point.

The goods are delivered, evidence is recorded, the delivery point is secured, and the overall service journey is marked complete.

## 3. Intended outcome

The use case is successfully completed when:

* the correct goods are collected from the correct source Place;
* the collection is performed by an authorised service agent;
* custody transfers from the source organisation to the service provider;
* the goods are transported to the intended destination Place;
* the destination interaction is authorised;
* the goods are deposited or handed over at the permitted destination;
* relevant access points are left secure;
* status changes are communicated;
* required evidence is associated with the appropriate stage;
* custody transfers to the recipient or destination Place;
* the overall service journey is completed or a clear exception is recorded.

## 4. Service journey structure

This use case introduces the concept of one service journey containing multiple Place visits.

A simple representation is:

```text
Service Journey
    │
    ├── Visit 1 — Collection from source Place
    │       ├── arrival
    │       ├── validation
    │       ├── access or handover
    │       ├── item collection
    │       └── custody accepted
    │
    ├── Transport stage
    │       ├── in transit
    │       ├── estimated arrival
    │       └── exception handling
    │
    └── Visit 2 — Delivery to destination Place
            ├── arrival
            ├── validation
            ├── access
            ├── item deposit or handover
            ├── evidence
            └── completion
```

A service journey may therefore contain:

* one or more Place visits;
* transport or processing stages between visits;
* separate authorities for each Place;
* separate evidence for each visit;
* an overall status representing the complete outcome.

The same service agent may perform every visit, but this should not be assumed.

## 5. Participants

### 5.1 Service recipient

The person or organisation for whom the overall service is being performed.

In the retail example, this is normally the customer receiving the goods.

### 5.2 Requesting party

The party that initiates or arranges the service journey.

This may be:

* the service recipient;
* the retailer;
* a care provider;
* another user;
* a marketplace;
* an NHS365 application;
* another service organisation.

### 5.3 Source organisation

The organisation responsible for making the goods or item available for collection.

Examples include:

* retailer;
* pharmacy;
* warehouse;
* restaurant;
* care-equipment depot;
* repair centre;
* another user.

### 5.4 Source Place operator

The person or organisation responsible for controlling service interaction at the source Place.

The source organisation and source Place operator may be the same party.

### 5.5 Destination Place operator

The person or organisation responsible for controlling service interaction at the destination Place.

For a residential Place, this may be the user, resident, household, landlord, care organisation, or another authorised party.

### 5.6 Service provider

The organisation responsible for coordinating or performing the service journey.

The service provider may manage:

* journey acceptance;
* agent assignment;
* route planning;
* collection;
* transport;
* delivery;
* status updates;
* evidence;
* exception handling.

### 5.7 Service agent

The person or automated system assigned to perform one or more visits in the service journey.

The service agent may be:

* a delivery driver;
* a courier;
* a care logistics worker;
* a subcontractor;
* a delivery robot;
* another authorised mechanism.

The initial NHS365 implementation is expected to focus on a human agent.

### 5.8 Place platforms

Each Place may use a separate platform to expose and coordinate its capabilities.

The source and destination Places are not required to use:

* the same platform;
* the same identity provider;
* the same access-control system;
* the same device technology;
* the same evidence policy;
* the same service instructions.

OSDI should allow the service journey to interact with both Places through a common service model.

## 6. Assumptions and preconditions

Before the journey begins:

* an order, item request, or service request exists;
* the source Place has been identified;
* the destination Place has been identified;
* the goods or item can be associated with the journey;
* the source organisation has accepted or recognised the collection;
* the destination Place has accepted or recognised the intended delivery;
* a service provider has accepted the journey;
* one or more agents may be assigned;
* relevant time windows are known;
* relevant handling requirements are known;
* the destination delivery preference is known;
* the journey can exchange meaningful status;
* applicable evidence policies are known.

The service provider should not need detailed knowledge of the internal technologies used at either Place.

## 7. Relevant Places and service points

### 7.1 Source Place

The Place from which the goods or item are collected.

Examples include:

* retail store;
* click-and-collect centre;
* pharmacy;
* warehouse;
* restaurant;
* depot;
* another user’s residence.

### 7.2 Source service point

The specific location at the source Place where collection occurs.

Examples include:

* collection bay;
* service counter;
* locker;
* loading point;
* refrigerated collection unit;
* staff handover area;
* secure external collection box.

### 7.3 Destination Place

The Place at which the goods or item are to be delivered.

Examples include:

* residence;
* apartment building;
* care facility;
* office;
* community location;
* secure collection hub.

### 7.4 Destination service point

The specific location where delivery is completed.

Examples include:

* front door;
* parcel box;
* delivery area;
* medicine locker;
* reception;
* staffed handover point;
* refrigerated delivery compartment.

## 8. Relevant source-Place capabilities

The source Place may expose:

* agent arrival reporting;
* collection-reference validation;
* order-ready status;
* service instructions;
* collection-bay allocation;
* locker or compartment access;
* staff notification;
* queue or delay information;
* item handover confirmation;
* item-temperature status where relevant;
* collection evidence;
* custody-transfer confirmation.

A source Place may provide the item through a person rather than an automated system. OSDI should support both.

## 9. Relevant destination-Place capabilities

The destination Place may expose:

* arrival notification;
* external gate access;
* main-entrance access where permitted;
* secure delivery-point access;
* delivery-point availability;
* resident approval;
* intercom or communication;
* evidence capture;
* item-presence confirmation;
* access-state confirmation;
* service instructions.

The source and destination capability sets may be completely different.

## 10. Information associated with the journey

The journey may use:

* journey identifier;
* originating request reference;
* source organisation;
* source Place;
* source service point;
* destination Place;
* destination service point;
* item or order reference;
* provider reference;
* assigned agent or assignment reference;
* source collection window;
* destination delivery window;
* handling requirements;
* item category;
* temperature requirements where relevant;
* collection instructions;
* delivery instructions;
* current journey status;
* current visit status;
* custody status;
* evidence references;
* exception details;
* completion time.

OSDI should not require the complete retailer order, payment record, route plan, or inventory record to be shared with either Place.

## 11. Identity and authority

### 11.1 Service-provider recognition

Each Place should be able to determine which provider is requesting interaction.

The source and destination Places may use different trust arrangements.

### 11.2 Agent recognition

The agent should present sufficient information to associate the agent with the relevant visit.

The same credential need not be accepted by both Places.

For example:

* the source Place may validate an order-collection assignment;
* the destination Place may validate a delivery assignment;
* NHS365 may link both assignments to the same service journey.

### 11.3 Separate Place authority

Authority should be granted separately for each Place.

Authority at the source Place may include:

* enter a collection lane;
* report arrival;
* collect a named order;
* open an assigned locker;
* confirm custody.

Authority at the destination Place may include:

* open an external gate;
* enter a delivery area;
* open a delivery box;
* deposit the item;
* capture approved evidence.

Authority granted at one Place must not imply authority at another Place.

### 11.4 Authority duration

Each visit should have its own limited authority based on:

* Place;
* visit;
* agent;
* service point;
* permitted actions;
* time window;
* visit state;
* expiry;
* cancellation;
* completion.

## 12. Custody model

This use case contains at least two custody transitions.

### 12.1 Source custody transfer

Custody transfers from the source organisation to the service provider when the item is accepted by the agent.

This may be confirmed by:

* source staff confirmation;
* agent confirmation;
* locker removal event;
* barcode scan;
* signed handover;
* another recognised method.

### 12.2 Destination custody transfer

Custody transfers from the service provider when the item is:

* handed directly to the recipient;
* deposited at an authorised service point;
* accepted by destination staff;
* placed into a secure destination compartment;
* otherwise completed under the agreed delivery method.

The exact legal interpretation remains subject to the service arrangement.

## 13. Normal journey

### Step 1 — User creates or confirms the request

The user places an order or creates a service request.

The request identifies:

* the item or order;
* the source Place;
* the destination Place;
* the preferred time;
* delivery requirements;
* any unattended-delivery preference.

### Step 2 — Source organisation accepts the order

The source organisation accepts and prepares the order through its normal systems.

### Step 3 — Service journey is created

A service journey is created or recognised.

The journey links:

* the source visit;
* the transport stage;
* the destination visit;
* the overall intended outcome.

### Step 4 — Service provider accepts the journey

A service provider accepts responsibility for one or more journey stages.

### Step 5 — Agent is assigned

The provider assigns an agent to the source visit, destination visit, or both.

Assignment may change before arrival.

### Step 6 — Source Place reports item ready

The source organisation or source Place reports that the item is ready.

The ready status may include:

* collection reference;
* source service point;
* collection window;
* handling instructions;
* expiry or latest collection time.

### Step 7 — Agent approaches the source Place

The agent application reports that the agent is approaching.

The source Place may prepare the relevant service point.

### Step 8 — Agent reports source arrival

The agent reports arrival at the source Place.

### Step 9 — Source visit is validated

The source Place checks:

* that the visit is recognised;
* that the item is ready;
* that the agent is assigned;
* that the time is acceptable;
* that the requested service point is available.

### Step 10 — Source instructions are presented

The agent receives instructions such as:

* use collection bay 4;
* present order reference;
* scan the displayed code;
* wait for staff handover;
* open locker 12;
* confirm the number of packages.

### Step 11 — Source interaction occurs

The item is handed over or released.

Where necessary, access to the source service point is granted.

### Step 12 — Agent verifies the item

The agent confirms the item or order through:

* barcode scan;
* order reference;
* package count;
* name or recipient reference;
* compartment assignment;
* another recognised method.

### Step 13 — Source custody transfers

The source organisation and service provider confirm that the agent has accepted custody.

The source visit is marked complete.

### Step 14 — Journey enters transport stage

The overall journey status changes to in transit or equivalent.

The user may receive:

* collection confirmation;
* estimated delivery time;
* agent progress;
* delay or exception updates.

### Step 15 — Agent approaches the destination Place

The provider or agent reports approaching status.

The destination Place may:

* notify the user;
* check capability availability;
* reserve a delivery point;
* prepare temporary authority.

### Step 16 — Agent reports destination arrival

The agent reports arrival at the destination Place.

### Step 17 — Destination visit is validated

The destination Place checks:

* that the journey is recognised;
* that the destination matches;
* that the delivery visit is active;
* that the agent is assigned;
* that the time is acceptable;
* that the delivery point is available;
* that the requested actions are permitted.

### Step 18 — Destination instructions are presented

The agent receives instructions such as:

* use the side gate;
* proceed to the secure delivery area;
* do not approach the main entrance;
* place ambient goods in compartment 1;
* request assistance for chilled goods;
* close and secure all compartments.

### Step 19 — Destination access is granted

Where required, limited access is granted for:

* external gate;
* delivery area;
* secure compartment;
* main entrance where explicitly permitted.

### Step 20 — Item is delivered

The agent hands over or deposits the goods.

Where the order contains multiple categories, different service points may be used.

For example:

* ambient goods in a parcel box;
* chilled goods in a refrigerated compartment;
* restricted items handed directly to an authorised person.

### Step 21 — Destination custody transfers

The destination interaction records that custody has transferred.

### Step 22 — Evidence is recorded

Evidence may include:

* source handover confirmation;
* package scan;
* collection timestamp;
* destination deposit image;
* recipient confirmation;
* delivery-point state;
* compartment lock confirmation;
* agent declaration.

### Step 23 — Destination service point is secured

Any gate, box, locker, or compartment used during delivery is closed and secured.

### Step 24 — Destination visit completes

The destination visit is marked completed or completed with exceptions.

### Step 25 — Overall journey completes

The service journey is completed when the required visits and custody transfers have been completed.

Temporary authorities associated with the journey expire or are revoked.

## 14. Example journey status

A simple journey status sequence may be:

```text
Requested
    ↓
Accepted
    ↓
Preparing
    ↓
Ready for Collection
    ↓
Agent Assigned
    ↓
Collecting
    ↓
Collected
    ↓
In Transit
    ↓
Approaching Destination
    ↓
Arrived at Destination
    ↓
Delivery Authorised
    ↓
Delivered
    ↓
Completed
```

Each visit may also maintain its own status.

For example:

```text
Source Visit:
Scheduled → Arrived → Authorised → Collected → Completed

Destination Visit:
Scheduled → Approaching → Arrived → Authorised → Delivered → Completed
```

## 15. Alternative and exception journeys

### 15.1 Order is not ready

If the source order is not ready:

* the agent may wait;
* the source may issue an updated estimate;
* the provider may reassign the journey;
* the collection may be cancelled;
* the destination estimate should be updated.

### 15.2 Source Place rejects the agent

The source Place may reject the agent because:

* the assignment is not recognised;
* the credential has expired;
* the wrong agent arrived;
* the collection window is invalid;
* the order has been cancelled.

Authority at the destination Place should not be activated solely because the journey exists.

### 15.3 Incorrect order is presented

The agent should not accept goods that cannot be associated with the journey.

The mismatch should be reported before custody transfers.

### 15.4 Some items are unavailable

The source organisation may offer:

* partial collection;
* substitution;
* delayed collection;
* cancellation;
* user approval.

The journey should indicate whether the destination visit remains valid.

### 15.5 Agent changes between visits

A different agent may perform the destination visit.

The journey should support:

* custody handover between agents;
* reassignment;
* separate credentials;
* updated destination authority;
* traceable status changes.

### 15.6 Goods require controlled conditions

Some goods may require:

* temperature control;
* time limits;
* separation from other goods;
* identity-verified handover;
* recipient signature.

The journey should record relevant handling requirements without requiring OSDI Core to define the full operating procedure.

### 15.7 Destination delivery point is unavailable

If the preferred destination point is full, offline, or unsuitable:

* another authorised service point may be proposed;
* resident approval may be requested;
* attended handover may be offered;
* the delivery may fail or be rescheduled.

### 15.8 User changes destination instructions

The user may change:

* destination service point;
* unattended-delivery permission;
* delivery time;
* contact preference.

Changes should not invalidate completed source custody records.

### 15.9 Destination access fails

If a gate, entrance, or delivery box cannot be operated:

* the agent may request help;
* the user may approve an alternative;
* the provider may use its normal exception process;
* goods may be returned to the source or another location.

### 15.10 Delivery requires direct handover

Age-restricted, controlled, high-value, or sensitive goods may require:

* verified recipient identity;
* signature;
* one-time code;
* attended delivery;
* refusal if the required recipient is unavailable.

### 15.11 Goods are damaged in transit

The agent should report:

* damage;
* affected packages;
* available evidence;
* whether delivery was attempted;
* whether goods were returned or retained.

### 15.12 Journey is cancelled after collection

If cancellation occurs after source custody transfer:

* the destination authority should be revoked;
* the provider should receive revised instructions;
* goods may be returned to the source;
* goods may be redirected;
* a new destination visit may be created.

### 15.13 Network access is unavailable

Each Place may apply its own offline policy.

The source may permit local order-code validation while the destination may require online validation, or vice versa.

### 15.14 Evidence capture fails

Failure of one evidence method should not necessarily fail the entire journey.

Each visit should record what evidence was or was not available.

## 16. Evidence and audit

A complete journey record should be able to answer:

* which request created the journey;
* which source and destination Places were involved;
* which provider accepted the journey;
* which agents performed each visit;
* when each visit occurred;
* which service points were used;
* when custody transferred;
* what authorities were granted;
* what access actions occurred;
* what evidence was captured;
* what exceptions occurred;
* whether the overall outcome was completed.

Evidence should be associated with the relevant visit rather than attached only to the overall journey.

## 17. Privacy considerations

The journey should minimise unnecessary disclosure between Places.

The source Place should not normally receive:

* detailed destination security information;
* destination camera information;
* resident presence;
* unrelated destination instructions.

The destination Place should not normally receive:

* source operational details;
* retailer inventory;
* source access-control information;
* unrelated order details.

The service provider should receive only the Place information required for each visit.

## 18. Security considerations

The implementation should guard against:

* fraudulent journey creation;
* unauthorised source collection;
* destination substitution;
* use of source authority at the destination;
* reassignment without appropriate credential update;
* item substitution;
* false custody-transfer claims;
* replay of visit credentials;
* access after visit completion;
* manipulation of journey status;
* disclosure of one Place’s security details to another;
* evidence attached to the wrong visit or item.

Each Place should remain independently responsible for its access policy.

## 19. Current-practice alignment

This use case should allow participating organisations to retain their existing systems.

The retailer may continue to manage:

* order creation;
* payment;
* inventory;
* substitutions;
* preparation;
* collection-point operation.

The service provider may continue to manage:

* journey acceptance;
* agent assignment;
* routing;
* tracking;
* transport;
* customer support.

The destination Place platform may manage:

* delivery preferences;
* access;
* notifications;
* evidence;
* Place capability operation.

OSDI or NHS365 may initially coordinate only the information needed to connect these existing processes.

## 20. Comparison with UC001–UC003

UC004 reuses many concepts already identified:

* requesting party;
* service provider;
* service agent;
* Place;
* service point;
* item or order reference;
* time window;
* instructions;
* capability;
* authority;
* status;
* evidence;
* completion;
* exception;
* custody transfer.

UC004 adds or validates:

* one journey containing multiple visits;
* distinct source and destination Places;
* independent authority at each Place;
* transport stages between visits;
* separate visit and journey status;
* multiple custody transitions;
* possible agent reassignment between visits;
* evidence associated with individual visits;
* coordination without shared Place technology.

## 21. Concepts validated

The following concepts now appear useful across the first four use cases.

### 21.1 Service Journey

A coordinated sequence of one or more activities intended to achieve an overall service outcome.

### 21.2 Service Visit

A bounded interaction with a specific Place as part of a Service Journey.

### 21.3 Place

A managed physical location at which a service interaction may occur.

### 21.4 Service Point

A specific location or function within a Place at which part of a service is performed.

### 21.5 Capability

A function made available by a Place to support an authorised service interaction.

### 21.6 Service Provider

An organisation responsible for coordinating or performing all or part of a Service Journey.

### 21.7 Service Agent

A person or automated system assigned to perform one or more Service Visits.

### 21.8 Authority

The limited permission to perform specified actions at a Place for a specific Visit.

### 21.9 Item

A physical object or grouped set of objects involved in the service outcome.

### 21.10 Custody

Responsibility for possession of an Item during a stage of the Service Journey.

### 21.11 Status

A meaningful indication of progress for a Journey or Visit.

### 21.12 Evidence

Information recorded to support confirmation of an action, state, transfer, exception, or outcome.

### 21.13 Exception

A condition that prevents or alters the intended normal journey.

These definitions are provisional and should be refined in a later core-concepts document.

## 22. Common OSDI needs identified

UC004 suggests that an initial OSDI baseline may need to support:

* creation or recognition of a Service Journey;
* association of one or more Service Visits;
* separate source and destination Places;
* service-point identification;
* service-provider and agent assignment;
* Place-specific authority;
* capability discovery;
* visit instructions;
* item or order references;
* custody state;
* visit status;
* overall journey status;
* evidence associated with a visit;
* exception reporting;
* cancellation;
* reassignment;
* authority expiry and revocation.

## 23. Proposed NHS365 starter implementation

### 23.1 User application

The NHS365 user application may allow a user to:

* request a collection-and-delivery service;
* identify or select the source organisation;
* enter an order or collection reference;
* select the destination Place;
* select the preferred destination service point;
* choose a time window;
* permit or deny unattended delivery;
* track source collection and destination delivery;
* receive delay or exception notifications;
* approve changed delivery instructions;
* view completion evidence.

### 23.2 Service-provider application template

The provider template may allow a partner to:

* accept available journeys;
* assign agents;
* manage source and destination visits;
* update status;
* record custody transfer;
* report exceptions;
* publish estimated arrival;
* complete the journey.

### 23.3 Agent application template

The agent application may provide:

* authentication;
* assigned journey list;
* source navigation and instructions;
* source arrival reporting;
* collection validation;
* custody confirmation;
* destination navigation and instructions;
* destination access requests;
* evidence submission;
* exception reporting;
* journey completion.

### 23.4 Source-organisation template

An early source template may allow a retailer or other organisation to:

* register a source Place;
* publish collection service points;
* receive journey or collection requests;
* mark orders ready;
* validate arriving agents;
* confirm handover;
* publish collection exceptions.

### 23.5 NHS365 platform services

The platform may provide:

* Service Journey coordination;
* Service Visit creation;
* source and destination association;
* provider and agent assignment;
* Place-specific authority;
* capability discovery;
* status exchange;
* custody recording;
* notifications;
* evidence association;
* audit recording.

### 23.6 NHS365 Place integration

At the source or destination, the NHS365 site agent may:

* expose local capabilities;
* operate gates, lockers, or delivery boxes;
* validate temporary authority;
* report state;
* request camera evidence;
* return normalised results.

## 24. Questions for refinement

1. Is Service Journey the correct name for the overall multi-visit process?
2. Is every Place interaction necessarily a Service Visit?
3. Can a Service Journey exist without a physical Place interaction?
4. Should transport be represented as a stage, activity, or Visit?
5. How should custody transfer between two agents be represented?
6. Should source and destination use separate credentials by default?
7. What is the minimum shared status model for journeys and visits?
8. How should partial collection or partial delivery be represented?
9. How should multiple destination Places be handled?
10. How should one source collection feed several destination deliveries?
11. How should one destination delivery combine items from several sources?
12. Should Service Point be a physical location, a logical function, or both?
13. How should temperature-controlled goods be represented without overloading OSDI Core?
14. What information may safely be shared between source and destination operators?
15. Which concepts belong in OSDI Core and which belong in an item-movement profile?
16. How should partner templates hide OSDI complexity while still remaining interoperable?

## 25. Initial conclusion

UC004 demonstrates that the same service-interaction concepts can be applied across more than one independently managed Place.

A complete service outcome may consist of:

* a Service Journey;
* one or more Service Visits;
* separate Place-specific authorities;
* one or more custody transfers;
* transport or processing stages;
* visit-specific evidence;
* an overall completion outcome.

The service provider does not need the source and destination Places to share the same implementation technology.

Each Place retains control over:

* its service points;
* its capabilities;
* its access policy;
* its evidence policy;
* the authority granted for each Visit.

This supports the initial OSDI objective of coordinating useful service outcomes while keeping Place implementations independent.
