# UC007 — Scheduled Care Visit

**Document status:** Informative working draft
**Specification version:** 0.1.0-draft
**Use-case identifier:** UC007

## 1. Purpose

This use case describes a scheduled visit to a Place by an authorised care worker acting on behalf of a recognised care provider.

The visit may support:

* personal care;
* medication assistance;
* welfare checks;
* meal preparation;
* mobility support;
* household assistance;
* companionship;
* another agreed care activity.

The intended outcome is that the correct authorised care worker can:

* identify themselves;
* demonstrate that they are assigned to the visit;
* obtain only the access required;
* enter the Place during the permitted period;
* provide the scheduled care;
* report arrival and departure;
* leave the Place secure;
* record completion or an exception.

This use case focuses on the interaction between the care provider, care worker, NHS365-supported Place, resident, and Place access systems.

It does not attempt to define a complete care-management, clinical-record, payroll, rostering, or regulatory system.

## 2. Example scenario

A resident receives scheduled support from a domiciliary care provider.

The care provider uses its existing care-management system to:

* maintain the resident’s care plan;
* schedule visits;
* assign care workers;
* record care notes;
* manage qualifications and employment;
* handle regulatory and safeguarding obligations.

The resident’s Place is supported by NHS365.

The Place has:

* an external gate;
* a main residence entrance with electronic access control;
* a doorbell or intercom;
* an external camera covering the entrance;
* internet connectivity;
* local capability control through a site agent;
* the ability to validate temporary or digitally presented credentials.

The care worker has:

* an identity verified through IAAM365 or another accepted identity service;
* a relationship with the care provider;
* a valid assignment to the scheduled visit;
* any professional role or qualification information required by the provider;
* an application capable of presenting the visit assignment.

Before the visit, the care provider shares only the information needed to coordinate access and status.

The care worker arrives during the scheduled period and reports arrival.

The Place or NHS365 platform validates:

* the care provider;
* the care worker;
* the visit assignment;
* the Place;
* the permitted time;
* the requested access action.

The resident may answer the door normally.

If the resident does not answer and the visit policy permits assisted entry, the care worker may receive temporary authority to unlock the main entrance.

The worker enters, provides the scheduled care, and later reports departure.

The entrance is secured, temporary authority ends, and visit completion is reported.

Detailed care notes remain in the care provider’s care-management system and are not stored as general OSDI Place evidence.

## 3. Intended outcome

The use case is successfully completed when:

* the scheduled visit is recognised;
* the correct care provider and care worker are associated with the visit;
* the resident or authorised representative has accepted the care arrangement;
* access is granted according to the agreed policy;
* the worker enters only the permitted areas;
* the worker reports arrival and departure;
* the Place is left secure;
* the care provider receives an appropriate visit status;
* access authority ends after the visit;
* required Place-interaction evidence is recorded;
* confidential care information remains appropriately separated.

Successful completion of the OSDI interaction indicates that the visit was performed or reported as performed.

It does not independently prove the quality, clinical appropriateness, or completeness of care.

## 4. Participants

### 4.1 Care recipient

The person intended to receive the care service.

The care recipient may also be:

* the resident;
* the Service Recipient;
* the Place Operator;
* the person who approved the care arrangement.

These roles should not always be assumed to be identical.

### 4.2 Resident

A person living at or normally occupying the Place.

The resident may be the care recipient or another member of the household.

### 4.3 Requesting party

The party that arranged or requested the care service.

This may be:

* the care recipient;
* a family member;
* an authorised representative;
* a care coordinator;
* a health or social-care body;
* a local authority;
* another approved organisation.

### 4.4 Care provider

The organisation responsible for coordinating and delivering the care service.

The care provider may manage:

* care planning;
* scheduling;
* worker assignment;
* professional qualifications;
* supervision;
* care notes;
* safeguarding;
* regulatory obligations;
* visit completion;
* payroll and billing.

The care provider is a Service Provider for this use case.

### 4.5 Care worker

The person assigned by the care provider to perform the scheduled visit.

