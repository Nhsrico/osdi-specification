# UC002 — Item Collection from a Place

**Document status:** Informative working draft
**Specification version:** 0.1.0-draft
**Use-case identifier:** UC002

## 1. Purpose

This use case describes the collection of an item from a Place by an authorised collection agent.

The item may be collected from:

* a secure parcel or collection box;
* a lockable external compartment;
* a gated collection area;
* a managed reception point;
* another designated location that restricts unauthorised access.

The intended outcome is that the correct authorised agent can reach the permitted collection area, retrieve the correct item, provide appropriate evidence, and complete the collection without receiving unnecessary access to the rest of the Place.

This use case may support:

* courier collection of an outbound parcel;
* collection of a returned item;
* collection of goods being sent to another user;
* collection of equipment for repair;
* collection of documents, samples, or other prepared items;
* scheduled service-provider pickup.

The use case is intended to preserve familiar collection-provider practices such as booking references, labels, tracking references, scheduled collection windows, status updates, and exception reporting.

## 2. Example scenario

A resident wants to send a parcel.

The resident arranges a collection through a courier, retailer, marketplace, or NHS365-supported service.

The Place has:

* an external gate;
* a secure collection box inside the gate;
* a camera covering the collection area;
* an access controller capable of validating temporary credentials;
* internet connectivity through which collection authority may be checked.

Before the collection window, the resident places the parcel in the designated collection box and confirms that the item is ready.

The courier assigns a collection agent.

The agent arrives during the permitted collection window and presents the collection reference using the provider application or an NHS365 collection-agent application.

The Place verifies that:

* the collection job is valid;
* the agent is associated with the job;
* the item has been declared ready;
* the collection point is available;
* the collection remains authorised.

The agent is granted temporary access through the external gate and permission to open the assigned collection box.

The correct item is removed, evidence is recorded, the collection box is secured, and the collection is marked complete.

The collection agent is not authorised to enter the main residence.

## 3. Intended outcome

The use case is successfully completed when:

* the correct item is collected from the correct Place;
* the item is retrieved from an authorised collection point;
* collection occurs during an authorised period or approved exception;
* access is granted only for the necessary area, action, and duration;
* the collection point and any access point are left secure;
* custody of the item is transferred to the collection provider or agent;
* the collection status is updated;
* required evidence is associated with the collection;
* temporary authority is ended or revoked.

## 4. Participants

### 4.1 Service sender

The person or organisation providing the item for collection.

The service sender may be:

* a resident;
* another authorised user of the Place;
* a business;
* a care organisation;
* a service provider;
* another party authorised to release the item.

### 4.2 Requesting party

The party that initiated or arranged the collection.

This may be:

* the service sender;
* the intended recipient;
* a retailer;
* a marketplace;
* a delivery provider;
* a returns provider;
* another service organisation.

The requesting party and service sender may be the same party, but this is not required.

### 4.3 Collection provider

The organisation responsible for collecting and transporting the item.

The collection provider retains responsibility for its operational processes, including:

* collection booking;
* route planning;
* job allocation;
* agent management;
* shipping-label requirements;
* item tracking;
* onward transportation.

### 4.4 Collection agent

The person or automated system assigned by the collection provider to perform the collection.

The collection agent may be:

* a courier;
* a delivery driver;
* an authorised subcontractor;
* a collection robot;
* another approved collection mechanism.

The initial NHS365 implementation is expected to focus on a human collection agent.

### 4.5 Intended recipient

The person or organisation intended to receive the item after collection.

The intended recipient may not interact directly with the Place.

The initial OSDI interaction should not require disclosure of unnecessary recipient information to the Place platform.

### 4.6 Place operator

The person or organisation responsible for managing service interaction at the Place.

The Place operator determines:

* which collection locations may be used;
* who may prepare or release an item;
* which access actions may be granted;
* when human approval is required;
* what evidence may be captured;
* what collection restrictions apply.

For a residential Place, the Place operator may be the resident or another authorised household member.

### 4.7 Place platform

The system responsible for exposing and coordinating the service capabilities available at the Place.

In the initial implementation, NHS365 may act as the Place platform.

### 4.8 Place systems

The local or connected systems that perform physical or supporting functions.

Examples include:

* gate controllers;
* access-control systems;
* secure collection-box controllers;
* cameras;
* weight or presence sensors;
* door or lid sensors;
* intercoms;
* Home Assistant;
* local edge agents;
* proprietary device platforms.

These implementation details should not normally be exposed directly to the collection provider.

## 5. Assumptions and preconditions

Before collection begins:

* a collection job exists;
* the collection job contains a provider reference or collection reference;
* the intended Place has been identified;
* the Place has been configured to support secure collections;
* an authorised collection point has been selected;
* the item has been prepared;
* the item has been placed at the authorised collection point, or will be placed there before collection;
* the item is identified sufficiently to avoid accidental collection of another item;
* the service sender or Place operator has confirmed that the item is ready;
* the collection provider or collection job can be recognised by the Place platform;
* the collection occurs within an allowed period or can be approved as an exception;
* any required collection instructions are available;
* the item is suitable for the selected collection point;
* the Place operator has defined the permitted evidence policy.

The collection provider is not required to understand the underlying devices or automation platform used at the Place.

## 6. Item preparation

Collection differs from delivery because the Place or service sender must prepare an item for release.

Before an item becomes available for collection, the service sender may need to:

* package the item;
* attach a shipping label;
* obtain a collection reference;
* place the item in the correct collection point;
* declare the item ready;
* identify any handling requirements;
* confirm that the item matches the collection booking;
* close and secure the collection point.

The collection should not normally be authorised until the item has been marked ready.

A Place may support preparation through:

* manual confirmation by the service sender;
* scanning a label or barcode;
* entering a collection reference;
* detecting item presence;
* detecting compartment closure;
* another supported method.

The initial baseline should allow simple manual confirmation without requiring specialised sensors.

## 7. Relevant Place areas

This use case may involve the following areas.

### 7.1 Public approach

The publicly accessible route leading towards the Place.

No OSDI-controlled access is normally required.

### 7.2 External gate or barrier

A controlled boundary that must be passed before reaching the collection point.

The collection agent may receive temporary authority to open the gate.

### 7.3 Collection area

An external or semi-external area approved for item collection.

The collection area should be clearly distinguishable from areas that the collection agent is not authorised to enter.

### 7.4 Secure collection point

The specific location from which the item is to be retrieved.

Examples include:

* a parcel box;
* a locked compartment;
* a collection cabinet;
* a secure room;
* a reception locker;
* a controlled porch.

### 7.5 Main residence or restricted area

An area outside the authority granted for this use case.

Access to the main residence is not part of the normal journey.

## 8. Relevant Place capabilities

The Place may expose the following service-relevant capabilities.

### 8.1 Gate access

The ability to request or authorise opening of an external gate or barrier.

### 8.2 Secure collection-point access

The ability to unlock, release, open, or otherwise make the collection point available.

### 8.3 Item-ready status

The ability to indicate whether the item:

* has been prepared;
* has been placed in the collection point;
* is ready for release;
* has already been collected;
* is no longer available;
* requires service-sender intervention.

### 8.4 Availability status

The ability to indicate whether the collection point:

* is operational;
* is accessible;
* is already open;
* is unavailable;
* requires resident intervention.

### 8.5 Item identification

The ability to help distinguish the intended collection item from another item.

This may use:

* collection reference;
* shipping label;
* barcode or QR code;
* compartment assignment;
* item description;
* sender confirmation;
* another supported identifier.

OSDI should avoid requiring the Place to hold the provider's complete order or shipping record.

### 8.6 Access-state confirmation

The ability to confirm that a gate, door, or compartment:

* opened;
* closed;
* locked;
* failed to secure;
* remains open unexpectedly.

### 8.7 Item-presence confirmation

Where supported, the ability to indicate that:

* an item was present before collection;
* an item was removed;
* the collection point is now empty;
* an unexpected item remains.

The initial baseline should not make item sensors mandatory.

### 8.8 Notification

The ability to notify the Place operator or service sender of:

* approaching collection;
* collection-agent arrival;
* access request;
* item removal;
* completion;
* an exception requiring attention.

### 8.9 Communication

The ability to request assistance through:

* a doorbell;
* an intercom;
* a voice call;
* a message;
* another supported communication method.

### 8.10 Evidence capture

The ability to capture permitted evidence, such as:

* an image of the item before removal;
* an image of the collection agent taking possession;
* an image of the closed collection compartment;
* a short video segment;
* collection-point state before and after removal;
* a sensor indication that the item was removed.

### 8.11 Instructions

The ability to provide current collection instructions, including:

* permitted route;
* gate instructions;
* assigned collection point;
* item identification guidance;
* actions to take if the item is missing;
* actions to take if the item appears damaged;
* actions to take if the collection point contains multiple items.

## 9. Information associated with the collection

The collection journey may use the following information:

* collection identifier;
* provider collection reference;
* shipment or return reference;
* collection-provider identity;
* assigned collection-agent identity or assignment reference;
* Place identifier;
* collection-point identifier;
* scheduled or permitted time window;
* item reference;
* shipping-label status;
* item-ready status;
* item size or category where relevant;
* handling requirements;
* collection instructions;
* required evidence;
* current collection status;
* completion time;
* exception reason;
* references to captured evidence;
* onward tracking reference where available.

The initial use case does not require OSDI to define:

* payment;
* product inventory;
* route planning;
* retailer order details;
* customs data;
* the full shipping-label format;
* the complete onward logistics process.

Only information necessary to coordinate the Place interaction and confirm transfer of custody should be exchanged.

## 10. Identity and authority

### 10.1 Collection-provider recognition

The Place platform should be able to determine which collection provider is responsible for the collection.

This may be established through:

* an existing partner integration;
* a signed collection-job assertion;
* a provider account;
* an NHS365-issued partner credential;
* another trusted association.

### 10.2 Collection-agent recognition

The collection agent should present sufficient information to associate the agent with the collection job.

The initial implementation may use:

* agent login to a provider or NHS365 application;
* collection-job barcode or QR code;
* temporary collection token;
* provider-issued job credential;
* direct confirmation from the collection provider.

For low-risk external collection points, confirmation that the agent is currently assigned to a valid collection job may be sufficient.

Higher-value or sensitive collections may require stronger individual identity verification.

### 10.3 Service-sender authority

The service sender or Place operator should have authority to release the item.

This is important where:

* the requesting party is not the Place operator;
* multiple users share a Place;
* the item belongs to another user;
* the item is valuable or sensitive;
* the item is part of an exchange;
* the collection was arranged by a retailer or third party.

The collection job should not by itself prove that the item may be released unless the Place has accepted or confirmed the collection arrangement.

### 10.4 Granted collection-agent authority

The collection agent may be authorised to:

* request access through a specified external gate;
* enter the designated collection area;
* open the assigned secure collection point;
* identify the intended item;
* remove the authorised item;
* request approved evidence capture;
* close and secure the collection point;
* report collection status and exceptions.

The collection agent should not normally be authorised to:

* enter the main residence;
* access unrelated collection compartments;
* remove another item;
* operate unrelated Place capabilities;
* view unrelated camera feeds;
* access previous collection evidence;
* retain access after the collection journey ends.

### 10.5 Authority duration

Authority should be limited by one or more of:

* collection-job validity;
* item-ready status;
* assigned agent;
* Place;
* collection point;
* item reference;
* permitted actions;
* start time;
* expiry time;
* successful item removal;
* completion of the collection;
* revocation by the Place operator, service sender, or collection provider.

## 11. Normal journey

### Step 1 — Collection is arranged

The service sender, recipient, retailer, or other requesting party arranges the collection.

The collection provider creates or maintains the collection job through its normal operational system.

The job includes a collection reference, Place, expected collection window, and any shipping-label or packaging requirements.

### Step 2 — Collection is accepted by the Place

The Place operator or authorised service sender accepts the collection arrangement.

Acceptance may occur:

* automatically under a standing preference;
* through the NHS365 application;
* through a partner integration;
* when the collection reference is entered;
* when the shipping label is scanned;
* through another supported method.

Acceptance associates the collection job with the Place and identifies the permitted collection point.

### Step 3 — Item is prepared

The service sender packages and labels the item as required.

The item is checked against the collection instructions.

Where the provider does not require a pre-printed label, the item may instead use:

* a digital reference;
* a provider-generated code;
* agent-applied labelling;
* another recognised procedure.

### Step 4 — Item is placed at the collection point

The service sender places the item in the designated collection box or area.

