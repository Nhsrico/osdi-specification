# UC001 — Item Delivery to a Secure Delivery Point

**Document status:** Informative working draft
**Specification version:** 0.1.0-draft
**Use-case identifier:** UC001

## 1. Purpose

This use case describes the delivery of an item to a secure delivery point at a Place.

The secure delivery point may be:

* a lockable parcel box;
* a secured delivery compartment;
* a gated delivery area;
* a managed reception point;
* another designated location that restricts unauthorised access.

The intended outcome is that an authorised delivery agent can reach the permitted delivery area, deposit the item, provide suitable evidence, and complete the delivery without receiving unnecessary access to the rest of the Place.

This use case is intended to preserve familiar delivery-provider processes such as job assignment, tracking references, arrival updates, proof of delivery, and exception reporting.

## 2. Example scenario

A resident orders an item from a retailer.

The retailer or delivery provider creates a delivery job using its existing systems. The delivery is associated with a Place that supports NHS365 services.

The Place has:

* an external gate;
* a secure parcel box located inside the gate;
* an external camera covering the delivery area;
* an access controller capable of validating temporary credentials;
* internet connectivity through which access authority may be checked.

The delivery agent arrives during the permitted delivery window.

The agent identifies the delivery job through the provider application or an NHS365 delivery-agent application. The Place verifies that the delivery job is valid and that the agent is currently assigned to it.

The agent is granted temporary access through the external gate and permission to open the parcel box.

The item is deposited, evidence is recorded, the parcel box is secured, and the delivery is marked complete.

The delivery agent is not authorised to enter the main residence.

## 3. Intended outcome

The use case is successfully completed when:

* the correct item is delivered to the correct Place;
* the item is deposited at an authorised delivery point;
* any required access is granted only for the necessary area and period;
* the delivery point and any access point are left secure;
* the delivery status is updated;
* required evidence is associated with the delivery;
* temporary authority is ended or revoked.

## 4. Participants

### 4.1 Service recipient

The person or organisation receiving the item.

The service recipient may be:

* the resident;
* another authorised user of the Place;
* a business;
* a care organisation;
* another party nominated to receive the item.

### 4.2 Requesting party

The party that initiated or arranged the delivery.

This may be:

* the service recipient;
* a retailer;
* a marketplace;
* another user;
* a service provider.

### 4.3 Delivery provider

The organisation responsible for transporting and delivering the item.

The delivery provider retains responsibility for its operational processes, including route planning, job allocation, driver management, and item tracking.

### 4.4 Delivery agent

The person or automated system assigned by the delivery provider to perform the delivery.

The delivery agent may be:

* a courier;
* a delivery driver;
* an authorised subcontractor;
* a delivery robot;
* another approved delivery mechanism.

The initial NHS365 implementation is expected to focus on a human delivery agent.

### 4.5 Place operator

The person or organisation responsible for managing service interaction at the Place.

The Place operator determines:

* which delivery locations may be used;
* which access actions may be granted;
* when human approval is required;
* what evidence may be captured;
* what delivery preferences and restrictions apply.

For a residential Place, the Place operator may be the resident or another authorised household member.

### 4.6 Place platform

The system responsible for exposing and coordinating the service capabilities available at the Place.

In the initial implementation, NHS365 may act as the Place platform.

### 4.7 Place systems

The local or connected systems that perform physical or supporting functions.

Examples include:

* gate controllers;
* access-control systems;
* parcel-box controllers;
* cameras;
* sensors;
* intercoms;
* Home Assistant;
* local edge agents;
* proprietary device platforms.

These implementation details should not normally be exposed directly to the delivery provider.

## 5. Assumptions and preconditions

Before the delivery begins:

* a delivery job exists;
* the delivery job contains a provider reference or tracking reference;
* the intended Place has been identified;
* the Place has been configured to accept secure deliveries;
* a permitted delivery point has been selected or can be selected at arrival;
* the delivery provider or delivery job can be recognised by the Place platform;
* the delivery occurs within an allowed period or can be approved as an exception;
* any required delivery instructions are available;
* the item is suitable for the selected delivery point;
* the delivery point is expected to have sufficient capacity;
* the Place operator has defined the permitted evidence policy.

The delivery provider is not required to understand the underlying devices or automation platform used at the Place.

## 6. Relevant Place areas

This use case may involve the following areas.

### 6.1 Public approach

The publicly accessible route leading towards the Place.

No OSDI-controlled access is normally required.

### 6.2 External gate or barrier