The care worker is the Service Agent.

The care worker may be:

* a domiciliary care worker;
* a nurse;
* a healthcare assistant;
* a support worker;
* a personal assistant;
* another authorised professional or support worker.

### 4.6 Place operator

The person or organisation responsible for controlling service interaction at the Place.

The Place Operator may be:

* the care recipient;
* another resident;
* a family member;
* an authorised representative;
* a housing provider;
* a care organisation;
* another approved party.

### 4.7 Authorised representative

A person or organisation permitted to act for the care recipient or Place Operator.

Examples include:

* family member;
* legal representative;
* care coordinator;
* appointed advocate;
* housing officer;
* another trusted delegate.

### 4.8 Place platform

The system responsible for coordinating the service capabilities available at the Place.

In the initial implementation, NHS365 may act as the Place platform.

### 4.9 Identity provider

A system used to establish or support identity claims.

The initial NHS365 implementation may use IAAM365.

OSDI should not require a particular identity provider.

### 4.10 Care-management system

The system used by the care provider to manage care-specific operations.

The care-management system may remain the authoritative source for:

* visit schedules;
* assignments;
* care plans;
* worker records;
* care notes;
* safeguarding records;
* clinical or operational information.

OSDI should exchange only the information needed to coordinate the Place interaction.

## 5. Assumptions and preconditions

Before the visit begins:

* a valid care arrangement exists;
* the care recipient or authorised representative has accepted the care service;
* a scheduled visit exists;
* the intended Place is known;
* the care provider is recognised;
* a care worker has been assigned;
* the care worker has an acceptable verified identity;
* any required employment, role, or qualification checks have been completed;
* the visit time window is known;
* the permitted access method is defined;
* the areas the care worker may enter are known;
* the Place has a policy for resident response and assisted entry;
* communication and escalation routes are defined;
* the care provider has appropriate consent and legal authority to process necessary information;
* the Place is configured to support the agreed access method.

The initial OSDI baseline should not require the Place platform to hold the resident’s complete care plan.

## 6. Relationship to existing care practice

This use case should align with established care-provider procedures.

The care provider may continue to use existing systems for:

* rostering;
* electronic visit verification;
* care planning;
* clinical documentation;
* medication records;
* safeguarding;
* billing;
* workforce management;
* regulatory reporting.

OSDI or NHS365 may initially support only:

* recognition of the scheduled visit;
* recognition of the assigned care worker;
* arrival and departure status;
* Place instructions;
* limited access authority;
* communication and escalation;
* Place-access evidence;
* completion or exception reporting.

This allows the care provider to retain familiar working practices.

## 7. Relevant Place areas

### 7.1 Public approach

The publicly accessible route to the Place.

### 7.2 External gate or shared boundary

A controlled gate, entrance, or shared boundary that may need to be passed before reaching the residence.

### 7.3 Main residence entrance

The primary controlled entrance through which the care worker enters.

This is likely to carry greater risk than an external parcel box and may require stronger identity and authority checks.

### 7.4 Shared internal area

A shared hall, lobby, lift, or corridor within a multi-occupancy building.

### 7.5 Permitted care area

The part of the Place in which the care service may be performed.

This may include:

* living room;
* kitchen;
* bedroom;
* bathroom;
* another agreed area.

The initial OSDI baseline should not require a detailed digital map of the residence.

### 7.6 Restricted area

An area the care worker is not authorised to enter unless separately permitted.

## 8. Relevant Place capabilities

### 8.1 Arrival reporting

The ability for the care worker to report arrival at the Place.

### 8.2 Resident notification

The ability to inform the resident that the care worker has arrived.

This may use:

* doorbell;
* intercom;
* application notification;
* voice announcement;
* telephone call;
* another accessible method.

### 8.3 External gate access

The ability to request entry through an external gate or shared boundary.

### 8.4 Main entrance access

The ability to request or perform authorised entry through the main residence entrance.

### 8.5 Credential validation

The ability to validate:

* worker identity;
* provider relationship;
* visit assignment;
* temporary authority;
* time window;
* Place;
* permitted access action.

