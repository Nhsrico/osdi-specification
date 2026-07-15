# UC003 — Return Collection

**Document status:** Informative working draft
**Specification version:** 0.1.0-draft
**Use-case identifier:** UC003

## 1. Purpose

This use case describes the collection of an item from a Place for return to a retailer, marketplace seller, manufacturer, service provider, repair centre, or other receiving organisation.

The return may involve:

* an unwanted purchase;
* a faulty item;
* an incorrect item;
* a damaged item;
* an item being returned under warranty;
* rented or loaned equipment;
* reusable packaging;
* equipment being sent for repair or assessment.

The intended outcome is that an authorised collection agent retrieves the correct return item from an authorised collection point, records appropriate evidence, and transfers the item into the return provider’s custody without receiving unnecessary access to the rest of the Place.

This use case extends UC002 — Item Collection from a Place. It adds return-specific concerns including:

* return authorisation;
* return eligibility;
* merchant or receiving-party references;
* packaging and labelling requirements;
* declared item condition;
* return deadlines;
* refund, replacement, or repair dependencies;
* possible rejection after collection.

## 2. Example scenario

A resident receives an item from a retailer and decides to return it.

The retailer approves the return and issues a return reference. The retailer may also provide:

* a printable return label;
* a QR code;
* a digital return token;
* packaging instructions;
* a collection window;
* a deadline for return;
* an indication of whether the collection agent will supply the label.

The resident registers the return with NHS365 or the return provider and selects a secure collection box at the Place.

The Place has:

* an external gate;
* a secure collection box inside the gate;
* a camera covering the collection area;
* an access controller capable of validating temporary credentials;
* internet connectivity through which return authority may be checked.

The resident prepares the item, places it in the assigned collection box, and declares it ready.

The return provider assigns a collection agent.

The collection agent arrives during the permitted collection window and presents the collection reference through the provider application or an NHS365 collection-agent application.

The Place verifies that:

* the return collection is recognised;
* the return remains active;
* the item has been declared ready;
* the presenting agent is associated with the collection;
* the agent is authorised to access the specified gate and collection point.

The agent retrieves the item, confirms acceptance into transport custody, and closes the collection box.

The Place records the collection, revokes temporary access authority, and notifies the resident.

The retailer may later inspect the item and determine whether the return qualifies for refund, replacement, repair, or rejection.

## 3. Intended outcome

The use case is successfully completed when:

* the return has been authorised or otherwise accepted by the receiving party;
* the correct item is prepared for return;
* the item is collected from the correct Place;
* the item is retrieved from an authorised collection point;
* collection occurs within the permitted period or approved exception;
* access is granted only for the necessary area, action, and duration;
* custody transfers to the collection or return provider;
* the collection point and any access point are left secure;
* collection status and evidence are recorded;
* temporary authority is ended or revoked;
* relevant parties are notified.

Successful collection does not necessarily mean that the retailer or receiving organisation has accepted the item for refund, replacement, repair, or credit.

## 4. Participants

### 4.1 Returning party

The person or organisation returning the item.

The returning party may be:

* the purchaser;
* the service recipient;
* a resident;
* another authorised user of the Place;
* a business;
* a person acting on behalf of the owner of the item.

### 4.2 Requesting party

The party that initiated or arranged the return.

This may be:

* the returning party;
* the retailer;
* a marketplace;
* a manufacturer;
* a repair provider;
* an insurer;
* a rental provider;
* another service organisation.

### 4.3 Receiving organisation

The organisation expected to receive and process the returned item.

This may be:

* a retailer;
* a marketplace seller;
* a manufacturer;
* a repair centre;
* a warranty provider;
* a rental company;
* a recycling organisation;
* another authorised recipient.

### 4.4 Return provider

The organisation responsible for collecting and transporting the returned item.

The return provider may be:

* the retailer’s own logistics operation;
* a parcel carrier;
* a specialist returns provider;
* a marketplace logistics provider;
* a repair or warranty collection service.

The return provider retains responsibility for its operational processes, including:

* collection scheduling;
* route planning;
* agent assignment;
* labelling requirements;
* item acceptance rules;
* onward tracking;
* exception handling.

### 4.5 Collection agent

The person or automated system assigned by the return provider to perform the collection.

The collection agent may be:

* a courier;
* a delivery driver;
* an authorised subcontractor;
* a collection robot;
* another approved collection mechanism.

The initial NHS365 implementation is expected to focus on a human collection agent.

### 4.6 Place operator

The person or organisation responsible for managing service interaction at the Place.

The Place operator determines:

* which collection points may be used;
* which access actions may be granted;
* whether human approval is required;
* what evidence may be captured;
* what restrictions apply.

For a residential Place, the Place operator may be the returning party or another authorised household member.

### 4.7 Place platform

The system responsible for exposing and coordinating the service capabilities available at the Place.

In the initial implementation, NHS365 may act as the Place platform.

### 4.8 Merchant or return system

The system that manages return authorisation, return eligibility, refund, replacement, repair, or credit.

This system may be operated by:

* the retailer;
* a marketplace;
* the manufacturer;
* a warranty provider;
* a repair organisation.

OSDI should not require the Place platform to reproduce the full merchant return-management process.

## 5. Assumptions and preconditions

Before the return collection begins:

* the item is eligible or provisionally eligible for return;
* a return request or return authorisation exists;
* the return has a reference or token;
* the receiving organisation has been identified;
* a collection method has been selected;
* the Place has been configured to support secure collections;
* an authorised collection point has been selected;
* packaging requirements are known;
* labelling requirements are known;
* the permitted collection window or deadline is known;
* the item has not already been returned;
* the Place operator has accepted the collection arrangement;
* the item is suitable for unattended collection where that method is used;
* the Place operator has defined the permitted evidence policy.

The return provider is not required to understand the underlying devices or automation platform used at the Place.

## 6. Return authorisation

A return collection should normally be associated with an authorisation or recognised return arrangement.

The return authorisation may include:

* return reference;
* merchant reference;
* original order reference;
* item reference;
* return reason;
* permitted return method;
* return deadline;
* receiving destination;
* packaging requirements;
* labelling requirements;
* whether the agent supplies the label;
* whether the item requires inspection before transport;
* whether collection is chargeable;
* expected return outcome.

The return authorisation should not require the Place platform to hold the retailer’s complete order or payment record.

The Place platform only needs enough information to:

* recognise the collection;
* confirm that the return remains active;
* identify the correct collection point;
* identify the item sufficiently;
* grant limited authority;
* report collection status and evidence.

## 7. Return outcomes

The intended business outcome may be:

* refund;
* replacement;
* repair;
* warranty assessment;
* account credit;
* rental closure;
* reuse;
* recycling;
* disposal;
* inspection.

Collection completion does not guarantee the final business outcome.

The receiving organisation may later determine that:

* the item is accepted;
* the item is rejected;
* only a partial refund is due;
* repair is required;
* the wrong item was returned;
* the item condition differs from the declaration;
* further information is required.

OSDI should distinguish between:

* collection completed;
* item received by the receiving organisation;
* return accepted;
* return rejected;
* refund or replacement completed.

## 8. Item preparation

Before the item becomes available for collection, the returning party may need to:

* confirm the return request;
* select the item being returned;
* provide a return reason;
* package the item;
* include required accessories or documentation;
* remove personal data where applicable;
* apply a return label;
* obtain or display a QR code;
* provide an item-condition declaration;
* place the item in the assigned collection point;
* declare the item ready.

The return should not normally be made available for collection until the returning party has confirmed that preparation is complete.

The initial baseline should allow manual confirmation without requiring specialised sensors or automated inspection.

## 9. Item-condition declaration

The return process may include a simple declaration of condition.

Examples include:

* unopened;
* unused;
* opened but complete;
* faulty;
* damaged;
* incomplete;
* missing accessories;
* requires repair;
* unknown.

The declaration is provided by the returning party and should not be treated as final proof of condition.