A controlled boundary that must be passed before reaching the delivery point.

The delivery agent may receive temporary authority to open the gate.

### 6.3 Delivery area

An external or semi-external area approved for receiving deliveries.

The delivery area should be clearly distinguishable from areas that the delivery agent is not authorised to enter.

### 6.4 Secure delivery point

The specific location where the item is to be deposited.

Examples include:

* a parcel box;
* a locked compartment;
* a delivery cabinet;
* a secure room;
* a reception locker;
* a controlled porch.

### 6.5 Main residence or restricted area

An area outside the authority granted for this use case.

Access to the main residence is not part of the normal journey.

## 7. Relevant Place capabilities

The Place may expose the following service-relevant capabilities.

### 7.1 Gate access

The ability to request or authorise opening of an external gate or barrier.

### 7.2 Secure delivery-point access

The ability to unlock, release, open, or otherwise make the secure delivery point available.

### 7.3 Availability status

The ability to indicate whether the delivery point:

* is operational;
* has capacity;
* is already open;
* is unavailable;
* requires resident intervention.

### 7.4 Access-state confirmation

The ability to confirm that a gate, door, or compartment:

* opened;
* closed;
* locked;
* failed to secure;
* remains open unexpectedly.

### 7.5 Notification

The ability to notify the Place operator or service recipient of:

* approaching delivery;
* delivery-agent arrival;
* access request;
* item deposit;
* completion;
* an exception requiring attention.

### 7.6 Communication

The ability to request assistance through:

* a doorbell;
* an intercom;
* a voice call;
* a message;
* another supported communication method.

### 7.7 Evidence capture

The ability to capture permitted evidence, such as:

* an image of the item at the delivery point;
* an image of the closed delivery compartment;
* a short video segment;
* the state of the delivery point before and after deposit;
* a sensor indication that an item is present.

### 7.8 Instructions

The ability to provide current delivery instructions, including:

* preferred delivery point;
* permitted route;
* gate instructions;
* parcel-box instructions;
* accessibility information;
* actions to take when the preferred delivery point is unavailable.

## 8. Information associated with the delivery

The delivery journey may use the following information:

* delivery identifier;
* provider tracking reference;
* delivery-provider identity;
* assigned delivery-agent identity or assignment reference;
* Place identifier;
* delivery-point identifier;
* scheduled or estimated time window;
* item size or category where relevant;
* handling requirements;
* delivery instructions;
* required evidence;
* current delivery status;
* completion time;
* exception reason;
* references to captured evidence.

The initial use case does not require OSDI to define the retailer's full order, payment, inventory, or route-planning data.

Only information necessary to coordinate the Place interaction should be exchanged.

## 9. Identity and authority

### 9.1 Delivery-provider recognition

The Place platform should be able to determine which delivery provider is responsible for the delivery.

This may be established through:

* an existing partner integration;
* a signed delivery-job assertion;
* a provider account;
* an NHS365-issued partner credential;
* another trusted association.

### 9.2 Delivery-agent recognition

The delivery agent should present sufficient information to associate the agent with the delivery job.

The initial implementation may use:

* agent login to a provider or NHS365 application;
* delivery-job barcode or QR code;
* temporary delivery token;
* provider-issued job credential;
* direct confirmation from the delivery provider.

The level of individual identity verification may vary by provider and risk.

For access to an external parcel box, confirmation that the agent is currently assigned to the valid delivery job may be sufficient.

### 9.3 Granted authority

The delivery agent may be authorised to:

* request access through a specified external gate;
* enter the designated delivery area;
* open the assigned secure delivery point;
* deposit the item;
* request approved evidence capture;
* close and secure the delivery point;
* report delivery status and exceptions.

The delivery agent should not normally be authorised to:

* enter the main residence;
* access unrelated delivery compartments;
* operate unrelated Place capabilities;
* view unrelated camera feeds;
* access previous delivery evidence;
* retain access after the delivery journey ends.

### 9.4 Authority duration

Authority should be limited by one or more of:

* delivery-job validity;
* assigned agent;
* Place;
* delivery point;
* permitted actions;
* start time;
* expiry time;
* completion of the delivery;
* revocation by the Place operator or delivery provider.

## 10. Normal journey

### Step 1 — Delivery job exists

The delivery provider creates or maintains the delivery job through its normal operational system.

The job includes a tracking reference, destination, assigned agent or route, and expected delivery status.

### Step 2 — Place interaction is prepared

Before arrival, the Place platform may determine:

* whether the Place is accepting deliveries;
* whether a suitable delivery point is available;
* whether the external gate and parcel box are operational;
* whether resident approval is required;
* what delivery instructions should be presented.

The delivery provider may receive a simplified indication that secure delivery is available.

### Step 3 — Agent approaches the Place

The delivery provider or agent application reports that the agent is approaching.

The Place platform may notify the service recipient or Place operator.

The arrival notification should not automatically grant access.

### Step 4 — Agent reports arrival

The delivery agent reports arrival using the provider application, NHS365 template application, or another recognised method.

The arrival report is associated with the delivery job and Place.

### Step 5 — Delivery job is validated

The Place platform checks that:

* the delivery job is recognised;
* the Place matches the intended destination;
* the job is active;
* the current time is acceptable;
* the presenting agent is associated with the job;
* the requested delivery point is permitted;
* the required capabilities are available.

### Step 6 — Instructions are presented

The agent receives current instructions, such as:

* use the side gate;
* proceed to parcel box 1;
* do not approach the main entrance;
* open the gate using the access request control;
* close the gate after entry;
* place the item inside the box;
* close the box and wait for confirmation.

Instructions should be brief and should not reveal unnecessary information about the Place.

### Step 7 — Gate access is requested

Where an external gate is present, the agent requests entry.

The Place platform verifies that gate access is within the granted authority.

The gate may be opened by:

* direct remote release;
* temporary code;
* digital credential;
* resident approval;
* local validation;
* another supported mechanism.

### Step 8 — Gate state is confirmed

Where supported, the Place platform records that the gate opened.

The agent enters the designated delivery area.

The Place may request or verify that the gate closes behind the agent.

### Step 9 — Secure delivery point is requested

The delivery agent requests access to the assigned parcel box or other secure delivery point.

The Place platform checks:

* that the correct delivery point was requested;
* that the job remains valid;
* that the delivery point is available;
* that it has not already been used for this delivery;
* that the agent remains authorised.

### Step 10 — Delivery point is opened

The Place platform causes or permits the secure delivery point to open.

The access event is recorded.

### Step 11 — Item is deposited

The agent deposits the item.

Where supported, the Place may detect item presence using:

* a door or lid sensor;
* a weight sensor;
* an occupancy sensor;
* camera analysis;
* agent confirmation.

The initial baseline should allow simple agent confirmation without requiring specialised sensors.

### Step 12 — Evidence is captured

Evidence is captured in accordance with the Place policy and delivery requirements.

Evidence may include:

* the provider's own proof-of-delivery image;
* a Place camera image;
* delivery-point state;
* item-presence confirmation;
* timestamp;
* agent confirmation.

The Place camera should not be treated as mandatory for a successful delivery unless the relevant service arrangement requires it.

### Step 13 — Delivery point is secured

The agent closes the parcel box or delivery compartment.

Where supported, the Place confirms that the delivery point has closed and locked.

If the compartment does not secure correctly, the journey moves to an exception state.

### Step 14 — Agent leaves the delivery area

The agent exits through the permitted route.

Where relevant, the Place confirms that the external gate has closed.

### Step 15 — Delivery is completed

The delivery agent or provider reports completion.

The completion record may contain:

* completion time;
* final status;
* delivery-point reference;
* evidence references;
* exception information;
* provider proof-of-delivery reference.

### Step 16 — Temporary authority ends

Access authority associated with the delivery is revoked or expires.

Subsequent attempts to use the delivery credential should be rejected unless a new authority is issued.

### Step 17 — Recipient is notified

The service recipient or Place operator receives a delivery-completion notification.

The notification may include:

* delivery status;
* delivery point;
* completion time;
* provider tracking reference;
* permitted evidence;
* instructions for retrieving the item.

## 11. Example status journey

A simple status sequence may be:

```text
Scheduled
    ↓
In Transit
    ↓
Approaching
    ↓
Arrived
    ↓
Access Authorised
    ↓
Delivery Point Open
    ↓
Item Deposited
    ↓
Delivery Point Secured
    ↓
Completed
```

Not every provider must use these exact status names.

The initial OSDI work should identify the minimum common statuses needed to exchange meaningful progress without replacing provider-specific tracking systems.

## 12. Alternative and exception journeys

### 12.1 Delivery point is full

If the assigned parcel box has insufficient capacity:

* the agent is informed that the delivery point is unavailable;
* an alternative permitted delivery point may be offered;
* the Place operator may be asked for approval;
* the provider may use its normal failed-delivery process;
* the delivery may be rescheduled.