Validation may involve internet access, local verification, or both.

### 8.6 Resident approval

The ability for the resident or authorised representative to approve or reject access.

### 8.7 Assisted entry

The ability to grant temporary entry when the resident cannot operate the entrance personally and the visit policy permits entry.

### 8.8 Communication

The ability to contact:

* the resident;
* an authorised representative;
* the care provider;
* an emergency contact;
* a support service.

### 8.9 Access-state confirmation

The ability to indicate that an entrance:

* opened;
* closed;
* locked;
* failed to secure;
* remains open unexpectedly.

### 8.10 Departure reporting

The ability for the care worker to report departure.

### 8.11 Evidence capture

The ability to record limited Place-interaction evidence, such as:

* arrival time;
* access authorisation;
* entrance opening;
* entrance closure;
* departure time;
* credential-validation result;
* exception or escalation event.

This capability should not imply routine recording of care delivery inside the residence.

### 8.12 Safety alert

The ability to raise a concern or request assistance.

Examples include:

* resident does not respond;
* worker feels unsafe;
* entrance cannot be secured;
* urgent welfare concern;
* another unexpected condition.

## 9. Information associated with the visit

The scheduled care visit may use:

* Service Journey identifier;
* Service Visit identifier;
* care-provider reference;
* care-provider identity;
* assigned care-worker identity;
* worker assignment reference;
* Place identifier;
* scheduled time window;
* expected visit duration;
* permitted access method;
* relevant Place instructions;
* resident contact preference;
* authorised-representative contact route;
* visit status;
* access status;
* arrival time;
* departure time;
* exception information;
* references to Place-interaction evidence.

The OSDI interaction should not normally include:

* full care plan;
* diagnosis;
* detailed medical history;
* medication details;
* clinical notes;
* personal care notes;
* safeguarding records;
* unrelated household information.

Where the care worker needs such information, it should normally be supplied through the care provider’s secure care-management system.

## 10. Identity, role, and assignment

### 10.1 Care-provider recognition

The Place platform should be able to determine which care provider is responsible for the visit.

This may be established through:

* a partner integration;
* an organisation credential;
* a signed provider assertion;
* an NHS365 partner relationship;
* another accepted trust mechanism.

### 10.2 Care-worker identity

The care worker should have an identity appropriate to the risk of entering the residence.

The initial NHS365 implementation may use IAAM365 to support:

* verified personal identity;
* care-provider affiliation;
* application login;
* role information;
* assignment presentation.

OSDI should define the required outcome without requiring IAAM365.

### 10.3 Provider relationship

The Place platform should be able to determine that the care worker is acting for the recognised care provider.

This may be established through:

* provider-issued assignment;
* signed organisational claim;
* direct provider confirmation;
* trusted workforce-directory association;
* another recognised mechanism.

### 10.4 Visit assignment

The worker should be associated with the specific scheduled visit.

The assignment may include:

* worker identity;
* provider;
* Place;
* time window;
* permitted actions;
* replacement status;
* expiry.

Identity alone should not grant access.

A verified care worker who is not assigned to the current visit should not normally receive entry.

### 10.5 Professional role and qualifications

Some care services may require evidence of:

* professional role;
* training;
* registration;
* qualification;
* employment status;
* background or vetting checks.

The care provider should normally remain responsible for validating and maintaining these records.

The Place platform may rely on a simple provider assertion that the assigned worker is suitable for the visit.

OSDI should not initially reproduce professional registration or vetting systems.

## 11. Consent and authority

### 11.1 Care arrangement consent

The care recipient or authorised representative should have accepted the care arrangement.

This acceptance may establish that the care provider may schedule workers to attend under agreed conditions.

### 11.2 Standing access policy

The Place Operator may establish a standing policy such as:

* always require the resident to answer;
* allow assigned workers to enter during scheduled visits;
* allow assisted entry only after a defined waiting period;
* require approval from a representative;
* permit entry only for named workers;
* deny unattended entry.

