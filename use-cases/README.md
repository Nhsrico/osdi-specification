# OSDI Use Cases

**Document status:** Informative working draft
**Specification version:** 0.1.0-draft

## 1. Purpose

The OSDI use cases describe practical service journeys involving service providers, service agents, users and compatible Places.

They are intended to:

* identify common requirements across different service domains;
* guide the development of the OSDI core concepts;
* validate that proposed abstractions support real service journeys;
* guide the development of NHS365 demonstrations and application templates;
* minimise unnecessary differences from current service-provider practices.

The use cases are informative. They do not independently establish normative OSDI requirements.

## 2. Use-case-led development

The first OSDI baseline will be developed from practical use cases rather than from a predetermined abstract model.

For each use case, the project will identify:

* the parties involved;
* the intended service outcome;
* the information that must be exchanged;
* the Place capabilities required;
* the authority granted to each party;
* the events and status changes that matter;
* the evidence required to confirm completion;
* the failure and exception paths that must be supported.

Requirements that recur across several use cases may become part of the OSDI core specification.

Requirements that apply only to a particular service domain should normally be defined in a service profile rather than in OSDI Core.

## 3. Initial service domains

The initial use cases focus on two service domains.

### 3.1 Item movement

Item-movement journeys include:

* delivering an item to a Place;
* collecting an item from a Place;
* returning an item;
* collecting shopping or other goods and delivering them to a Place;
* transferring an item between users;
* exchanging one item for another.

### 3.2 Care services

Care-service journeys include:

* a scheduled care visit;
* a replacement care worker attending a scheduled visit;
* an unplanned but authorised care visit;
* access escalation when the resident cannot respond;
* urgent or emergency access under defined authority.

These domains have different risk levels but share common needs relating to identity, scheduling, Place interaction, access, status, evidence and completion.

## 4. Place interaction model

A Place is treated as a managed physical location at which a service may be performed.

A Place may contain one or more service-relevant areas, including:

* an external approach;
* an external gate or barrier;
* a driveway, path or shared entrance;
* an external delivery area;
* a secure delivery or collection box;
* a main building entrance;
* shared internal areas;
* restricted internal areas;
* a designated care or service area.

A service journey may require access to only one of these areas.

For example:

* a parcel courier may be authorised to open an external gate and a delivery box;
* a collection agent may be authorised to retrieve a prepared item from a collection box;
* a care worker may be authorised to enter through the main residence entrance;
* a maintenance engineer may be authorised to enter a plant room but not the residence;
* an emergency responder may receive broader access under an emergency policy.

OSDI should allow a Place to expose service-relevant capabilities without exposing unnecessary details of the underlying equipment or property layout.

## 5. Initial Place capabilities

The initial use cases may involve the following capabilities.

### 5.1 Access capabilities

* request opening of an external gate;
* request access through a main entrance;
* validate a temporary code or digital credential;
* request approval from a resident or authorised representative;
* release a secure delivery or collection compartment;
* confirm that an access point has closed or secured;
* revoke access when a service interaction ends.

### 5.2 Communication capabilities

* operate a doorbell;
* initiate an intercom call;
* send a resident notification;
* request remote approval;
* provide service instructions to the service agent;
* provide accessible communication options where supported.

### 5.3 Evidence capabilities

* capture an authorised image;
* capture an authorised video segment;
* record access-point state changes;
* record delivery-box state changes;
* record item presence or removal where supported;
* associate evidence with the relevant service journey.

### 5.4 Status capabilities

* indicate whether an access point is available;
* indicate whether a delivery box has capacity;
* indicate whether a capability is unavailable or degraded;
* indicate whether human approval is required;
* indicate whether the Place can currently support the requested service outcome.

The initial specification does not require any particular implementation technology for these capabilities.

## 6. Identity, credentials and authority

The use cases distinguish between identity, credentials, authority and access method.

### 6.1 Identity