Where permitted, supporting evidence may include:

* photographs;
* video;
* item serial number;
* packaging condition;
* accessory checklist;
* fault description.

OSDI should support references to this information without defining the merchant’s complete return-assessment rules.

## 10. Relevant Place areas

This use case may involve the following areas.

### 10.1 Public approach

The publicly accessible route leading towards the Place.

No OSDI-controlled access is normally required.

### 10.2 External gate or barrier

A controlled boundary that must be passed before reaching the collection point.

The collection agent may receive temporary authority to open the gate.

### 10.3 Collection area

An external or semi-external area approved for return collection.

The collection area should be clearly distinguishable from areas the collection agent is not authorised to enter.

### 10.4 Secure collection point

The specific location from which the return item is to be retrieved.

Examples include:

* a parcel box;
* a locked compartment;
* a collection cabinet;
* a secure room;
* a reception locker;
* a controlled porch.

### 10.5 Main residence or restricted area

An area outside the authority granted for this use case.

Access to the main residence is not part of the normal journey.

## 11. Relevant Place capabilities

The Place may expose the following service-relevant capabilities.

### 11.1 Gate access

The ability to request or authorise opening of an external gate or barrier.

### 11.2 Secure collection-point access

The ability to unlock, release, open, or otherwise make the collection point available.

### 11.3 Item-ready status

The ability to indicate whether the return item:

* has been prepared;
* has been placed in the collection point;
* is ready for release;
* has already been collected;
* is no longer available;
* requires returning-party intervention.

### 11.4 Return-validity status

The ability to indicate whether the return collection:

* remains authorised;
* has expired;
* has been cancelled;
* requires approval;
* has already been completed;
* cannot currently proceed.

This should normally be obtained from the return provider or receiving organisation rather than inferred by the Place.

### 11.5 Item identification

The ability to help distinguish the intended return item from another item.

This may use:

* return reference;
* collection reference;
* barcode or QR code;
* return label;
* item identifier;
* serial number;
* assigned compartment;
* simple item description.

### 11.6 Access-state confirmation

The ability to confirm that a gate, door, or compartment:

* opened;
* closed;
* locked;
* failed to secure;
* remains open unexpectedly.

### 11.7 Item-presence confirmation

Where supported, the ability to indicate that:

* an item was present before collection;
* an item was removed;
* the collection point is now empty;
* another item remains.

Specialised sensors should not be mandatory for the initial baseline.

### 11.8 Notification

The ability to notify relevant parties of:

* return preparation;
* item-ready status;
* approaching collection;
* agent arrival;
* access request;
* item removal;
* collection completion;
* cancellation;
* an exception requiring attention.

### 11.9 Communication

The ability to request assistance through:

* a doorbell;
* an intercom;
* a voice call;
* a message;
* another supported method.

### 11.10 Evidence capture

The ability to capture permitted evidence, such as:

* item condition before collection;
* packaging condition;
* label presence;
* item removal;
* collection-point state;
* collection completion;
* secure closure of the compartment.

### 11.11 Instructions

The ability to provide current instructions, including:

* permitted route;
* gate instructions;
* assigned collection point;
* item-identification guidance;
* label procedure;
* actions if the parcel is not correctly packaged;
* actions if the item appears unsafe or damaged;
* actions if the return authorisation is rejected.

## 12. Information associated with the return

The return journey may use:

* return identifier;
* return authorisation reference;
* original order or transaction reference;
* collection identifier;
* return-provider identity;
* receiving-organisation identity;
* assigned collection-agent identity or assignment reference;
* Place identifier;
* collection-point identifier;
* scheduled or permitted time window;
* return deadline;
* item reference;
* item serial number where relevant;
* return reason;
* item-condition declaration;
* packaging status;
* label status;
* handling requirements;
* item-ready status;
* collection instructions;
* required evidence;
* current return status;
* collection completion time;
* onward tracking reference;
* exception reason;
* evidence references.

The initial use case does not require OSDI to define:

* payment processing;
* refund calculation;
* merchant inventory;
* retailer order-management rules;
* consumer-rights rules;
* full warranty assessment;
* route planning;
* customs documentation;
* complete shipping-label formats.

## 13. Identity and authority

### 13.1 Return-provider recognition

The Place platform should be able to determine which return provider is responsible for the collection.

This may be established through:

* an existing partner integration;
* a signed return-job assertion;
* a provider account;
* an NHS365-issued partner credential;
* another trusted association.

### 13.2 Collection-agent recognition

The collection agent should present sufficient information to associate the agent with the return collection.

The initial implementation may use:

* agent login to a provider or NHS365 application;
* collection barcode or QR code;
* return token;
* provider-issued job credential;
* direct confirmation from the return provider.

Higher-value, sensitive, or regulated returns may require stronger individual verification.

### 13.3 Returning-party authority

The returning party or Place operator should have authority to release the item.

This is especially important where:

* the requesting party is a retailer or marketplace;
* the item belongs to another Place user;
* the item is valuable or sensitive;
* the original purchaser is not present;
* the return was arranged by a third party.

A merchant-issued return authorisation should not by itself grant physical access to the Place.

### 13.4 Granted collection-agent authority

The collection agent may be authorised to:

* request access through a specified external gate;
* enter the designated collection area;
* open the assigned collection point;
* identify the intended return item;
* apply a return label where permitted;
* remove the authorised item;
* request approved evidence capture;
* close and secure the collection point;
* report status and exceptions.

The collection agent should not normally be authorised to:

* enter the main residence;
* access unrelated compartments;
* remove another item;
* inspect unrelated Place contents;
* operate unrelated Place capabilities;
* view unrestricted camera feeds;
* retain access after the collection ends.

### 13.5 Authority duration

Authority should be limited by one or more of:

* return validity;
* collection-job validity;
* item-ready status;
* assigned agent;
* Place;
* collection point;
* item reference;
* permitted actions;
* permitted time window;
* return deadline;
* successful item removal;
* completion;
* cancellation or revocation.

## 14. Normal journey

### Step 1 — Return is requested

The returning party, retailer, marketplace, manufacturer, or another authorised party initiates the return.

The request identifies the item and intended return outcome.

### Step 2 — Return is authorised

The receiving organisation evaluates the request according to its existing policies.

If accepted, it creates a return authorisation or recognised return arrangement.

The authorisation may define:

* return reference;
* return deadline;
* permitted return method;
* packaging requirements;
* labelling method;
* collection provider;
* collection charges;
* expected outcome.

### Step 3 — Collection is arranged

The returning party or receiving organisation schedules a collection.

The return provider creates or maintains the collection job through its normal operational system.

### Step 4 — Collection is accepted by the Place

The Place operator accepts or registers the return collection.

Acceptance associates the return with:

* the Place;
* an authorised collection point;
* a permitted time window;
* the relevant Place access policy.

### Step 5 — Item is prepared

The returning party packages the item and follows the return instructions.

Where relevant, the returning party:

* includes accessories;
* removes personal information;
* applies a label;
* records the serial number;
* captures condition evidence;
* provides a condition declaration.

### Step 6 — Item is placed at the collection point

The item is placed in the designated secure collection point.

Where supported, the Place records:

* collection-point opening;
* item placement;
* item-presence state;
* collection-point closure;
* lock status.

### Step 7 — Item is declared ready

The returning party confirms that preparation is complete and that the item is ready.

The ready declaration may include:

* return reference;
* collection-point identifier;
* item reference;
* label status;
* packaging status;
* declared condition;
* placement time;
* optional evidence.

### Step 8 — Return validity is checked

Before collection, the Place platform or NHS365 service may confirm that:

* the return remains active;
* the collection job remains valid;
* the return deadline has not expired;
* the item is ready;
* the collection has not been cancelled;
* the collection point is available.

### Step 9 — Agent approaches the Place

The return provider or agent application reports that the collection agent is approaching.

The Place platform may notify the returning party or Place operator.

Approaching status should not automatically grant access.