### 11.3 Visit-specific authority

Authority should be granted for the specific Service Visit.

It may allow the care worker to:

* report arrival;
* use an external gate;
* ring or call the resident;
* request approval;
* unlock the main entrance;
* enter the permitted area;
* report departure;
* secure the entrance;
* raise an exception or safety alert.

### 11.4 Limits of authority

The care worker should not automatically be authorised to:

* enter outside the scheduled or approved period;
* admit another person;
* use unrelated Place capabilities;
* view unrestricted camera feeds;
* access unrelated household information;
* retain access after departure;
* transfer their credential to another worker.

### 11.5 Authority duration

Authority should be limited by:

* Service Visit;
* assigned worker;
* care provider;
* Place;
* time window;
* permitted actions;
* visit status;
* cancellation;
* completion;
* expiry;
* revocation.

## 12. Access modes

The Place may support one or more access modes.

### 12.1 Resident-controlled entry

The care worker arrives and the resident opens the entrance.

This should remain the preferred method where it is practical and consistent with the care arrangement.

### 12.2 Remote representative approval

An authorised representative remotely approves entry.

### 12.3 Temporary code

The care worker uses a short-lived code associated with the visit.

### 12.4 Digital credential

The care worker presents a digitally verifiable credential through an application or supported access controller.

### 12.5 Remote release

The Place platform releases the entrance after validating the worker and visit.

### 12.6 Local validation

The Place validates a short-lived or signed credential locally when internet access is unavailable.

### 12.7 Physical key or key-safe process

Some Places may continue to use:

* physical key;
* key safe;
* staffed access;
* existing provider procedure.

OSDI may record that an approved access method was used without controlling the method directly.

## 13. Normal journey

### Step 1 — Care visit is scheduled

The care provider schedules the visit through its normal care-management system.

The schedule includes:

* care recipient;
* Place;
* planned time;
* expected duration;
* required worker role;
* relevant visit reference.

### Step 2 — Worker is assigned

The care provider assigns a care worker.

The assignment associates:

* provider;
* worker;
* visit;
* Place;
* time window;
* permitted interaction.

### Step 3 — Place receives visit notice

The Place platform or NHS365 receives enough information to recognise the scheduled visit.

The Place does not need the full care plan.

### Step 4 — Access policy is prepared

The Place determines:

* normal access method;
* whether resident approval is required;
* whether assisted entry is permitted;
* permitted time window;
* relevant Place instructions;
* escalation contacts.

### Step 5 — Worker prepares for the visit

The care worker authenticates to the provider or NHS365 application and receives:

* visit reference;
* destination;
* permitted time;
* appropriate Place instructions;
* contact and escalation options.

Sensitive care information should continue to be obtained through the provider’s authorised system.

### Step 6 — Worker approaches the Place

The worker or provider application may report approaching status.

The Place may notify the resident.

Approaching status should not grant entry.

### Step 7 — Worker reports arrival

The worker reports arrival at the Place.

The arrival report is associated with the scheduled Service Visit.

### Step 8 — Visit is validated

The Place platform checks:

* the care provider is recognised;
* the worker identity is acceptable;
* the worker is assigned;
* the Place matches;
* the visit is active;
* the current time is permitted;
* the requested access is allowed.

### Step 9 — Arrival notification is made

The resident is notified through the configured method.

The worker may use the doorbell, intercom, or another communication method.

### Step 10 — Resident response is awaited

The worker follows the agreed waiting procedure.

For example:

* ring once;
* wait a defined period;
* attempt intercom;
* send a notification;
* contact the resident;
* contact the care provider.

### Step 11 — Entry is authorised

Entry may be authorised by:

* the resident opening the entrance;
* resident approval through the application;
* authorised-representative approval;
* standing visit policy;
* validated temporary credential;
* care-provider-assisted process.

### Step 12 — Entrance is opened

The entrance is opened using the authorised method.

Where supported, the Place records:

* access request;
* authorisation result;
* entrance opening;
* worker entry.

### Step 13 — Worker enters

