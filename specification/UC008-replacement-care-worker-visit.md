# UC008 — Replacement Care Worker Visit

**Document status:** Informative working draft
**Specification version:** 0.1.0-draft
**Use-case identifier:** UC008

## 1. Purpose

This use case describes a scheduled care visit in which the originally assigned care worker is replaced before the visit is completed.

The replacement may occur because of:

* illness;
* delay;
* shift change;
* emergency reassignment;
* transport disruption;
* staff unavailability;
* safeguarding or suitability concerns;
* another operational reason.

The intended outcome is that the replacement worker can be assigned, recognised, and granted appropriate access without requiring the resident or Place to repeat the entire care arrangement.

The process should ensure that:

* the replacement is authorised by the care provider;
* the original assignment is withdrawn or superseded;
* the resident or authorised representative is informed where appropriate;
* only the currently assigned worker receives access;
* access remains limited to the scheduled visit;
* the Place can distinguish a legitimate replacement from an unassigned worker;
* the visit can continue with minimal disruption.

This use case extends UC007 — Scheduled Care Visit.

## 2. Example scenario

A resident has a scheduled care visit at 10:00.

The care provider originally assigns Worker A.

Shortly before the visit, Worker A becomes unavailable. The provider assigns Worker B.

Worker B has:

* a verified identity;
* an active relationship with the care provider;
* any required role or suitability status;
* a new assignment to the visit.

The provider updates the visit assignment.

NHS365 receives the updated assignment and:

* marks Worker A as no longer authorised;
* associates Worker B with the visit;
* updates any temporary credentials;
* notifies the resident or authorised representative;
* keeps the original visit time and Place access policy unless otherwise changed.

Worker B arrives and presents the replacement assignment.

The Place validates:

* the recognised care provider;
* Worker B’s identity;
* the updated assignment;
* the scheduled Place and time;
* the permitted access actions.

Worker A’s previous credential is no longer accepted.

Worker B completes the visit under the same care arrangement and reports departure.

## 3. Intended outcome

The use case is successfully completed when:

* the replacement assignment is issued by an authorised care provider;
* the previous assignment is withdrawn, expired, or superseded;
* the Place recognises the current assignment;
* the resident or representative is informed according to policy;
* the replacement worker receives only the authority required for the visit;
* the replaced worker cannot use superseded access authority;
* the visit is completed or an exception is recorded;
* the assignment history remains auditable.

## 4. Participants

### 4.1 Care recipient

The person intended to receive the scheduled care.

### 4.2 Resident

A person living at or occupying the Place.

The resident may be the care recipient.

### 4.3 Care provider

The organisation responsible for scheduling the visit and assigning a suitable worker.

The care provider is responsible for deciding that the replacement worker is suitable for the visit.

### 4.4 Original care worker

The Service Agent initially assigned to the visit.

The original worker may never attend the Place.

### 4.5 Replacement care worker

The Service Agent newly assigned to perform the visit.

The replacement worker may be:

* assigned before the original worker starts travelling;
* assigned while the original worker is travelling;
* assigned after a missed or failed arrival;
* assigned after the visit has begun only in exceptional cases.

### 4.6 Place operator

The person or organisation responsible for controlling service interaction at the Place.

### 4.7 Authorised representative

A person or organisation permitted to receive notices or approve access on behalf of the care recipient or Place Operator.

### 4.8 Place platform

The system responsible for recognising the active assignment and coordinating Place interaction.

In the initial implementation, NHS365 may act as the Place platform.

### 4.9 Care-management system

The provider system that remains authoritative for scheduling and workforce assignment.

## 5. Assumptions and preconditions

Before reassignment:

* a valid scheduled care visit exists;
* the Place has accepted or recognised the visit;
* an original worker assignment exists;
* the care provider is permitted to replace the assigned worker;
* the replacement worker has an acceptable verified identity;
* the replacement worker is suitable for the service;
* the visit has not been completed or cancelled;
* the Place access policy allows provider reassignment;
* notification and escalation preferences are available.

The Place should not need to reapprove the entire care arrangement solely because the provider changes the assigned worker, unless the Place policy requires named-worker approval.

## 6. Replacement types

### 6.1 Planned replacement

A replacement made sufficiently early that normal notifications and credential updates can occur before arrival.