### Step 10 — Agent reports arrival

The collection agent reports arrival using a provider application, NHS365 application template, or another recognised method.

### Step 11 — Collection is validated

The Place platform checks that:

* the return collection is recognised;
* the Place matches the intended collection location;
* the collection is active;
* the return remains valid;
* the current time is acceptable;
* the agent is associated with the job;
* the item has been declared ready;
* the collection point is permitted;
* the required capabilities are available.

### Step 12 — Instructions are presented

The agent receives current instructions, such as:

* use the side gate;
* proceed to collection box 1;
* do not approach the main entrance;
* scan the return label;
* apply the provider label if required;
* remove only the item associated with the current return;
* close the collection box and wait for confirmation.

### Step 13 — Gate access is requested

Where an external gate is present, the agent requests entry.

The Place platform verifies that gate access is within the granted authority.

### Step 14 — Gate state is confirmed

Where supported, the Place records that the gate opened.

The agent enters the designated collection area.

The Place may request or verify that the gate closes behind the agent.

### Step 15 — Collection-point access is requested

The agent requests access to the assigned collection point.

The Place platform checks that:

* the correct point was requested;
* the collection remains active;
* the return remains valid;
* the item is still ready;
* the agent remains authorised;
* the item has not already been collected.

### Step 16 — Collection point is opened

The Place platform causes or permits the collection point to open.

The access event is recorded.

### Step 17 — Agent verifies the return item

The agent checks that the item corresponds to the active return.

This may involve:

* scanning the return label;
* scanning a QR code;
* confirming the return reference;
* matching the item identifier;
* matching the assigned compartment;
* confirming a simple description.

### Step 18 — Label is applied or confirmed

Where required, the agent:

* confirms that the return label is present;
* applies a provider label;
* links the item to a digital return code;
* reports a label exception.

OSDI should support the result but should not define the provider’s complete labelling process.

### Step 19 — Item is removed

The agent removes the item.

Where supported, the Place may detect removal through:

* weight or presence sensing;
* camera analysis;
* collection-point state;
* agent confirmation.

### Step 20 — Transport custody is accepted

The collection agent confirms possession of the item on behalf of the return provider.

This records transfer into transport custody.

It does not necessarily mean the receiving organisation has accepted the return.

### Step 21 — Evidence is captured

Evidence is captured according to the applicable policy.

Evidence may include:

* return label scan;
* provider collection confirmation;
* agent-captured image;
* Place-camera image;
* item-condition evidence;
* collection-point state;
* item-removal confirmation;
* timestamp.

### Step 22 — Collection point is secured

The agent closes the collection point.

Where supported, the Place confirms that it has closed and locked.

### Step 23 — Agent leaves the collection area

The agent exits through the permitted route.

Where relevant, the Place confirms that the external gate has closed.

### Step 24 — Collection is completed

The return provider reports collection completion.

The completion record may include:

* return reference;
* collection time;
* collection-point reference;
* item reference;
* evidence references;
* exception information;
* onward tracking reference.

### Step 25 — Temporary authority ends

Access authority associated with the return collection is revoked or expires.

### Step 26 — Parties are notified

The returning party, Place operator, receiving organisation, or requesting party may receive a collection-completion notification.

### Step 27 — Return progresses outside the Place

After collection, the return provider transports the item to the receiving organisation.

Later statuses may include:

* in transit;
* received;
* inspected;
* accepted;
* rejected;
* refunded;
* replacement issued;
* repair started;
* return closed.

These later stages may be exchanged through OSDI where useful, but they do not involve further physical interaction with the originating Place.

## 15. Example status journey

A simple return journey may be:

```text
Return Requested
    ↓
Return Authorised
    ↓
Collection Arranged
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
Item Collected
    ↓
Collection Completed
    ↓
In Transit
    ↓
Received by Return Organisation
    ↓
Return Accepted or Rejected
    ↓
Refund, Replacement, Repair, or Closure
```

Not every provider must use these exact status names.

The Place-interaction portion should remain distinguishable from later merchant processing.