The care worker enters the Place and follows the applicable care-provider procedures.

OSDI does not direct the detailed care activity.

### Step 14 — Visit is started

The worker or provider application records that the care visit has started.

Arrival at the Place and start of care may be recorded as separate events where useful.

### Step 15 — Care is provided

The care worker performs the agreed service.

Care-specific actions and records remain within the care provider’s systems unless a specific OSDI interaction is required.

### Step 16 — Visit exceptions are reported if necessary

The worker may report an OSDI-relevant exception such as:

* resident not present;
* resident does not respond;
* access refused;
* entrance fault;
* worker unable to remain;
* worker safety concern;
* urgent escalation required.

Detailed care observations should remain in the appropriate care system.

### Step 17 — Worker prepares to leave

The worker follows provider procedures before departure.

This may include:

* ensuring the resident is safe;
* checking that agreed tasks are complete;
* recording care notes;
* informing the resident;
* checking the exit route.

### Step 18 — Worker exits

The worker leaves through the authorised entrance.

### Step 19 — Entrance is secured

Where supported, the Place confirms that the entrance:

* closed;
* locked;
* remains secure.

If the entrance cannot be secured, an exception is raised.

### Step 20 — Departure is reported

The worker reports departure.

The departure report may include:

* departure time;
* visit completed;
* visit completed with exception;
* access issue;
* follow-up required.

### Step 21 — Visit is completed

The Service Visit is marked:

* completed;
* completed with exception;
* failed;
* cancelled.

### Step 22 — Temporary authority ends

Unused or continuing access authority is revoked or expires.

### Step 23 — Relevant parties are notified

The care provider receives the visit status.

The resident or authorised representative may also receive an appropriate confirmation.

## 14. Example status journey

A simple scheduled-care status journey may be:

```text
Scheduled
    ↓
Worker Assigned
    ↓
Worker Approaching
    ↓
Worker Arrived
    ↓
Identity and Assignment Validated
    ↓
Entry Authorised
    ↓
Visit Started
    ↓
Visit in Progress
    ↓
Worker Departed
    ↓
Entrance Secured
    ↓
Completed
```

Alternative final states may include:

```text
Cancelled
Unable to Access
Resident Unavailable
Completed with Exception
Escalated
```

OSDI should use only the minimum shared statuses needed for coordination.

The care provider may retain a more detailed internal visit-status model.

## 15. Alternative and exception journeys

### 15.1 Resident answers normally

The resident opens the door without automated access.

The system may still record:

* worker arrival;
* successful visit validation;
* visit start;
* departure;
* completion.

### 15.2 Resident does not answer

The worker follows the agreed escalation sequence.

This may include:

* repeat notification;
* intercom;
* telephone call;
* contact authorised representative;
* contact care provider;
* request assisted entry;
* request welfare escalation.

Lack of response should not automatically grant access unless the policy explicitly permits it.

### 15.3 Worker arrives early

The Place policy may:

* permit entry within a grace period;
* require resident approval;
* ask the worker to wait;
* deny entry until the scheduled time.

### 15.4 Worker arrives late

The Place may:

* continue to accept the visit;
* notify the resident;
* request approval;
* treat the assignment as expired;
* require provider confirmation.

### 15.5 Assigned worker changes

The care provider may assign a replacement worker.

The Place should validate:

* the updated assignment;
* the new worker identity;
* the continuing visit authority.

A credential issued to the previous worker should be revoked or become invalid.

### 15.6 Unassigned worker arrives

A recognised care worker who is not assigned to the visit should not normally receive entry.

The worker may:

* contact the care provider;
* obtain a corrected assignment;
* request resident approval;
* leave without entry.

### 15.7 Credential cannot be validated online

The Place may support:

* a locally verifiable signed credential;
* a previously issued short-lived credential;
* resident-controlled entry;
* provider telephone confirmation;
* no automated entry.

Offline behaviour should be defined by Place policy.

### 15.8 Resident refuses entry

The worker should not enter.

The refusal should be reported to the care provider.