The agent should not gain access to an alternative location unless specifically authorised.

### 12.2 Delivery point is offline

If the parcel box or controller is unavailable:

* the failure is reported;
* the agent may request assistance;
* resident approval may enable an alternative;
* the provider's normal exception process may be used.

A device failure should not result in broader access being granted automatically.

### 12.3 External gate cannot be opened

If the gate cannot be operated:

* the agent may retry within defined limits;
* the Place operator may be notified;
* an intercom or communication option may be offered;
* an alternative public delivery point may be selected;
* the delivery may fail or be rescheduled.

### 12.4 Credential is rejected

The credential may be rejected because:

* it is invalid;
* it has expired;
* it is for another Place;
* it is associated with another delivery;
* the agent is not currently assigned;
* it has already been used;
* the authority has been revoked.

The rejection should not reveal sensitive details about the Place or other deliveries.

### 12.5 Agent arrives outside the time window

The Place policy may:

* allow a limited grace period;
* request resident approval;
* issue revised temporary authority;
* reject the access request;
* direct the provider to reschedule.

### 12.6 Resident changes the delivery instruction

Before completion, the Place operator may:

* change the preferred delivery point;
* require attendance at the main entrance;
* withdraw permission for unattended delivery;
* cancel access authority.

Changes should be communicated clearly to the delivery agent and recorded.

### 12.7 Item requires a signature

Where a signature or direct handover is required, the secure delivery-point journey may not be sufficient.

The delivery agent may be directed to:

* contact the resident;
* use the main entrance without automated access;
* obtain another authorised recipient;
* follow the provider's normal failed-delivery procedure.

UC001 does not assume that secure unattended delivery satisfies every legal or contractual delivery requirement.

### 12.8 Item is unsuitable for the delivery point

The item may be:

* too large;
* too heavy;
* temperature-sensitive;
* hazardous;
* age-restricted;
* damaged;
* otherwise unsuitable.

The secure delivery point should not be used when the item's requirements cannot be satisfied.

### 12.9 Delivery point fails to secure

If the parcel box remains open or unlocked:

* completion should be delayed;
* the agent should be asked to retry closure;
* the Place operator should be notified;
* the item may need to be removed;
* another delivery point may be selected;
* the event should be recorded as an exception.

### 12.10 Evidence capture fails

If optional evidence capture fails, the delivery may still complete using provider evidence or agent confirmation.

If evidence is contractually required:

* another permitted evidence method should be attempted;
* the Place operator or provider may approve completion;
* the delivery may be recorded as completed with an evidence exception;
* the provider may determine that completion is not permitted.

### 12.11 Network connection is unavailable

Where internet-based validation is unavailable, the Place may support:

* a previously issued short-lived credential;
* a locally verifiable signed credential;
* resident-controlled access;
* no access until connectivity is restored.

Offline access should be explicitly supported by the Place policy. It should not be assumed.

### 12.12 Suspected misuse or security concern

If the Place detects unexpected behaviour:

* further access may be denied;
* existing authority may be revoked;
* the Place operator may be alerted;
* an audit event may be recorded;
* the delivery provider may be notified;
* normal Place security procedures may be activated.

## 13. Evidence and completion

A completion record should be sufficient to answer:

* which delivery was performed;
* which provider performed it;
* when it occurred;
* which Place and delivery point were used;
* whether access was granted;
* whether the delivery point was secured;
* what completion status was reported;
* what evidence is available;
* whether exceptions occurred.

Potential evidence includes:

* provider proof-of-delivery reference;
* agent-captured photograph;
* Place-camera image;
* delivery-point open and close events;
* lock-state confirmation;
* item-presence indication;
* timestamp;
* resident approval;
* agent completion declaration.

Evidence should be retained and disclosed according to the applicable privacy, contractual, and Place policies.

## 14. Privacy considerations

The use case should minimise disclosure of:

* resident identity;
* resident presence or absence;
* internal Place layout;
* unrelated camera footage;
* unrelated access points;
* other deliveries;
* household routines;
* detailed security configuration.

The delivery agent should receive only the information required to complete the delivery.

Camera access should normally be limited to event-specific evidence. The agent should not receive unrestricted live or historical camera access solely because a camera supports the delivery journey.

## 15. Security considerations

The implementation should guard against:

* reuse of delivery credentials;
* presentation of credentials at the wrong Place;
* access outside the permitted period;
* access to an incorrect delivery point;
* impersonation of a delivery agent;
* fraudulent delivery-job creation;
* unauthorised expansion of access;
* continued access after completion;
* disclosure of sensitive Place capabilities;
* manipulation or substitution of evidence;
* repeated automated access attempts.

Access authority should be limited, short-lived, and associated with a specific service journey wherever practical.

## 16. Current-practice alignment

This use case is intended to extend rather than replace existing delivery-provider practices.

A delivery provider may continue to manage:

* customer orders;
* item tracking;
* routing;
* agent assignment;
* estimated arrival;
* proof of delivery;
* failed-delivery procedures;
* customer support.

The OSDI or NHS365 role may initially be limited to:

* recognising the delivery job;
* exposing the permitted delivery location;
* providing current Place instructions;
* granting temporary Place access;
* supporting evidence;
* exchanging relevant status;
* notifying the recipient.

This allows an early service provider to adopt secure Place interaction without replacing its existing logistics platform.

## 17. Common OSDI needs identified

UC001 suggests the need for the following common concepts:

* service job or service request;
* requesting party;
* service provider;
* assigned service agent;
* Place;
* service location or delivery point;
* scheduled or permitted time window;
* service instructions;
* Place capability;
* capability availability;
* credential;
* authority;
* access action;
* status update;
* evidence;
* completion;
* exception;
* authority expiry or revocation.

These concepts remain provisional until compared with other use cases.

## 18. Proposed NHS365 starter implementation

An initial NHS365 demonstration may include:

### 18.1 Resident application

The resident application may allow the user to:

* enable secure delivery for the Place;
* select a preferred delivery point;
* define permitted delivery hours;
* select evidence preferences;
* receive arrival and completion notifications;
* approve exceptions;
* view the delivery record.

### 18.2 Delivery-agent application template

The delivery-agent application may provide:

* agent authentication;
* assigned delivery reference entry or scanning;
* arrival reporting;
* current Place instructions;
* gate access request;
* parcel-box access request;
* delivery confirmation;
* evidence submission;
* exception reporting;
* completion status.

### 18.3 NHS365 platform services

The platform may provide:

* delivery-job association;
* Place lookup;
* authority generation;
* temporary credential validation;
* capability discovery;
* status processing;
* notification;
* evidence association;
* audit recording.

### 18.4 NHS365 site agent

The site agent may:

* communicate with the local Place platform;
* map OSDI-style capability requests to local systems;
* operate a gate or parcel box;
* request camera evidence;
* report capability state;
* return success or failure results.

### 18.5 Home Assistant adapter

Where Home Assistant is used, the NHS365 adapter may map:

* an external gate to a cover, lock, or other suitable entity;
* a parcel box to a lock and open/closed sensor;
* a delivery-area camera to a camera entity;
* an intercom or notification action to an appropriate Home Assistant service;
* capability state to normalised NHS365 results.

Home Assistant entity identifiers remain internal to the NHS365 implementation and are not exposed as OSDI concepts.

## 19. Questions for refinement

The following questions should be considered during future iterations:

1. How is the delivery job first associated with the Place?
2. Must the individual delivery agent always be identified, or is provider-confirmed job possession sufficient for low-risk delivery points?
3. Should a delivery credential be issued before arrival or generated at the Place?
4. What is the minimum useful common delivery-status model?
5. How should offline credential verification work?
6. Should the Place be able to select a different delivery point dynamically?
7. Who owns evidence captured using Place cameras?
8. How should the provider obtain evidence without learning unnecessary Place details?
9. What happens when provider proof and Place evidence disagree?
10. How should multiple items or multiple delivery agents be handled?
11. Should a parcel box support reservation before arrival?
12. What information about parcel dimensions is needed to prevent failed delivery?
13. How should shared apartment or multi-occupancy Places be represented?
14. How should a delivery be cancelled after temporary authority has already been issued?
15. Which parts of the journey belong in OSDI Core and which belong in a parcel-delivery profile?

## 20. Initial conclusion

UC001 demonstrates that secure item delivery can be supported without exposing the internal technology or full security configuration of a Place.

The delivery provider needs a small set of outcomes:

* recognise the delivery;
* identify the permitted delivery point;
* receive instructions;
* obtain limited temporary access;
* deposit the item;
* record evidence;
* report completion or failure.

The Place retains control over how those outcomes are implemented and which physical capabilities are made available.

This separation between service intent and Place implementation is a candidate foundation for the broader OSDI approach.