## 16. Alternative and exception journeys

### 16.1 Return is not authorised

If no valid return authorisation exists:

* collection access should not normally be granted;
* the returning party should be informed;
* the receiving organisation may be contacted;
* the collection may be cancelled or rescheduled.

A collection booking should not automatically prove that the receiving organisation will accept the return.

### 16.2 Return authorisation has expired

If the return deadline has passed:

* access may be denied;
* the receiving organisation may approve an extension;
* a new authorisation may be required;
* the collection may be cancelled.

### 16.3 Item is not ready

If the agent arrives before the item is ready:

* access to the collection point should normally be denied;
* the returning party may be notified;
* the agent may wait within provider rules;
* the collection may be rescheduled or failed.

### 16.4 Item is missing

If the assigned collection point is empty:

* the agent reports the item missing;
* the returning party or Place operator is notified;
* available evidence may be reviewed;
* the collection may be failed or rescheduled.

### 16.5 Incorrect item is present

If the item does not correspond to the return:

* the agent should not remove it;
* the mismatch should be reported;
* the returning party may correct the item;
* the collection may be rescheduled or cancelled.

### 16.6 Label is missing

Depending on provider practice:

* the agent may apply a label;
* a digital code may be sufficient;
* the returning party may be asked to correct the issue;
* the collection may proceed with an exception;
* the collection may be refused.

### 16.7 Item is poorly packaged

If packaging is unsafe or inadequate:

* the agent may refuse collection;
* the returning party may be asked to repackage;
* evidence may be captured;
* the collection may be rescheduled.

### 16.8 Item condition differs from declaration

If the agent is expected to perform a basic condition check and finds a significant discrepancy:

* the discrepancy may be recorded;
* evidence may be captured;
* the receiving organisation may be consulted;
* collection may proceed subject to inspection;
* collection may be refused where provider rules require it.

The collection agent should not be expected to perform a full merchant assessment unless that is part of the service.

### 16.9 Item contains personal data

For devices such as phones, computers, or storage media:

* the returning party may be reminded to remove personal data;
* the provider may require confirmation;
* collection may proceed under the provider’s normal terms;
* OSDI should not inspect the contents of the device.

### 16.10 Item contains prohibited or hazardous material

If the item is unsuitable for the selected transport service:

* collection should be refused;
* access may be ended;
* the returning party should be informed;
* the event should be recorded.

### 16.11 Collection point is offline

If the collection point cannot be operated:

* the failure is reported;
* a communication option may be offered;
* the returning party may approve an alternative;
* the collection may be rescheduled.

### 16.12 External gate cannot be opened

If the gate cannot be operated:

* the agent may retry within defined limits;
* the Place operator may be notified;
* an alternative handover may be arranged;
* the collection may fail or be rescheduled.

### 16.13 Credential is rejected

The credential may be rejected because:

* it is invalid;
* it has expired;
* it is for another Place;
* it is associated with another return;
* the agent is not assigned;
* the collection is cancelled;
* the credential has already been used;
* authority has been revoked.

### 16.14 Return is cancelled after item preparation

If the return is cancelled after the item is placed in the collection point:

* collection authority should be revoked;
* the return provider should be notified;
* the returning party should retrieve or reassign the item;
* any issued credential should become unusable.

### 16.15 Collection succeeds but return is later rejected

The receiving organisation may later reject the item because:

* it is the wrong item;
* it arrived after the deadline;
* it is incomplete;
* its condition is outside policy;
* the return reason is not accepted;
* required documentation is absent.

The return status should distinguish:

* collected;
* received;
* inspected;
* accepted;
* rejected.

Rejection after collection should not alter the historical record that the item was collected successfully.

### 16.16 Evidence capture fails

If optional evidence capture fails, the collection may still complete.

If evidence is required:

* another permitted method may be attempted;
* the provider may approve completion with an exception;
* the collection may be refused or rescheduled.

### 16.17 Network connection is unavailable

Where internet-based validation is unavailable, the Place may support:

* a previously issued short-lived credential;
* a locally verifiable signed credential;
* returning-party-controlled access;
* no access until connectivity is restored.

Offline access should be explicitly supported by policy.

### 16.18 Suspected misuse or fraud

If suspicious activity is detected:

* access may be denied;
* authority may be revoked;
* the Place operator may be alerted;
* the return provider may be notified;
* evidence and audit events may be preserved;
* normal security or fraud procedures may be activated.

## 17. Evidence and completion

A collection-completion record should be sufficient to answer:

* which return was collected;
* which provider performed the collection;
* which agent or assignment was used;
* when collection occurred;
* which Place and collection point were used;
* which item was released;
* whether access was granted;
* whether the collection point was secured;
* whether transport custody was accepted;
* what evidence is available;
* whether exceptions occurred;
* what onward tracking reference was assigned.

Potential evidence includes:

* return authorisation reference;
* collection reference;
* return-label or QR-code scan;
* item identifier or serial number;
* returning-party ready declaration;
* item-condition declaration;
* agent-captured photograph;
* Place-camera image;
* collection-point open and close events;
* lock-state confirmation;
* item-removal indication;
* timestamp;
* transport-custody declaration.

Evidence should be retained and disclosed according to applicable privacy, contractual, and Place policies.

## 18. Privacy considerations

The use case should minimise disclosure of:

* resident identity;
* resident presence or absence;
* internal Place layout;
* unrelated camera footage;
* unrelated access points;
* other items awaiting collection;
* item contents where not required;
* original purchase details;
* payment information;
* refund information;
* household routines;
* detailed Place security configuration.

Condition evidence may reveal personal or commercially sensitive information and should be limited to what is necessary.

The collection agent should not receive unrestricted access to return history, purchase history, or Place camera feeds.

## 19. Security considerations

The implementation should guard against:

* fraudulent return authorisations;
* collection of the wrong item;
* use of a return reference at the wrong Place;
* reuse of credentials;
* unassigned-agent access;
* access outside the permitted period;
* collection after cancellation;
* substitution of a lower-value or different item;
* false item-ready declarations;
* false collection-completion declarations;
* manipulation of condition evidence;
* unauthorised access to merchant or refund information;
* continued access after collection;
* repeated automated access attempts.

Because a return may affect refunds, replacements, warranties, or financial credit, integrity of the return reference, item identity, and collection evidence may be particularly important.

## 20. Current-practice alignment

This use case is intended to extend existing returns processes rather than replace them.

The retailer, marketplace, manufacturer, or return provider may continue to manage:

* return eligibility;
* return authorisation;
* customer support;
* labels and packaging rules;
* refund or replacement decisions;
* inspection;
* repair;
* onward logistics;
* fraud controls;
* financial processing.

The OSDI or NHS365 role may initially be limited to:

* associating the return collection with the Place;
* confirming that the item is ready;
* exposing the permitted collection point;
* providing current Place instructions;
* granting temporary access;
* supporting item and return-reference confirmation;
* supporting evidence;
* exchanging collection status;
* notifying relevant parties.

This allows an early provider to use secure Place collection without replacing its existing returns platform.

## 21. Comparison with UC002

UC002 and UC003 share:

* collection booking;
* service-provider recognition;
* assigned collection agent;
* Place association;
* item-ready state;
* temporary access;
* item identification;
* custody transfer;
* evidence;
* completion;
* exception handling.

UC003 additionally requires consideration of:

* return authorisation;
* receiving organisation;
* return eligibility;
* return deadline;
* return reason;
* packaging and labelling requirements;
* item-condition declaration;
* merchant processing after collection;
* acceptance or rejection after receipt;
* refund, replacement, repair, or credit outcomes.

This suggests that return-specific information should normally sit in an item-return profile or extension rather than in the simplest OSDI core.

## 22. Common OSDI needs identified

UC003 suggests the need for the following common concepts:

* service request or job;
* requesting party;
* service provider;
* service agent;
* Place;
* service point;
* permitted time window;
* service instructions;
* capability;
* credential;
* authority;
* access action;
* item reference;
* item-ready state;
* item movement;
* custody transfer;
* status update;
* evidence;
* completion;
* exception;
* cancellation;
* expiry or revocation.

Return-specific concepts include:

* receiving organisation;
* return authorisation;
* return deadline;
* return reason;
* declared condition;
* packaging status;
* label status;
* post-collection acceptance or rejection;
* refund, replacement, repair, or credit outcome.

These concepts remain provisional until compared with later use cases.

## 23. Proposed NHS365 starter implementation

An initial NHS365 demonstration may include the following components.

### 23.1 User application

The user application may allow the returning party to:

* register or arrange a return;
* select the retailer or receiving organisation;
* enter or scan the return reference;
* view preparation instructions;
* select a collection point;
* record item condition;
* upload optional condition evidence;
* confirm packaging and label status;
* declare the item ready;
* set or view the collection period;
* receive approaching and arrival notifications;
* approve exceptions;
* cancel the return collection;
* view collection status and onward tracking;
* view later return status where supplied by the receiving organisation.

### 23.2 Collection-agent application template

The application may provide:

* agent authentication;
* return or collection reference entry or scanning;
* arrival reporting;
* item-ready confirmation;
* current Place instructions;
* gate access request;
* collection-point access request;
* item and label verification;
* agent-applied label confirmation where applicable;
* custody acceptance;
* evidence submission;
* exception reporting;
* completion status.

### 23.3 NHS365 platform services

The platform may provide:

* return-collection association;
* Place lookup;
* item-ready status;
* return-validity check;
* authority generation;
* temporary credential validation;
* capability discovery;
* status processing;
* notification;
* evidence association;
* custody-transfer recording;
* onward tracking association;
* audit recording.

### 23.4 NHS365 site agent

The site agent may:

* communicate with local Place systems;
* map access requests to local capabilities;
* operate a gate or collection box;
* confirm compartment state;
* request camera evidence;
* report capability state;
* return normalised success or failure results.

### 23.5 Retailer or return-provider template

An early partner template may allow a retailer or return provider to:

* create or import return collections;
* issue return references;
* associate collection agents;
* receive item-ready updates;
* receive collection status;
* receive evidence references;
* publish onward tracking;
* publish received, accepted, rejected, refunded, replaced, or repaired statuses.

This template should integrate with existing provider systems rather than require them to be replaced.

## 24. Questions for refinement

The following questions should be considered during future iterations:

1. What minimum proof is needed that a return is authorised?
2. Must every return be explicitly accepted by the Place?
3. Should the Place platform query return validity at arrival?
4. What information is required to identify the correct return item?
5. Should item condition be represented as structured data or free text initially?
6. Who is responsible for return-condition evidence?
7. How should agent-applied labels be recorded?
8. When does transport custody begin?
9. Should collection completion and return acceptance always be separate statuses?
10. How should return rejection be communicated to the returning party?
11. Does OSDI need to represent refund and replacement outcomes, or merely link to provider status?
12. How should high-value returns require stronger identity or evidence?
13. How should devices containing personal data be handled?
14. How should multiple items under one return authorisation be represented?
15. How should one collection containing several return authorisations be handled?
16. How should an item be returned to the Place when transport custody was accepted in error?
17. Which concepts belong in OSDI Core and which belong in an item-return profile?

## 25. Initial conclusion

UC003 demonstrates that return collection can build upon the same Place-interaction pattern used for ordinary item collection.

The return provider needs a limited set of Place-facing outcomes:

* recognise the return collection;
* confirm that the item is ready;
* identify the permitted collection point;
* receive current instructions;
* obtain temporary access;
* identify and retrieve the correct item;
* accept transport custody;
* record evidence;
* report completion or failure.

The retailer or receiving organisation continues to manage:

* eligibility;
* return policy;
* inspection;
* acceptance or rejection;
* refund;
* replacement;
* repair;
* financial outcomes.

This separation allows OSDI to support secure return collection without becoming a retail returns-management specification.