The worker may follow safeguarding or welfare procedures where relevant, but OSDI should not define the full care response.

### 15.9 Care recipient is absent

The worker reports the absence.

The Place or provider may:

* contact the recipient;
* contact an authorised representative;
* reschedule;
* raise a welfare concern;
* record an exception.

### 15.10 Worker feels unsafe

The worker may:

* avoid entry;
* leave the Place;
* contact the provider;
* raise a safety alert;
* contact emergency services where necessary.

### 15.11 Access system fails

If the entrance cannot be operated:

* the worker may use the doorbell or intercom;
* the resident may open manually;
* the provider may be contacted;
* an authorised physical key process may be used;
* the visit may fail or be delayed.

Access-system failure should not automatically broaden authority.

### 15.12 Entrance fails to secure

If the entrance remains open or unlocked after departure:

* the worker should attempt to secure it;
* the Place Operator should be notified;
* the care provider may be informed;
* a security exception should be recorded;
* assistance may be requested.

### 15.13 Worker forgets to report departure

The system may:

* prompt the worker;
* use entrance state as supporting evidence;
* ask the provider to confirm;
* mark the visit as requiring review.

Automatic assumptions should be used cautiously.

### 15.14 Visit exceeds expected duration

An extended visit may be legitimate.

The system should not automatically revoke access while the worker is inside solely because the planned duration has elapsed.

A reasonable overrun policy may:

* extend authority while the visit remains active;
* notify the provider;
* require confirmation for significant overruns;
* revoke re-entry after departure.

### 15.15 Care concern requires escalation

The worker may discover a concern requiring:

* supervisor contact;
* family contact;
* healthcare escalation;
* emergency response;
* extended visit duration.

OSDI may record that escalation occurred without storing detailed clinical or safeguarding information.

### 15.16 Visit is cancelled

If the visit is cancelled:

* assigned authority should be revoked;
* worker credentials for the visit should become unusable;
* relevant parties should be notified;
* completed historical records should remain unchanged.

### 15.17 Duplicate worker arrival

If more than one worker presents for a single-worker visit:

* only authorised assignments should be accepted;
* provider confirmation may be required;
* unexpected access attempts should be recorded.

Some visits may legitimately require multiple workers and should be scheduled accordingly.

## 16. Evidence and completion

A Place-interaction completion record should be able to answer:

* which scheduled visit occurred;
* which care provider was responsible;
* which worker or assignment was presented;
* when the worker arrived;
* how access was authorised;
* when entry occurred;
* when departure occurred;
* whether the entrance was secured;
* whether an OSDI-relevant exception occurred;
* what limited evidence is available.

Potential evidence includes:

* provider visit reference;
* verified worker identity reference;
* assignment validation;
* arrival timestamp;
* resident or representative approval;
* entrance open and close events;
* lock-state confirmation;
* departure timestamp;
* worker completion declaration;
* exception or escalation reference.

The evidence should normally support the Place interaction and access process.

It should not become a general record of the care delivered.

## 17. Separation of care records and Place evidence

Care information and Place-interaction information should remain separated.

### 17.1 Place-interaction information

Examples include:

* worker arrived;
* worker identity and assignment were validated;
* access was granted;
* entrance opened;
* worker departed;
* entrance secured;
* an access exception occurred.

### 17.2 Care-provider information

Examples include:

* personal-care tasks completed;
* medication administered;
* health observations;
* care notes;
* safeguarding concerns;
* clinical instructions;
* details of the resident’s condition.

OSDI should not require confidential care notes to be shared with the Place platform.

Where coordination requires a limited care-related status, the information should be:

* necessary;
* proportionate;
* clearly defined;
* access controlled;
* retained according to the relevant policy.

## 18. Privacy considerations

The use case may involve sensitive personal information.

The implementation should minimise disclosure of:

* care recipient’s health condition;
* care plan;
* worker qualifications beyond what is needed;
* household routines;
* resident presence or absence;
* internal Place layout;
* unrelated camera footage;
* unrelated access history;
* family or representative details;
* other residents’ information.