Where supported, the Place may record:

* collection-point opening;
* item placement;
* item-presence status;
* collection-point closure;
* lock status.

### Step 5 — Item is declared ready

The service sender or Place operator confirms that the item is ready for collection.

The ready declaration may include:

* collection reference;
* collection-point identifier;
* item reference;
* placement time;
* handling instructions;
* optional evidence;
* expiry time.

The item should not normally be released before it has been declared ready.

### Step 6 — Place interaction is prepared

Before arrival, the Place platform may determine:

* whether the collection remains authorised;
* whether the item is ready;
* whether the collection point is operational;
* whether the external gate is operational;
* whether the collection time remains valid;
* whether resident approval is required;
* what collection instructions should be presented.

The collection provider may receive a simplified indication that the item is ready.

### Step 7 — Agent approaches the Place

The collection provider or agent application reports that the agent is approaching.

The Place platform may notify the service sender or Place operator.

The approaching status should not automatically grant access.

### Step 8 — Agent reports arrival

The collection agent reports arrival using the provider application, NHS365 application template, or another recognised method.

The arrival report is associated with the collection job and Place.

### Step 9 — Collection job is validated

The Place platform checks that:

* the collection job is recognised;
* the Place matches the intended collection location;
* the job is active;
* the current time is acceptable;
* the presenting agent is associated with the job;
* the item has been declared ready;
* the requested collection point is permitted;
* the required capabilities are available;
* the collection has not already been completed or cancelled.

### Step 10 — Instructions are presented

The agent receives current instructions, such as:

* use the side gate;
* proceed to collection box 1;
* do not approach the main entrance;
* confirm the parcel label before removing the item;
* remove only the parcel associated with the current collection;
* close the box and wait for confirmation.

Instructions should be brief and should not reveal unnecessary information about the Place or other items.

### Step 11 — Gate access is requested

Where an external gate is present, the agent requests entry.

The Place platform verifies that gate access is within the granted authority.

The gate may be opened by:

* direct remote release;
* temporary code;
* digital credential;
* resident approval;
* local validation;
* another supported mechanism.

### Step 12 — Gate state is confirmed

Where supported, the Place platform records that the gate opened.

The agent enters the designated collection area.

The Place may request or verify that the gate closes behind the agent.

### Step 13 — Secure collection point is requested

The collection agent requests access to the assigned collection box or other secure collection point.

The Place platform checks:

* that the correct collection point was requested;
* that the job remains valid;
* that the item remains ready;
* that the collection point is available;
* that the item has not already been collected;
* that the agent remains authorised.

### Step 14 — Collection point is opened

The Place platform causes or permits the secure collection point to open.

The access event is recorded.

### Step 15 — Agent identifies the item

The collection agent confirms that the item corresponds to the collection job.

This may involve:

* scanning the label;
* matching the collection reference;
* matching the assigned compartment;
* reading an item identifier;
* confirming a simple description;
* another supported check.

The agent should not remove an item that cannot reasonably be associated with the active collection job.

### Step 16 — Item is removed

The collection agent removes the item.

Where supported, the Place may detect item removal using:

* a weight sensor;
* an occupancy sensor;
* camera analysis;
* collection-point state;
* agent confirmation.

The initial baseline should allow simple agent confirmation without requiring specialised sensors.

### Step 17 — Custody is accepted

The collection agent confirms possession of the item.

This represents transfer of operational custody from the service sender or Place to the collection provider.

The exact legal meaning of custody transfer remains subject to the applicable provider terms and service arrangement.

### Step 18 — Evidence is captured

Evidence is captured in accordance with the Place policy and collection requirements.

Evidence may include:

* provider collection confirmation;
* agent-captured image;
* Place-camera image;
* collection-point state;
* item-removal confirmation;
* label scan;
* timestamp;
* service-sender preparation evidence.

Place-camera evidence should not be mandatory unless required by the relevant arrangement.

### Step 19 — Collection point is secured

The agent closes the collection box or compartment.

Where supported, the Place confirms that the collection point has closed and locked.

If it does not secure correctly, the journey moves to an exception state.

### Step 20 — Agent leaves the collection area

The agent exits through the permitted route.

Where relevant, the Place confirms that the external gate has closed.

### Step 21 — Collection is completed