Identity describes the person, organisation, automated agent or other party participating in the service journey.

### 6.2 Credential

A credential provides evidence supporting an identity, role, assignment or other claim.

Examples include:

* a service-provider-issued job credential;
* a verified care-worker identity;
* an employer assertion;
* a temporary access code;
* a signed digital credential;
* a resident approval.

### 6.3 Authority

Authority describes what a participant is permitted to do for a particular service journey, at a particular Place, during a defined period or under defined conditions.

Authority should be limited to the actions needed to achieve the service outcome.

### 6.4 Access method

The access method is the mechanism used to carry out an authorised action.

Examples include:

* remote release;
* temporary PIN;
* digitally presented credential;
* resident-operated control;
* service-provider application;
* locally verified identity;
* internet-connected credential validation.

OSDI should define the requested outcome and associated authority without requiring a single access method.

## 7. Cameras and evidence

A Place may use cameras or other sensors to support evidence, safety and audit.

The presence of a camera does not imply unrestricted access to images or video.

Each use case should identify:

* whether evidence is required;
* who may request it;
* what may be captured;
* when capture may occur;
* how the evidence is associated with the service journey;
* who may access it;
* how long it should be retained;
* what happens if evidence capture is unavailable.

Evidence should be proportionate to the service and should not expose unrelated activity or private areas unnecessarily.

## 8. Current-practice alignment

OSDI should minimise disruption to established service-provider procedures.

Where possible, OSDI should extend familiar concepts such as:

* service bookings;
* delivery or collection references;
* assigned agents;
* scheduled time windows;
* status updates;
* arrival notifications;
* proof of delivery;
* proof of collection;
* visit records;
* completion and exception codes.

Early integrations should allow providers to retain their existing operational systems while using OSDI or NHS365 for Place interaction, access, notification, evidence and status exchange.

## 9. NHS365 starter implementations

NHS365 may provide application templates for early service providers.

Initial templates may include:

* delivery-agent application;
* collection-agent application;
* shopping collection and delivery application;
* return collection application;
* user item-exchange application;
* care-provider application;
* care-worker application.

A template may provide:

* authentication;
* assigned service jobs;
* navigation to the relevant Place;
* arrival reporting;
* access requests;
* Place instructions;
* status updates;
* evidence capture;
* exception reporting;
* completion confirmation.

These templates are NHS365 implementation assets and are not normative parts of OSDI.

They will, however, provide practical validation of the OSDI use cases and may serve as reference examples for partner implementations.

## 10. Use-case document structure

Each use case should contain:

1. purpose and intended outcome;
2. participants;
3. assumptions and preconditions;
4. relevant Place areas and capabilities;
5. normal journey;
6. alternative and exception journeys;
7. information exchanged;
8. identity and authority requirements;
9. privacy and security considerations;
10. evidence and completion requirements;
11. common OSDI needs identified;
12. proposed NHS365 starter implementation.

## 11. Initial use-case catalogue

The initial catalogue is:

* UC001 — Item delivery to a secure delivery point;
* UC002 — Item collection from a Place;
* UC003 — Return collection;
* UC004 — Shopping collection and delivery;
* UC005 — User-to-user item transfer;
* UC006 — Item exchange;
* UC007 — Scheduled care visit;
* UC008 — Replacement care worker visit;
* UC009 — Unplanned authorised care visit;
* UC010 — Urgent or emergency access.

This catalogue may change as the journeys are refined.

## 12. Expected outcome

The use-case work should produce a small and understandable set of common requirements.

The likely common denominators include:

* a service request or booking;
* an identified requesting party;
* an identified service provider;
* an assigned service agent;
* a Place;
* an intended service outcome;
* a time window;
* relevant Place capabilities;
* limited authority;
* status updates;
* instructions;
* evidence;
* completion or exception reporting.

These concepts are provisional. They should become part of the OSDI core model only after being validated across several use cases.