### 6.2 Short-notice replacement

A replacement made shortly before the visit.

The resident may have limited time to review the updated worker details.

### 6.3 Replacement after missed arrival

The original worker fails to attend or reports inability to attend, and another worker is assigned.

### 6.4 Replacement after access failure

The original worker attends but cannot complete the visit, and a replacement is assigned.

### 6.5 Mid-visit replacement

A second worker takes over after the visit has started.

This is expected to be uncommon and may require:

* explicit provider confirmation;
* a custody-style handover of visit responsibility;
* new access authority;
* updated resident approval;
* separate arrival and departure records.

The first baseline may treat mid-visit replacement as an exception rather than a normal flow.

## 7. Assignment

An **Assignment** associates a Service Agent with a Service Visit.

For this use case, the assignment should identify at least:

* the Service Visit;
* the care provider;
* the assigned worker;
* the assignment status;
* the effective time;
* any expiry;
* whether it supersedes another assignment.

Possible assignment statuses include:

* proposed;
* active;
* superseded;
* withdrawn;
* completed;
* expired.

Only an active assignment should normally support new Place access.

The care provider should remain authoritative for assignment changes.

## 8. Assignment history

The visit should preserve an assignment history sufficient to show:

* who was originally assigned;
* when the original assignment was created;
* who issued the replacement;
* when the replacement became effective;
* why the replacement occurred where an appropriate non-sensitive reason may be recorded;
* when the previous assignment was withdrawn or superseded;
* which worker actually performed the visit.

The Place does not need access to detailed employment or operational reasons unless they affect safety or access policy.

## 9. Identity and suitability

### 9.1 Replacement-worker identity

The replacement worker should meet the same identity-assurance requirement as the original worker.

A lower standard should not be used merely because the replacement is urgent.

### 9.2 Provider relationship

The replacement worker should be recognised as acting for the care provider.

### 9.3 Suitability assertion

The care provider may assert that the replacement worker is suitable for the visit.

This may cover:

* role;
* training;
* qualification;
* vetting;
* employment or contractual status;
* service-specific suitability.

The Place should normally rely on the provider’s suitability decision rather than receiving detailed workforce records.

### 9.4 Named-worker restrictions

Some residents may accept only:

* named workers;
* previously known workers;
* workers of a stated role;
* workers satisfying another preference.

The Place policy may therefore:

* accept provider substitutions automatically;
* require resident approval;
* require representative approval;
* reject replacements not previously approved.

OSDI should support these choices without assuming one universal policy.

## 10. Authority and credential changes

When a replacement is activated:

* the original worker’s unused authority should be revoked or superseded;
* previously issued visit credentials should become invalid where practical;
* the replacement worker should receive new or updated authority;
* the new authority should remain limited to the same Place, Visit, time, and permitted actions unless explicitly changed;
* any access already completed by the original worker should remain in the audit record.

A replacement assignment should not copy unrelated permissions from another visit.

## 11. Notifications

The Place policy may define who receives replacement notifications.

Possible recipients include:

* care recipient;
* resident;
* authorised representative;
* family member;
* care coordinator;
* Place Operator.

A notification may include:

* that the worker has changed;
* the replacement worker’s name or display identity;
* the care provider;
* the expected arrival time;
* whether approval is required;
* a contact route for questions or concerns.

The notification should not expose unnecessary workforce or personal information.

## 12. Relevant Place capabilities

UC008 uses the same Place capabilities as UC007, with additional emphasis on:

### 12.1 Assignment-update handling

The ability to receive or recognise a changed Service Agent assignment.

### 12.2 Credential revocation

The ability to reject authority associated with the superseded worker.

### 12.3 Replacement notification

The ability to inform the resident or representative that the assigned worker has changed.

### 12.4 Replacement approval

The ability to approve or reject the replacement where the Place policy requires it.

### 12.5 Current-assignment query

The ability to determine which worker is currently assigned to the visit.

The Place should avoid disclosing a wider provider workforce list.

## 13. Normal journey

### Step 1 — Visit is scheduled

The care provider creates a scheduled care visit.

### Step 2 — Original worker is assigned

Worker A is associated with the Service Visit.

### Step 3 — Place receives the original assignment