The collection agent or provider reports completion.

The completion record may contain:

* completion time;
* final status;
* collection-point reference;
* item reference;
* evidence references;
* exception information;
* provider collection confirmation;
* onward tracking reference.

### Step 22 — Temporary authority ends

Access authority associated with the collection is revoked or expires.

Subsequent attempts to use the collection credential should be rejected unless new authority is issued.

### Step 23 — Parties are notified

The service sender, Place operator, requesting party, or intended recipient may receive a collection-completion notification.

The notification may include:

* collection status;
* collection time;
* provider reference;
* onward tracking information;
* permitted evidence;
* exception information.

## 12. Example status journey

A simple collection-status sequence may be:

```text
Arranged
    ↓
Accepted by Place
    ↓
Item Preparing
    ↓
Ready for Collection
    ↓
Agent Approaching
    ↓
Agent Arrived
    ↓
Access Authorised
    ↓
Collection Point Open
    ↓
Item Collected
    ↓
Collection Point Secured
    ↓
Completed
```

Not every provider must use these exact status names.

OSDI should identify the minimum common statuses required to exchange meaningful progress without replacing provider-specific logistics systems.

## 13. Alternative and exception journeys

### 13.1 Item is not ready

If the agent arrives before the item has been declared ready:

* access to the collection point should normally be denied;
* the service sender may be notified;
* the agent may wait within provider rules;
* the provider may reschedule;
* the collection may fail.

A valid collection booking should not automatically prove that an item is ready for release.

### 13.2 Item is missing

If the assigned collection point is empty:

* the agent reports that the item is missing;
* the Place operator or service sender may be notified;
* available evidence may be reviewed;
* the agent should not search unrelated areas;
* the collection may be marked failed or rescheduled.

### 13.3 Incorrect item is present

If the item does not match the collection job:

* the agent should not remove it;
* the mismatch should be reported;
* the service sender may be contacted;
* the collection may be corrected, rescheduled, or cancelled;
* the event should be recorded.

### 13.4 Multiple items are present

If multiple items are present in the collection point:

* the instructions should identify the authorised item;
* the agent may scan or verify the intended item;
* unrelated items must remain in place;
* the agent should request assistance if the item cannot be distinguished safely.

### 13.5 Shipping label is missing or invalid

The provider's existing process may allow:

* agent-applied labelling;
* use of a digital collection code;
* service-sender correction;
* collection with a documented exception;
* refusal or rescheduling.

OSDI should support the exchange of status and instructions but should not define the complete provider shipping-label process.

### 13.6 Collection point is offline

If the collection box or controller is unavailable:

* the failure is reported;
* the agent may request assistance;
* resident approval may enable an alternative;
* the provider's normal exception process may be used.

Device failure should not result in broader access being granted automatically.

### 13.7 External gate cannot be opened

If the gate cannot be operated:

* the agent may retry within defined limits;
* the Place operator may be notified;
* a communication option may be offered;
* an alternative public handover may be arranged;
* the collection may fail or be rescheduled.

### 13.8 Credential is rejected

The credential may be rejected because:

* it is invalid;
* it has expired;
* it is for another Place;
* it is associated with another collection;
* the agent is not currently assigned;
* it has already been used;
* the authority has been revoked.

The rejection should not reveal sensitive information about the Place or item.

### 13.9 Agent arrives outside the time window

The Place policy may:

* allow a limited grace period;
* request service-sender approval;
* issue revised temporary authority;
* reject the access request;
* direct the provider to reschedule.

### 13.10 Collection is cancelled after preparation

If the collection is cancelled after the item has been placed in the collection point:

* collection authority should be revoked;
* the collection provider should be notified;
* the service sender should be instructed to retrieve or reassign the item;
* any issued credential should become unusable;
* the cancellation should be recorded.

### 13.11 Item appears damaged or unsafe

If the item appears damaged, leaking, hazardous, insecurely packaged, or otherwise unsuitable:

* the agent may refuse collection;
* evidence may be captured where permitted;
* the service sender should be notified;
* the item should remain at the Place unless provider procedures say otherwise;
* the collection should be recorded as failed or exceptional.

### 13.12 Item exceeds declared size or weight

If the item cannot be transported under the collection arrangement:

* the agent may reject it;
* a different service may be requested;
* the collection may be rescheduled;
* the mismatch should be recorded.

### 13.13 Collection point fails to secure

If the collection box remains open or unlocked:

* completion should be delayed;
* the agent should be asked to retry closure;
* the Place operator should be notified;
* unrelated items may require protection;
* the event should be recorded as an exception.

### 13.14 Evidence capture fails

If optional evidence capture fails, the collection may still complete using provider confirmation or agent declaration.

If evidence is contractually required:

* another permitted evidence method should be attempted;
* the Place operator or provider may approve completion;
* the collection may be recorded with an evidence exception;
* the provider may determine that completion is not permitted.

### 13.15 Network connection is unavailable

Where internet-based validation is unavailable, the Place may support:

* a previously issued short-lived credential;
* a locally verifiable signed credential;
* resident-controlled access;
* no access until connectivity is restored.

Offline access should be explicitly supported by Place policy.

### 13.16 Suspected misuse or security concern

If the Place detects unexpected behaviour:

* further access may be denied;
* existing authority may be revoked;
* the Place operator may be alerted;
* an audit event may be recorded;
* the collection provider may be notified;
* normal Place security procedures may be activated.

## 14. Evidence and completion

A completion record should be sufficient to answer:

* which collection was performed;
* which provider performed it;
* which agent or assignment was used;
* when it occurred;
* which Place and collection point were used;
* which item was released;
* whether access was granted;
* whether the collection point was secured;
* whether custody was accepted;
* what completion status was reported;
* what evidence is available;
* whether exceptions occurred.

Potential evidence includes:

* provider collection confirmation;
* collection reference;
* label or barcode scan;
* agent-captured photograph;
* Place-camera image;
* collection-point open and close events;
* lock-state confirmation;
* item-presence or removal indication;
* timestamp;
* service-sender ready declaration;
* agent possession declaration.

Evidence should be retained and disclosed according to applicable privacy, contractual, and Place policies.

## 15. Privacy considerations

The use case should minimise disclosure of:

* resident identity;
* resident presence or absence;
* internal Place layout;
* unrelated camera footage;
* unrelated access points;
* other items awaiting collection;
* item contents where not operationally required;
* destination-recipient details;
* household routines;
* detailed security configuration.

The collection agent should receive only the information required to complete the collection.

Camera access should normally be limited to event-specific evidence. The agent should not receive unrestricted live or historical camera access solely because a camera supports the collection journey.

## 16. Security considerations

The implementation should guard against:

* fraudulent collection bookings;
* collection of an item by the wrong provider;
* collection by an unassigned agent;
* reuse of collection credentials;
* collection from the wrong Place;
* collection outside the permitted period;
* removal of an unrelated item;
* access to an incorrect collection point;
* continued access after completion;
* unauthorised cancellation or reassignment;
* false item-ready declarations;
* false collection-completion declarations;
* manipulation or substitution of evidence;
* disclosure of sensitive Place or item information;
* repeated automated access attempts.

Because collection releases an item from the control of the Place, the implementation may require stronger confirmation than an equivalent low-risk delivery.

## 17. Current-practice alignment

This use case is intended to extend rather than replace existing collection-provider practices.

A collection provider may continue to manage:

* booking;
* shipping labels;
* route planning;
* agent assignment;
* expected arrival;
* item acceptance rules;
* onward tracking;
* failed-collection procedures;
* customer support.

The OSDI or NHS365 role may initially be limited to:

* associating the collection job with the Place;
* confirming that the item is ready;
* exposing the permitted collection location;
* providing current Place instructions;
* granting temporary Place access;
* supporting item identification;
* supporting evidence;
* exchanging relevant status;
* notifying the service sender.

This allows an early service provider to adopt secure Place interaction without replacing its existing collection platform.

## 18. Comparison with UC001

UC001 and UC002 share several common needs:

* provider recognition;
* assigned service agent;
* Place identification;
* scheduled time window;
* service instructions;
* temporary authority;
* gate or boundary access;
* secure compartment access;
* status updates;
* evidence;
* completion;
* exception handling;
* authority expiry.

UC002 introduces additional concerns:

* the Place or service sender must prepare an item;
* the item must be declared ready;
* the agent must identify the correct item;
* the Place must authorise release of the item;
* custody transfers away from the Place;
* an incorrect collection may result in loss of property.

