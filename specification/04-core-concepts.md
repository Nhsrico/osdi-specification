# OSDI Core Concepts

**Document status:** Foundational working draft
**Specification version:** 0.1.0-draft
**Basis:** Derived from use cases UC001–UC004

## 1. Purpose

This document identifies the initial common concepts emerging from the first OSDI use cases.

The concepts are intended to provide a simple shared language for describing how services are arranged, performed, tracked, and completed across one or more Places.

This document does not yet define a complete information model, API, protocol, or conformance standard.

The concepts remain provisional and may be refined as additional use cases are developed, particularly care, maintenance, and emergency-access journeys.

## 2. Development approach

The initial OSDI model is being derived from practical service journeys rather than from a predetermined technical architecture.

The first use cases cover:

* delivery of an item to a secure delivery point;
* collection of an item from a Place;
* collection of an item for return;
* collection from one Place followed by delivery to another Place.

The concepts in this document have been included because they recur across several of those journeys.

A concept should not become part of OSDI Core merely because it is useful to one service provider or one implementation.

Service-specific requirements should normally remain in profiles or implementation guidance.

## 3. Concept overview

The initial concepts are:

```text
Service Request
      │
      ▼
Service Journey
      │
      ├── Service Visit
      │       ├── Place
      │       ├── Service Point
      │       ├── Capability
      │       ├── Authority
      │       ├── Action
      │       ├── Status
      │       └── Evidence
      │
      ├── Transport or Processing Stage
      │
      └── Additional Service Visits
```

The journey is performed by one or more Service Agents acting for one or more Service Providers.

Items may move between Places and may pass through one or more custody states.

## 4. Service Request

A **Service Request** expresses an intended service outcome.

Examples include:

* deliver an item to a Place;
* collect an item from a Place;
* return an item to a retailer;
* collect an order from a retailer and deliver it to a residence;
* perform a care visit;
* inspect or maintain equipment.

A Service Request may be created by:

* a user;
* a retailer;
* a service organisation;
* a Place operator;
* another authorised party.

A Service Request should describe the required outcome without defining unnecessary implementation detail.

A Service Request may lead to the creation of one Service Journey.

The initial baseline does not assume that OSDI must replace an existing provider booking or order system. A provider reference may be associated with an OSDI Service Request or Service Journey instead.

## 5. Service Journey

A **Service Journey** is a coordinated sequence of activities intended to fulfil a Service Request.

A Service Journey may contain:

* one Service Visit;
* multiple Service Visits;
* transport stages;
* waiting periods;
* processing stages;
* custody transfers;
* status updates;
* evidence;
* exceptions.

Examples include:

* one visit to deliver a parcel;
* one visit to collect a return;
* a source visit, transport stage, and destination visit;
* a scheduled care visit at a residence.

A Service Journey provides the overall context for:

* the intended outcome;
* involved parties;
* participating Places;
* assigned Service Providers;
* progress;
* completion;
* cancellation;
* exceptions.

A Service Journey should have a unique identifier within the system coordinating it.

The identifier does not need to replace provider order, tracking, job, or booking references.

## 6. Service Visit

A **Service Visit** is a bounded interaction with a specific Place as part of a Service Journey.

A Service Visit normally includes:

* one Place;
* one intended visit outcome;
* one or more participating Service Agents;
* a permitted time or condition;
* Place-specific instructions;
* Place-specific Authority;
* use of one or more Capabilities;
* progress Status;
* Evidence or completion information.

Examples include:

* depositing an item into a secure parcel box;
* collecting an item from a collection compartment;
* collecting an order from a retailer;
* delivering shopping to a residence;
* entering a residence to provide scheduled care.

A Service Journey may contain more than one Service Visit.

Authority granted for one Service Visit must not automatically apply to another Service Visit, even where both visits belong to the same Service Journey.

## 7. Place

A **Place** is a managed physical location at which a service interaction may occur.

Examples include:

* a house;
* an apartment;
* a residential building;
* a retail store;
* a pharmacy;
* a warehouse;
* a care facility;
* an office;
* a community location;
* a secure collection hub.

A Place may contain:

* public areas;
* controlled boundaries;
* external gates;
* delivery areas;
* collection areas;
* main entrances;
* shared spaces;
* restricted spaces;
* service-specific locations.

A Place is not defined by the technology used to manage it.

A Place may use:

* automated systems;
* human staff;
* smart-property platforms;
* access-control systems;
* local devices;
* cloud services;
* combinations of these.

A Place retains control over the Capabilities and Authority it makes available for a Service Visit.

## 8. Place Operator

A **Place Operator** is the person or organisation responsible for controlling or administering service interaction at a Place.

Examples include:

* a resident;
* a household;
* a landlord;
* a retailer;
* a building manager;
* a care organisation;
* a reception team;
* a local authority.

The Place Operator may define:

* available Service Points;
* permitted services;
* access rules;
* approval requirements;
* evidence policy;
* service hours;
* exception handling;
* restrictions on individual Capabilities.

A Place may have more than one authorised operator.

The internal governance of multiple Place Operators is outside the initial OSDI baseline.

## 9. Service Point

A **Service Point** is a defined location or function within a Place at which part of a service may be performed.

Examples include:

* parcel box;
* collection locker;
* front entrance;
* external gate;
* loading bay;
* collection counter;
* refrigerated compartment;
* reception desk;
* medicine cabinet;
* designated care area.

A Service Point may be:

* physical;
* staffed;
* automated;
* temporarily assigned;
* permanently configured.

A Service Point may expose one or more Capabilities.

A Service Point should be described in service-relevant terms rather than through vendor-specific device identifiers.

For example:

```text
Preferred:
Secure collection box 1

Not preferred:
lock.parcel_box_relay_03
```

The underlying implementation identifier may still be used internally by the Place platform.

## 10. Capability

A **Capability** is a function made available by a Place to support an authorised service interaction.

Examples include:

* request gate opening;
* request entrance access;
* open a secure compartment;
* report arrival;
* call an intercom;
* request resident approval;
* confirm whether a Service Point is available;
* capture permitted evidence;
* confirm that an access point is secure;
* report item presence.

A Capability describes an available outcome or function.

It should not require the service provider to understand the underlying:

* device;
* entity identifier;
* automation platform;
* communication protocol;
* manufacturer;
* local control logic.

For example, a gate-access Capability may be implemented using:

* a smart gate controller;
* an access-control system;
* a Home Assistant entity;
* a temporary code;
* a remote operator;
* a staffed reception point.

The initial OSDI baseline should define only the minimum Capabilities required by the validated use cases.

## 11. Service Provider

A **Service Provider** is an organisation responsible for coordinating or performing all or part of a Service Journey.

Examples include:

* parcel carrier;
* retailer delivery service;
* collection provider;
* care provider;
* maintenance contractor;
* local delivery cooperative.

A Service Provider may:

* accept a Service Request;
* create or recognise a Service Journey;
* assign Service Agents;
* manage routing and scheduling;
* exchange status;
* record custody;
* report completion;
* manage exceptions.

A Service Provider remains responsible for its own operational systems and procedures unless the service arrangement states otherwise.

OSDI should not require a provider to replace its existing job, route, order, care-management, or tracking systems.

## 12. Service Agent

A **Service Agent** is a person or automated system assigned to perform one or more Service Visits.

Examples include:

* courier;
* driver;
* care worker;
* engineer;
* authorised subcontractor;
* delivery robot.

A Service Agent acts on behalf of a Service Provider or another authorised organisation.

A Service Agent should be associated with the Service Visit it is permitted to perform.

The required level of individual identification may vary according to:

* service type;
* risk;
* requested Capability;
* Place policy;
* regulatory or contractual requirements.

For a low-risk external parcel-box delivery, a valid provider-confirmed assignment may be sufficient.

For care access to a residence, stronger individual identity and role verification may be required.

## 13. Requesting Party

A **Requesting Party** is the person or organisation that initiates or arranges a Service Request.

Examples include:

* resident;
* retailer;
* recipient;
* sender;
* care organisation;
* marketplace;
* another service provider.

The Requesting Party is not necessarily:

* the Service Recipient;
* the Place Operator;
* the Service Provider;
* the owner of an Item.

These roles may be performed by the same party in simple journeys but should not be assumed to be identical.