The Place platform receives enough information to recognise Worker A as the assigned Service Agent.

### Step 4 — Replacement becomes necessary

The care provider determines that Worker A will not perform the visit.

### Step 5 — Replacement worker is selected

The provider selects Worker B and confirms that Worker B is suitable.

### Step 6 — New assignment is issued

The provider issues an updated assignment associating Worker B with the visit.

The assignment indicates that it supersedes Worker A’s assignment.

### Step 7 — Original assignment is withdrawn

Worker A’s assignment becomes superseded, withdrawn, or otherwise inactive.

Any unused access authority should be revoked.

### Step 8 — Place platform is updated

The Place platform receives or retrieves the changed assignment.

It checks that:

* the update originates from the recognised care provider;
* the Service Visit is valid;
* Worker B has an acceptable identity;
* Worker B is currently assigned;
* the replacement is permitted by Place policy.

### Step 9 — Resident or representative is notified

A replacement notification is sent according to the Place policy.

### Step 10 — Approval is obtained where required

If the policy requires replacement approval, the resident or representative may:

* approve Worker B;
* reject Worker B;
* request provider contact;
* cancel or reschedule the visit.

### Step 11 — Replacement authority is prepared

Authority is created or updated for Worker B.

It may permit:

* arrival reporting;
* resident notification;
* gate access;
* entrance access;
* visit start;
* departure reporting;
* exception reporting.

### Step 12 — Replacement worker approaches

Worker B receives the visit assignment and approaches the Place.

### Step 13 — Replacement worker reports arrival

Worker B reports arrival through the provider or NHS365 application.

### Step 14 — Current assignment is validated

The Place checks that Worker B, not Worker A, is currently assigned.

### Step 15 — Entry proceeds under the scheduled policy

The resident opens the entrance, approves entry, or the Place applies an authorised assisted-entry process.

### Step 16 — Visit is performed

Worker B provides the scheduled care under the provider’s normal procedures.

### Step 17 — Departure is reported

Worker B exits and reports departure.

### Step 18 — Entrance is secured

The Place confirms that the entrance is closed and secure where supported.

### Step 19 — Visit is completed

The visit record indicates that Worker B performed the visit.

The assignment history preserves that Worker A was originally assigned and later replaced.

## 14. Example status sequence

A replacement journey may be represented as:

```text
Visit Scheduled
    ↓
Worker A Assigned
    ↓
Replacement Required
    ↓
Worker B Assigned
    ↓
Worker A Assignment Superseded
    ↓
Resident Notified
    ↓
Replacement Approved or Automatically Accepted
    ↓
Worker B Approaching
    ↓
Worker B Arrived
    ↓
Entry Authorised
    ↓
Visit Started
    ↓
Worker B Departed
    ↓
Completed
```

The Service Visit remains the same visit unless the provider cancels it and creates a new one.

## 15. Alternative and exception journeys

### 15.1 Replacement update arrives after original credential issuance

The original credential should be revoked or rejected after the replacement becomes effective.

Where immediate revocation cannot be guaranteed, the Place may require an online current-assignment check before main-residence access.

### 15.2 Original worker arrives after being replaced

Worker A may still arrive because of delayed communication.

The Place should:

* identify that Worker A is no longer assigned;
* deny automated access;
* provide a safe contact route;
* notify the care provider;
* avoid disclosing unnecessary details about Worker B.

### 15.3 Replacement worker arrives before the Place receives the update

The Place may:

* query the care provider;
* request a signed assignment assertion;
* ask the worker to wait;
* seek resident approval;
* deny automated access until the assignment is confirmed.

A worker’s general provider affiliation should not by itself prove the replacement assignment.

### 15.4 Resident rejects the replacement

If Place policy permits rejection:

* access should not be granted;
* the provider should be notified;
* another worker may be assigned;
* the visit may be delayed, rescheduled, or cancelled;
* safeguarding or welfare procedures may still apply.

### 15.5 Resident cannot respond

The Place applies the standing access policy.

A provider-authorised replacement may be permitted if the policy allows provider substitutions without immediate resident approval.

Otherwise, escalation may be required.

### 15.6 Replacement worker has a different role

The provider should ensure that the new worker is suitable for the planned care.