The care worker should receive only the Place information needed for the visit.

The Place platform should receive only the provider and assignment information needed to validate access.

Camera evidence should normally be limited to external entrance interaction.

Internal cameras should not be made available to the care provider or worker merely because they exist.

## 19. Security considerations

The implementation should guard against:

* impersonation of a care worker;
* use of a genuine worker identity without a valid assignment;
* reuse of a visit credential;
* access at the wrong Place;
* access outside the permitted period;
* use of a cancelled or superseded assignment;
* transfer of credentials between workers;
* unauthorised entry to restricted areas;
* continued access after departure;
* disclosure of resident vulnerability or routine;
* manipulation of arrival or departure records;
* false completion reporting;
* inappropriate use of emergency or assisted entry;
* excessive retention of care-related information.

Main-residence access should normally require stronger assurance than access to an external delivery point.

## 20. Current-practice alignment

The initial integration should require minimal changes to care-provider procedures.

The care provider may continue to:

* create the care plan;
* schedule the visit;
* assign the worker;
* verify employment and qualifications;
* provide worker instructions;
* collect care notes;
* manage visit verification;
* handle safeguarding and escalation;
* bill or report the service.

NHS365 or OSDI may provide:

* Place recognition;
* visit association;
* identity and assignment validation;
* Place instructions;
* arrival and departure status;
* temporary access;
* resident or representative approval;
* access evidence;
* access exception reporting.

An early care provider should be able to use an NHS365 application template without replacing its existing care-management system.

## 21. Comparison with UC001–UC004

UC007 validates several existing concepts:

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

UC007 also adds emphasis to:

* verified personal identity;
* provider relationship;
* visit assignment;
* professional role;
* standing consent;
* resident approval;
* delegated authority;
* main-residence access;
* arrival and departure;
* privacy boundaries;
* separation of operational evidence from confidential service records.

UC007 does not require the Item or Custody concepts used in logistics.

This supports keeping Item and Custody primarily within an item-movement profile unless broader use cases require them.

## 22. Common OSDI needs identified

UC007 suggests that an initial OSDI baseline may need to support:

* recognised Service Providers;
* verified or adequately assured Service Agents;
* provider-to-agent relationship;
* visit assignment;
* scheduled Time Window;
* Place-specific Authority;
* standing or visit-specific access policy;
* resident or representative approval;
* Place instructions;
* arrival and departure reporting;
* entry and exit Actions;
* access-state Evidence;
* limited exception reporting;
* cancellation and reassignment;
* Authority expiry and revocation;
* separation of OSDI interaction data from domain-specific records.

## 23. Proposed NHS365 starter implementation

### 23.1 Care-provider application template

The provider template may allow an early partner to:

* register the care organisation;
* register or link care workers;
* import or create scheduled visits;
* assign workers;
* submit replacement assignments;
* receive arrival and departure status;
* receive access results;
* receive Place-access exceptions;
* cancel or reschedule visits;
* link to its existing care-management system.

### 23.2 Care-worker application template

The worker application may provide:

* IAAM365 or supported authentication;
* assigned visit list;
* navigation to the Place;
* current Place instructions;
* approaching and arrival reporting;
* identity and assignment presentation;
* gate and entrance access request;
* resident contact options;
* visit-start confirmation;
* departure reporting;
* access exception reporting;
* emergency contact options.

The application should avoid storing unnecessary care information.

### 23.3 Resident application

The resident or authorised representative may be able to:

* view scheduled visits;
* see the assigned provider and worker where permitted;
* approve or reject entry;
* define standing access preferences;
* receive arrival notifications;
* contact the provider;
* view arrival and departure records;
* revoke future access;
* report concerns.

### 23.4 NHS365 platform services

The platform may provide:

* provider registration;
* worker identity association;
* IAAM365 integration;
* visit association;
* assignment validation;
* Time Window validation;
* Authority generation;
* temporary credential validation;
* Place capability discovery;
* resident approval;
* notifications;
* arrival and departure status;
* evidence association;
* audit recording.