## 14. Service Recipient

A **Service Recipient** is the person or organisation intended to benefit from the Service Journey.

Examples include:

* a user receiving shopping;
* a resident receiving a parcel;
* a person receiving care;
* a business receiving equipment;
* an organisation receiving a returned item.

The Service Recipient may or may not be present during a Service Visit.

The Service Recipient may also be the Requesting Party or Place Operator.

## 15. Item

An **Item** is a physical object, package, or grouped set of objects involved in a Service Journey.

Examples include:

* parcel;
* grocery order;
* medication package;
* returned product;
* equipment;
* documents;
* several packages treated as one order.

An Item may have:

* a provider reference;
* an order reference;
* a return reference;
* an identifier;
* size or category information;
* handling requirements;
* condition information;
* evidence.

The initial OSDI baseline should not attempt to define full product, inventory, customs, or commercial-order data.

Only information necessary to coordinate the Service Journey should be exchanged.

## 16. Custody

**Custody** describes which party currently accepts operational responsibility for possession of an Item.

Examples include:

* source organisation retains custody before collection;
* Service Provider accepts custody at collection;
* another agent accepts custody during a handover;
* destination Place or recipient accepts custody at delivery.

A custody transition should be associated with:

* an Item;
* a Service Journey;
* a stage or Service Visit;
* the transferring party;
* the receiving party;
* a time;
* available Evidence;
* any exception.

Custody does not necessarily define legal ownership.

The legal effect of custody transfer remains subject to the relevant service agreement, provider terms, and applicable law.

## 17. Identity

**Identity** describes the recognised person, organisation, system, or automated agent participating in an OSDI interaction.

Identity may apply to:

* Requesting Party;
* Service Provider;
* Service Agent;
* Place Operator;
* Service Recipient;
* Place platform;
* another participating system.

OSDI should state what identity or organisational information is required for an interaction without requiring a particular identity provider.

For example, NHS365 may use IAAM365, while another implementation may use a different trusted identity service.

## 18. Credential

A **Credential** is information presented to support a claim about identity, assignment, role, or authority.

Examples include:

* signed provider token;
* temporary access code;
* QR code;
* job reference;
* digital identity credential;
* provider application session;
* care-worker credential;
* locally verifiable short-lived credential.

A Credential is evidence supporting a claim.

Possession of a Credential should not automatically grant unrestricted access.

The Place or coordinating platform should evaluate whether the Credential supports the requested action in the current Service Visit.

## 19. Authority

**Authority** describes what a participant is permitted to do for a specific Service Visit.

Authority should normally be limited by:

* Service Visit;
* Place;
* Service Point;
* Service Agent or assignment;
* permitted Capability or Action;
* time window;
* conditions;
* completion;
* cancellation;
* expiry;
* revocation.

Examples include authority to:

* open an external gate;
* enter a designated delivery area;
* open one assigned parcel box;
* collect one identified Item;
* capture one permitted evidence image;
* enter a residence for a scheduled care visit.

Authority at one Place does not imply Authority at another Place.

Authority to use one Capability does not imply authority to use unrelated Capabilities.

## 20. Permission

A **Permission** is a specific action or class of actions allowed by an Authority.

Examples include:

* request gate opening;
* access parcel box 1;
* collect Item A;
* deposit Item B;
* request resident contact;
* capture delivery evidence;
* enter the main entrance.

For the initial OSDI baseline, Permission may be treated as part of Authority rather than as a fully independent model.

A separate detailed permission model should only be introduced if the use cases require it.

## 21. Action

An **Action** is a requested or performed operation during a Service Visit.

Examples include:

* report arrival;
* request gate access;
* open a compartment;
* confirm an Item is ready;
* confirm collection;
* confirm delivery;
* record custody transfer;
* request evidence capture;
* close a Service Point;
* report an exception.

An Action may have:

* a requesting party;
* Authority;
* a target Capability or Service Point;
* a result;
* a timestamp;
* related Evidence;
* an exception.

The specification should focus on meaningful service actions rather than low-level device commands.

## 22. Instruction

An **Instruction** is information provided to help a Service Agent complete a Service Visit correctly.