If the Place policy restricts acceptable roles, new approval may be required.

### 15.7 Multiple replacements occur

The assignment history should preserve each change.

Only the latest active assignment should support access.

### 15.8 Worker is reassigned during travel

The original worker’s app should be updated and any unused credential revoked.

The replacement should receive the active assignment.

### 15.9 Original worker already entered

If Worker A has already entered, replacing them is no longer a simple pre-visit reassignment.

The provider may need to:

* complete the visit with Worker A;
* add Worker B as a second worker;
* arrange a controlled handover;
* end Worker A’s authority after departure.

The first OSDI baseline may report this as a visit exception.

### 15.10 Replacement worker arrives outside the time window

The normal early or late-arrival policy applies.

The replacement status alone should not broaden the Time Window.

### 15.11 Provider cannot be reached

If assignment confirmation is unavailable:

* resident-controlled entry may still occur;
* automated assisted entry should follow the Place’s offline policy;
* access may be denied until confirmation is available.

### 15.12 Suspicious reassignment

The Place may treat a reassignment as suspicious if:

* the provider signature is invalid;
* several rapid changes occur;
* the replacement identity cannot be verified;
* the visit details do not match;
* the original worker also requests access.

The Place may deny access and raise an alert.

## 16. Evidence and audit

The replacement process should record enough information to answer:

* which visit was affected;
* who was originally assigned;
* who issued the replacement;
* who became the active worker;
* when the change became effective;
* whether the resident or representative was notified;
* whether approval was required and obtained;
* when the previous authority was revoked;
* which worker arrived;
* which worker entered;
* which worker completed the visit;
* what exceptions occurred.

The audit record should avoid unnecessary employment or health details explaining why the original worker was unavailable.

## 17. Privacy considerations

The implementation should minimise disclosure of:

* the original worker’s reason for absence;
* workforce schedules;
* private employment information;
* detailed suitability or vetting records;
* resident vulnerability;
* care-plan details;
* household routines;
* unrelated provider staff.

The resident may need enough information to recognise the replacement but not unrestricted access to the worker’s personal records.

## 18. Security considerations

The implementation should guard against:

* forged reassignment;
* use of an old assignment after replacement;
* race conditions between old and new credentials;
* two workers gaining access for one assignment;
* provider-account compromise;
* reassignment to an unsuitable or unverified person;
* worker impersonation;
* notification spoofing;
* approval obtained from an unauthorised person;
* use of general provider membership as proof of visit assignment;
* disclosure of worker or resident information during rejection.

For main-residence access, the Place should normally validate the current assignment close to the time of entry.

## 19. Current-practice alignment

Care providers already reassign visits through rostering and scheduling systems.

OSDI should not require a new workforce-management process.

The provider may continue to:

* identify staffing problems;
* select a replacement;
* verify suitability;
* update the rota;
* notify the worker;
* record the operational reason.

OSDI or NHS365 may support:

* receiving the active assignment;
* updating Place authority;
* revoking superseded access;
* notifying the resident;
* obtaining replacement approval where required;
* validating the replacement at arrival;
* recording which worker completed the visit.

## 20. Comparison with UC007

UC007 establishes the normal scheduled-care journey.

UC008 validates that the same Service Visit can survive a change of Service Agent.

The main additional needs are:

* explicit Assignment;
* assignment status;
* assignment history;
* supersession;
* credential revocation;
* current-assignment validation;
* replacement notification;
* optional replacement approval.

UC008 suggests that Assignment should become an explicit OSDI Core concept rather than remaining only an attribute of a Service Visit.

## 21. Common OSDI needs identified

UC008 suggests that an initial OSDI baseline may need to support:

* creation of a Service Agent Assignment;
* activation and withdrawal of an Assignment;
* superseding one Assignment with another;
* provider authority to issue assignments;
* current-assignment lookup;
* assignment-specific credentials;
* authority revocation;
* resident or representative notification;
* replacement approval policy;
* assignment history;
* audit of the worker who actually performed the visit.

## 22. Proposed NHS365 starter implementation

### 22.1 Care-provider template

The provider template may allow an early partner to:

* create scheduled visits;
* assign workers;
* replace assigned workers;
* indicate whether the replacement is urgent;
* provide a non-sensitive replacement reason category;
* confirm replacement suitability;
* notify NHS365 of the updated assignment;
* view assignment and access results.