These differences suggest that the common OSDI core should support a general service interaction, while an item-movement profile may define whether the item is being deposited, collected, exchanged, or returned.

## 19. Common OSDI needs identified

UC002 suggests the need for the following common concepts:

* service request or job;
* requesting party;
* service provider;
* service sender;
* assigned service agent;
* Place;
* service point;
* item reference;
* intended item movement;
* scheduled or permitted time window;
* service instructions;
* Place capability;
* capability availability;
* item-ready state;
* credential;
* authority;
* access action;
* custody transfer;
* status update;
* evidence;
* completion;
* exception;
* cancellation;
* authority expiry or revocation.

These concepts remain provisional until compared with additional use cases.

## 20. Proposed NHS365 starter implementation

An initial NHS365 demonstration may include the following components.

### 20.1 User application

The user application may allow the service sender to:

* arrange or register a collection;
* enter or scan a collection reference;
* select a collection point;
* view packaging and label instructions;
* declare the item ready;
* set the permitted collection period;
* receive approaching and arrival notifications;
* approve exceptions;
* cancel the collection;
* view collection completion and evidence.

### 20.2 Collection-agent application template

The collection-agent application may provide:

* agent authentication;
* assigned collection reference entry or scanning;
* arrival reporting;
* item-ready confirmation;
* current Place instructions;
* gate access request;
* collection-box access request;
* item identification;
* possession confirmation;
* evidence submission;
* exception reporting;
* completion status.

### 20.3 NHS365 platform services

The platform may provide:

* collection-job association;
* Place lookup;
* item-ready status;
* authority generation;
* temporary credential validation;
* capability discovery;
* status processing;
* notification;
* evidence association;
* custody-transfer recording;
* audit recording.

### 20.4 NHS365 site agent

The site agent may:

* communicate with the local Place platform;
* map capability requests to local systems;
* operate a gate or collection box;
* confirm compartment state;
* request camera evidence;
* report capability state;
* return success or failure results.

### 20.5 Home Assistant adapter

Where Home Assistant is used, the NHS365 adapter may map:

* an external gate to a cover, lock, or other suitable entity;
* a collection box to a lock and open/closed sensor;
* an optional item-presence sensor to a binary sensor or weight sensor;
* a collection-area camera to a camera entity;
* a notification or intercom action to an appropriate Home Assistant service;
* capability state to normalised NHS365 results.

Home Assistant entity identifiers remain internal to the NHS365 implementation and are not exposed as OSDI concepts.

## 21. Questions for refinement

The following questions should be considered during future iterations:

1. Who must approve the release of an item from a Place?
2. Is a valid collection job sufficient, or must the Place explicitly accept every collection?
3. How should the item-ready declaration be represented?
4. Should item-ready status expire automatically?
5. What minimum information is needed to distinguish the correct item?
6. Must the collection agent scan the item before removal?
7. How should multiple items in one collection point be handled?
8. When does custody formally transfer from the service sender to the provider?
9. What evidence is proportionate for ordinary collections?
10. How should high-value or sensitive items require stronger verification?
11. How should an item be returned to the Place if the agent accepts it and then discovers a problem?
12. How should collection cancellation affect issued credentials?
13. Should the Place support collection-point reservation?
14. How should collections arranged by a third party be authorised by the Place?
15. How should item collection work when the service sender is not the Place operator?
16. What happens when the provider and Place disagree about whether collection occurred?
17. Which concepts belong in OSDI Core and which belong in an item-movement profile?

## 22. Initial conclusion

UC002 demonstrates that secure collection can use many of the same Place-interaction mechanisms as secure delivery.

The collection provider needs a small set of outcomes:

* recognise the collection;
* confirm that the item is ready;
* identify the permitted collection point;
* receive instructions;
* obtain limited temporary access;
* identify and retrieve the correct item;
* accept custody;
* record evidence;
* report completion or failure.

The Place retains control over:

* whether the item may be released;
* which collection point may be accessed;
* what authority is granted;
* how access is implemented;
* what evidence is permitted;
* when authority ends.

The comparison between UC001 and UC002 suggests that OSDI should model the intended movement and custody of an item without treating delivery and collection as entirely separate interaction frameworks.