Examples include:

* use the side gate;
* proceed to collection bay 4;
* do not approach the main entrance;
* open parcel box 1;
* remove only the package with the current reference;
* place chilled goods in the refrigerated compartment;
* call the resident if the box is full.

Instructions may be:

* static Place instructions;
* service-specific instructions;
* generated from current Capability state;
* updated during a Service Visit.

Instructions should be brief and should not reveal unnecessary Place, security, or personal information.

## 23. Time Window

A **Time Window** describes when a Service Journey, Service Visit, Authority, or Action may occur.

Examples include:

* scheduled collection period;
* expected delivery interval;
* care-visit start and end time;
* temporary credential validity;
* return deadline;
* grace period.

A Time Window may be:

* exact;
* estimated;
* flexible;
* conditional;
* extended by approval.

The initial baseline should support a permitted interval without requiring a complex scheduling model.

## 24. Status

A **Status** is a meaningful indication of progress or outcome.

Status may apply to:

* Service Request;
* Service Journey;
* Service Visit;
* Item readiness;
* custody;
* Capability availability;
* completion;
* exception.

Examples include:

* requested;
* accepted;
* scheduled;
* preparing;
* ready;
* approaching;
* arrived;
* authorised;
* collected;
* in transit;
* delivered;
* completed;
* failed;
* cancelled.

Provider-specific status models may contain more detail.

OSDI should initially define only a small set of shared status meanings needed for interoperability.

A Service Journey and its Service Visits may have separate statuses.

For example:

```text
Journey: In Transit

Source Visit: Completed

Destination Visit: Scheduled
```

## 25. Evidence

**Evidence** is information recorded to support confirmation of an Action, state, transfer, exception, or outcome.

Examples include:

* timestamp;
* agent declaration;
* barcode scan;
* provider proof-of-delivery reference;
* image;
* short video segment;
* access-point state;
* parcel-box lock state;
* item-presence indication;
* resident approval;
* custody confirmation.

Evidence should be associated with the relevant:

* Service Journey;
* Service Visit;
* Action;
* Item;
* custody transfer;
* exception.

Evidence should be proportionate to the service and risk.

The existence of a camera or sensor does not imply that a Service Provider or Service Agent receives unrestricted access to it.

## 26. Exception

An **Exception** is a condition that prevents, delays, changes, or qualifies the intended Service Journey or Service Visit.

Examples include:

* invalid Credential;
* unavailable Service Point;
* Item not ready;
* incorrect Item;
* full delivery box;
* access failure;
* agent reassignment;
* late arrival;
* evidence unavailable;
* delivery rejected;
* journey cancelled after collection.

An Exception should identify:

* where it occurred;
* what was affected;
* whether recovery is possible;
* what status resulted;
* whether human action is required.

The initial baseline should use clear provider-friendly exception descriptions rather than an extensive formal error taxonomy.

## 27. Completion

**Completion** indicates that a Service Journey or Service Visit has reached an intended or accepted final outcome.

A Service Visit may be:

* completed successfully;
* completed with an exception;
* failed;
* cancelled.

A Service Journey should not normally be marked successfully completed until all required Service Visits and stages have reached acceptable outcomes.

Completion of a Place interaction does not necessarily mean completion of a later commercial process.

For example:

* return collection may be completed;
* retailer inspection may still be pending;
* refund may not yet have been issued.

## 28. Cancellation

**Cancellation** indicates that a Service Request, Service Journey, or Service Visit should no longer proceed as originally planned.

Cancellation may occur:

* before assignment;
* before arrival;
* after temporary Authority is issued;
* after one Visit is completed;
* after custody has transferred.

Cancellation should result in appropriate action, such as:

* revoking unused Authority;
* invalidating Credentials;
* notifying participants;
* preserving completed records;
* creating a revised Journey;
* returning or redirecting an Item.

## 29. Relationship summary

The initial relationships may be summarised as follows:

* a Requesting Party creates or initiates a Service Request;
* a Service Request may produce a Service Journey;
* a Service Journey fulfils an intended service outcome;
* a Service Journey contains one or more Service Visits or other stages;
* each Service Visit occurs at one Place;
* a Place is controlled by one or more Place Operators;
* a Service Visit may use one or more Service Points;
* Service Points expose Capabilities;
* a Service Provider coordinates or performs all or part of a Service Journey;
* a Service Agent performs one or more Service Visits;
* Credentials support claims about identity, assignment, or Authority;
* Authority limits what may be done during a Service Visit;
* Actions use Capabilities under that Authority;
* Items may move through the Service Journey;
* custody may transfer between parties;
* Status describes progress;
* Evidence supports recorded outcomes;
* Exceptions alter the normal journey;
* Completion records the final result.

## 30. Conceptual example

A retail collection-and-delivery journey may be represented as:

```text
Service Request
    Deliver order 123 from Store A to Home B

Service Journey
    Journey J1001

Source Service Visit
    Place: Store A
    Service Point: Collection bay 4
    Agent: Driver D7
    Authority:
        - report arrival
        - collect order 123
        - confirm custody

Transport Stage
    Custody: Delivery Provider

Destination Service Visit
    Place: Home B
    Service Point: Secure delivery box
    Authority:
        - open external gate
        - access delivery area
        - open delivery box
        - deposit order 123
        - record permitted evidence

Completion
    Source Visit completed
    Destination Visit completed
    Journey completed
```

The source and destination may use entirely different implementation technologies.

## 31. Core versus profile-specific concepts

The following concepts currently appear suitable for OSDI Core:

* Service Request;
* Service Journey;
* Service Visit;
* Place;
* Place Operator;
* Service Point;
* Capability;
* Service Provider;
* Service Agent;
* Requesting Party;
* Service Recipient;
* Identity;
* Credential;
* Authority;
* Action;
* Instruction;
* Time Window;
* Status;
* Evidence;
* Exception;
* Completion;
* Cancellation.

The following may belong primarily in an item-movement profile:

* Item;
* Item-ready state;
* custody;
* delivery;
* collection;
* return;
* packaging;
* label status;
* return authorisation;
* item condition.

Item and custody may still be useful in OSDI Core if future non-logistics use cases demonstrate broader equivalents.

The care use cases should help determine whether similar concepts apply to medication, equipment, documents, or responsibility for a person-related service outcome.

## 32. Simplicity principles

The initial OSDI Core should remain small.

The following principles should guide refinement:

1. Use familiar words where possible.
2. Avoid introducing a concept unless several use cases need it.
3. Do not model provider systems that OSDI only needs to reference.
4. Do not expose implementation-specific devices through the common model.
5. Keep Place Authority limited and understandable.
6. Allow early providers to integrate without replacing their existing systems.
7. Prefer a small useful baseline over a complete theoretical model.
8. Place service-specific detail into profiles.
9. Validate every core concept through working NHS365 demonstrations.
10. Revise the concepts when real implementation experience shows they are unclear or unnecessary.

## 33. Questions for the next use cases

The following questions should be tested against the care use cases:

1. Does Service Journey remain useful for a single scheduled care visit?
2. Is Service Visit sufficient for describing entry, care delivery, and departure?
3. Does Item have a broader equivalent, or should it remain profile-specific?
4. How should professional roles and qualifications relate to Identity and Authority?
5. How should a replacement Service Agent be assigned?
6. How should resident consent or delegated approval be represented?
7. Is a care outcome represented by Completion, Evidence, or another concept?
8. How should private care notes be kept separate from Place-interaction Evidence?
9. How should main-residence access differ from access to an external Service Point?
10. How should urgent or emergency Authority differ from normal scheduled Authority?
11. Can Place Capability remain simple when the Capability is human-assisted access?
12. What minimum information must a care provider disclose to a Place?
13. What minimum information must a Place disclose to a care provider?

## 34. Initial conclusion

The first four use cases suggest that OSDI can begin with a small common model centred on:

* an intended service outcome;
* a coordinated Service Journey;
* one or more Place-specific Service Visits;
* identified organisations and agents;
* limited Authority;
* service-relevant Capabilities;
* clear Status;
* proportionate Evidence;
* explicit Completion or Exception.

This model remains intentionally simple.

The next use cases should test whether it can support scheduled care services without becoming biased towards logistics or requiring unnecessary complexity.