### 23.5 NHS365 site agent

The site agent may:

* communicate with local Place systems;
* operate an external gate or main entrance;
* validate or receive temporary authority;
* report entrance state;
* trigger resident notifications;
* request permitted external-camera evidence;
* return normalised success or failure results.

### 23.6 Home Assistant adapter

Where Home Assistant is used, the NHS365 adapter may map:

* an external gate to an appropriate lock or cover entity;
* the main entrance to a lock entity;
* entrance state to contact or lock-state entities;
* an external entrance camera to a camera entity;
* a doorbell or intercom to supported services or integrations;
* resident notifications to Home Assistant notification services;
* Place actions to normalised NHS365 capability results.

Home Assistant entity identifiers remain internal to the NHS365 implementation.

## 24. Starter demonstration

A first demonstration could use the following journey:

1. NHS365 holds a scheduled care visit.
2. A care worker signs into the template application using IAAM365.
3. The application displays the assigned visit.
4. The worker reports approaching.
5. The resident receives a notification.
6. The worker reports arrival.
7. NHS365 validates identity, provider, assignment, Place, and time.
8. The worker rings the doorbell.
9. The resident approves entry through the NHS365 application.
10. The site agent unlocks the main entrance through Home Assistant.
11. The worker enters.
12. The entrance closes and locks.
13. The worker records visit start.
14. The worker later records departure.
15. The site agent confirms that the entrance is secured.
16. NHS365 records the visit as completed.
17. Temporary authority expires.

A second demonstration could show assisted entry when the resident does not answer but a standing policy permits access by the assigned worker.

## 25. Questions for refinement

1. What minimum identity assurance is required for a scheduled care worker?
2. Is provider confirmation sufficient to establish worker suitability?
3. Should the Place receive professional-role information or only an access-approved assertion?
4. How should resident consent to the overall care arrangement be recorded?
5. Should standing access authority be represented separately from visit-specific Authority?
6. What is the minimum assignment information the Place must receive?
7. How should replacement workers be handled close to the visit time?
8. How long before and after the scheduled time should access be permitted?
9. How should legitimate visit overruns affect Authority?
10. Should arrival and visit start be separate statuses?
11. Should departure and visit completion be separate statuses?
12. What evidence is appropriate for ordinary care visits?
13. How should the system distinguish access verification from electronic visit verification used for payroll?
14. When may assisted entry occur without immediate resident approval?
15. How should delegated representatives approve or revoke access?
16. How should multiple care workers on one visit be represented?
17. How should confidential care information remain separate from OSDI status?
18. What information may the resident see about the assigned worker?
19. What happens when the provider system and Place record different arrival or departure times?
20. Which concepts belong in OSDI Core and which belong in a care-service profile?

## 26. Concepts validated

UC007 validates the following cross-domain concepts:

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

It suggests possible additional core concepts or clarifications:

* **Assignment** — association of a Service Agent with a Service Visit;
* **Approval** — a decision by an authorised party permitting an Action;
* **Access Policy** — the rules used by a Place to determine whether an Action may proceed;
* **Representative** — a party authorised to act for a Service Recipient or Place Operator;
* **Assurance** — confidence supporting an identity, role, assignment, or claim.

These should remain provisional until tested against replacement, unplanned, and emergency visits.

## 27. Initial conclusion

UC007 demonstrates that the initial OSDI model can support scheduled care access without being centred on logistics.

The common pattern remains:

* an intended service outcome;
* a recognised Service Provider;
* an assigned Service Agent;
* a bounded Service Visit;
* a specific Place;
* limited Place-specific Authority;
* service-relevant Capabilities;
* arrival and departure Status;
* proportionate Evidence;
* explicit Completion or Exception.

The care use case places greater emphasis on:

* personal identity;
* provider relationship;
* assignment;
* consent;
* approval;
* main-residence access;
* privacy;
* separation of OSDI interaction records from confidential service records.

This suggests that the OSDI Core model remains useful across both item movement and care, while domain-specific details should be defined through separate profiles.