### 22.2 Care-worker application

The application may:

* remove superseded visits from the original worker’s active list;
* display the visit to the replacement worker;
* refresh visit credentials;
* show current Place instructions;
* report approaching and arrival;
* present the active assignment;
* report access results and completion.

### 22.3 Resident application

The resident or representative may:

* receive a replacement notification;
* view the replacement worker’s approved display identity;
* approve or reject the replacement where policy requires;
* contact the care provider;
* change future replacement preferences.

### 22.4 NHS365 platform services

The platform may provide:

* Assignment creation and versioning;
* supersession handling;
* provider-signature validation;
* worker identity linking;
* credential revocation;
* replacement notifications;
* approval workflow;
* current-assignment validation;
* audit history.

### 22.5 Site agent and access integration

The site agent may receive only the currently valid authority.

It should not need the full assignment history.

At access time, it may verify:

* visit identifier;
* worker identifier;
* active authority;
* expiry;
* requested action.

## 23. Starter demonstration

A first demonstration could follow this sequence:

1. A care visit is scheduled for Worker A.
2. Worker A appears in the resident and provider views.
3. The provider replaces Worker A with Worker B.
4. NHS365 marks Worker A’s assignment as superseded.
5. Worker A’s temporary access token is invalidated.
6. Worker B receives the visit in the care-worker application.
7. The resident receives a replacement notification.
8. The resident approves Worker B.
9. Worker A attempts access and is rejected.
10. Worker B reports arrival.
11. NHS365 validates Worker B as the active assignment.
12. Worker B receives authorised entry.
13. Worker B completes the visit.
14. The audit record shows both assignments and identifies Worker B as the performing worker.

## 24. Questions for refinement

1. Should Assignment become an explicit OSDI Core concept?
2. Who is permitted to issue or change an Assignment?
3. Must every replacement explicitly supersede a previous Assignment?
4. How should several active workers be represented for a two-person visit?
5. Should a Place cache assignments or query the provider at access time?
6. How quickly must superseded credentials become invalid?
7. Should the resident be able to reject all replacements or only certain replacements?
8. What identity information should be shown to the resident?
9. Should the replacement reason be shared with the Place?
10. How should urgent replacements work when the resident cannot respond?
11. Can the same credential be reissued to a replacement worker, or must every worker receive a distinct credential?
12. What happens if both original and replacement workers arrive?
13. Should assignment changes create a new Service Visit or update the existing Visit?
14. How should mid-visit replacement be handled?
15. How should temporary provider-system outages affect replacement validation?
16. Does Approval need to become a distinct core concept?
17. Does Access Policy need to become a distinct core concept?
18. Which replacement rules belong in OSDI Core and which belong in a care profile?

## 25. Concepts validated

UC008 validates:

* Service Journey;
* Service Visit;
* Service Provider;
* Service Agent;
* Identity;
* Credential;
* Authority;
* Time Window;
* Status;
* Evidence;
* Exception;
* Completion;
* Cancellation.

It strongly supports adding:

### Assignment

A time-bounded association between a Service Agent and a Service Visit, issued or confirmed by an authorised party.

### Supersession

The replacement of an existing Assignment, Authority, Credential, or instruction with a newer valid version.

### Approval

A decision by an authorised person or system allowing a proposed Action, Assignment, or exception path to proceed.

### Access Policy

Rules defined for a Place that determine how identity, Assignment, time, Approval, and other conditions are evaluated before access is granted.

These concepts should be tested further in UC009 and UC010 before being finalised.

## 26. Initial conclusion

UC008 demonstrates that a scheduled Service Visit should remain stable even when the assigned Service Agent changes.

The Place does not need to understand the provider’s complete rostering process.

It needs to know:

* which provider controls the visit;
* which Assignment is currently active;
* whether the worker’s identity is acceptable;
* whether the replacement satisfies the Place policy;
* which Authority is currently valid;
* whether earlier authority has been revoked.

This supports a simple separation of responsibilities:

* the care provider selects and assigns suitable workers;
* the Place controls physical access;
* OSDI coordinates the current Assignment, Authority, Approval, Status, and audit information needed for them to cooperate.
