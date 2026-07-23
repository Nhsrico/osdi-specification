# UC009 — Unplanned Authorised Care Visit

**Document status:** Informative working draft
**Specification version:** 0.1.0-draft
**Use-case identifier:** UC009

## 1. Purpose

This use case describes a legitimate care visit that was not scheduled through the normal advance process but is authorised before access is granted.

The visit may arise because of:

* a same-day welfare concern;
* a missed earlier visit;
* a request from the care recipient or authorised representative;
* an urgent medication or support need;
* a care-provider operational issue;
* a follow-up visit requested after another service interaction;
* another non-emergency circumstance requiring prompt attendance.

The intended outcome is that an authorised care provider can create or confirm an unplanned visit, assign a suitable worker, and request access to a Place without weakening the normal identity, assignment, authority, and audit controls.

This use case is not intended to cover immediate emergency entry by police, fire, ambulance, or another emergency responder. That is addressed separately in UC010.

## 2. Example scenario

A resident was expected to receive a care visit earlier in the day, but the visit could not be completed.

Later, the care provider determines that a worker should attend the Place as soon as practical to perform a welfare check.

No advance visit exists in the normal schedule.

The provider:

* creates an unplanned visit;
* records the reason category;
* assigns Worker B;
* confirms that Worker B is suitable;
* provides a short expected arrival window;
* requests access under the resident’s existing care arrangement.

The resident’s Place is configured to permit unplanned visits from recognised providers only when one of the following applies:

* the resident approves the visit;
* an authorised representative approves the visit;
* a standing care policy allows a provider to create certain categories of unplanned visit;
* an escalation rule authorises attendance.

Worker B arrives and presents the current assignment.

The Place validates:

* the care provider;
* the worker identity;
* the new visit;
* the assignment;
* the stated authority basis;
* the permitted time;
* the Place access policy.

If resident or representative approval is required, access is not granted until approval is received.

The worker enters, completes the visit, reports departure, and the Place records the access interaction.

## 3. Intended outcome

The use case is successfully completed when:

* a recognised care provider creates or confirms a valid unplanned visit;
* the reason and authority basis are recorded at an appropriate level;
* a suitable worker is assigned;
* the Place evaluates the request under its Access Policy;
* required Approval is obtained;
* access is granted only for the new Visit;
* the worker reports arrival and departure;
* the Place is left secure;
* the visit is completed or an exception is recorded;
* the unplanned nature of the visit remains auditable.

## 4. Participants

### 4.1 Care recipient

The person intended to receive the care or welfare support.

### 4.2 Resident

A person living at or occupying the Place.

The resident may be the care recipient.

### 4.3 Care provider

The organisation responsible for creating, authorising, and coordinating the unplanned visit.

### 4.4 Care worker

The Service Agent assigned to perform the visit.

### 4.5 Requesting party

The party that causes the unplanned visit to be considered.

This may be:

* the care recipient;
* a family member;
* an authorised representative;
* the care provider;
* a care coordinator;
* another recognised health or social-care organisation;
* another approved party.

### 4.6 Place operator

The person or organisation responsible for controlling interaction at the Place.

### 4.7 Authorised representative

A person or organisation permitted to approve or manage access on behalf of the care recipient or Place Operator.

### 4.8 Place platform

The system responsible for evaluating the visit against the Place Access Policy and coordinating Place capabilities.

### 4.9 Care-management system

The provider system responsible for creating and recording the unplanned visit.

## 5. Difference from a scheduled visit

A scheduled visit normally exists before the worker is assigned and before the expected arrival period begins.

An unplanned visit may be created:

* shortly before arrival;
* while the worker is travelling;
* after an earlier failed visit;
* in response to a new concern;
* at the request of the resident or representative.

The absence of an advance schedule should not mean that the visit is unauthorised.

However, an unplanned visit requires a clear authority basis and should not be treated as equivalent to unrestricted provider access.

## 6. Relationship to emergency access

An unplanned care visit is urgent or short-notice, but not necessarily an emergency.

The normal expectation remains that:

* the provider is recognised;
* the worker is identified;
* an Assignment exists;
* the Place Access Policy is applied;
* required Approval is obtained;
* access is limited and auditable.

Emergency access may permit broader or faster action under a different authority basis.

A provider should not label an ordinary operational problem as an emergency merely to bypass normal controls.

## 7. Assumptions and preconditions

Before access is granted:

* an existing care relationship or other recognised basis exists;
* the care provider is trusted or recognised;
* the provider is permitted to request unplanned visits of the relevant type;
* the care worker has an acceptable identity;
* the worker is suitable for the visit;
* an Assignment has been created;
* the intended Place is known;
* an authority basis has been stated;
* the Place Access Policy can evaluate the request;
* communication or escalation routes are available;
* the visit has not been cancelled or superseded.

Where no prior care relationship exists, stronger Approval or a different onboarding process may be required.

## 8. Authority basis

Every unplanned visit should identify why the visit may legitimately proceed.

Possible authority bases include:

* direct request by the care recipient;
* Approval by an authorised representative;
* standing care agreement;
* provider escalation under an agreed care plan;
* welfare-check policy;
* missed-visit follow-up policy;
* request by another recognised care or health organisation;
* another defined basis.

The authority basis should be specific enough for the Place to evaluate the request without disclosing unnecessary care details.

Examples of suitable reason categories include:

* resident requested;
* missed-visit follow-up;
* welfare concern;
* urgent support requested;
* provider-directed follow-up;
* representative requested.

Detailed clinical or safeguarding information should remain in the appropriate care system.

## 9. Unplanned Visit creation

The provider should create a distinct Service Visit rather than attempting to reuse an unrelated scheduled visit.

The new Visit should include:

* Visit identifier;
* provider;
* Place;
* assigned worker;
* reason category;
* authority basis;
* creation time;
* permitted arrival window;
* expected duration where known;
* requested access actions;
* Approval requirement;
* expiry;
* link to any earlier Visit where relevant.

A missed scheduled visit may therefore lead to a new linked unplanned Visit.

## 10. Assignment

The unplanned Visit should have an explicit active Assignment.

The Assignment should identify:

* care provider;
* assigned worker;
* Visit;
* effective time;
* expiry;
* status.

General employment by the provider is not sufficient proof that the worker is assigned to this unplanned Visit.

## 11. Access Policy

The Place Access Policy should define how unplanned visits are handled.

Possible policy options include:

### 11.1 Resident Approval required

No automated entry is granted until the resident approves.

### 11.2 Representative Approval required

An authorised representative may approve when the resident cannot respond.

### 11.3 Provider-authorised categories

The Place may allow a recognised provider to create specific categories of unplanned Visit under a standing care arrangement.

### 11.4 Assisted-entry restrictions

Assisted entry may be allowed only:

* after a defined contact sequence;
* for specified reason categories;
* for specified providers;
* within defined hours;
* with representative or provider confirmation.

### 11.5 Named-worker restrictions

The Place may permit unplanned visits only from previously approved workers.

### 11.6 No unplanned automated access

The Place may require the resident to open the entrance for every unplanned Visit.

OSDI should support these choices without imposing a single policy.

## 12. Approval

Approval may be required before the Visit becomes access-eligible.

Approval may be given by:

* care recipient;
* resident;
* authorised representative;
* Place Operator;
* another authorised organisation;
* a standing policy rule.

Approval should identify:

* what is approved;
* who approved it;
* when;
* for which Visit;
* any conditions;
* expiry or revocation.

Approval of one unplanned Visit should not create standing authority for later visits unless explicitly stated.

## 13. Relevant Place capabilities

UC009 uses the capabilities identified in UC007, with additional emphasis on:

* short-notice Visit recognition;
* Approval request;
* current Assignment validation;
* reason-category display;
* resident or representative contact;
* temporary Authority generation;
* escalation;
* Access Policy evaluation;
* Visit expiry;
* revocation.

## 14. Information associated with the Visit

The Visit may use:

* Visit identifier;
* provider identity;
* worker identity;
* Assignment reference;
* Place identifier;
* reason category;
* authority basis;
* related earlier Visit reference;
* creation time;
* permitted arrival window;
* expected duration;
* requested access actions;
* Approval status;
* relevant Place instructions;
* arrival time;
* departure time;
* final status;
* exception references;
* limited Place-interaction evidence.

The Place should not normally receive:

* detailed medical reason;
* full safeguarding concern;
* clinical notes;
* complete care plan;
* internal staffing explanation;
* unrelated family information.

## 15. Normal journey

### Step 1 — Need for unplanned visit is identified

A legitimate need is identified by the resident, representative, care provider, or another recognised party.

### Step 2 — Provider evaluates the request

The care provider determines:

* whether a Visit is required;
* the urgency;
* the appropriate worker role;
* whether the request fits an agreed care arrangement;
* what authority basis applies.

### Step 3 — Unplanned Visit is created

The provider creates a new Service Visit.

The Visit is marked as unplanned or short-notice.

### Step 4 — Worker is assigned

The provider assigns a suitable care worker.

### Step 5 — Visit is shared with the Place

The Place platform receives enough information to recognise and evaluate the Visit.

### Step 6 — Place Access Policy is evaluated

The Place determines:

* whether the provider may request this Visit type;
* whether resident or representative Approval is required;
* whether assisted entry is allowed;
* the permitted Time Window;
* the requested Capabilities;
* any additional conditions.

### Step 7 — Approval is requested where required

The resident or representative receives a clear request showing:

* care provider;
* worker display identity where available;
* reason category;
* expected arrival;
* requested access;
* contact route.

### Step 8 — Visit is approved or accepted by policy

The Visit becomes eligible for access.

Approval may be explicit or derived from a standing policy.

### Step 9 — Temporary Authority is prepared

Authority is created for:

* the assigned worker;
* the specific Visit;
* the Place;
* the permitted Time Window;
* the required access Actions.

### Step 10 — Worker approaches

The worker receives the active Visit and relevant instructions.

### Step 11 — Worker reports arrival

The worker reports arrival through the provider or NHS365 application.

### Step 12 — Visit and Assignment are validated

The Place checks:

* provider;
* worker identity;
* active Assignment;
* authority basis;
* Approval;
* current time;
* requested access;
* Visit status.

### Step 13 — Resident contact sequence occurs

Where required, the worker:

* rings;
* uses intercom;
* sends a notification;
* calls the resident;
* contacts the representative or provider.

### Step 14 — Entry is authorised

Entry occurs according to the Place policy.

### Step 15 — Visit starts

The worker reports Visit start.

### Step 16 — Care or welfare service is provided

The worker follows provider procedures.

Detailed care information remains in the provider system.

### Step 17 — Departure is reported

The worker leaves and reports departure.

### Step 18 — Entrance is secured

The Place confirms closure or lock state where supported.

### Step 19 — Visit completes

The Visit is marked:

* completed;
* completed with exception;
* failed;
* cancelled;
* escalated.

### Step 20 — Authority ends

Temporary Authority expires or is revoked.

## 16. Example status sequence

```text id="r5k2cz"
Need Identified
    ↓
Provider Review
    ↓
Unplanned Visit Created
    ↓
Worker Assigned
    ↓
Approval Requested
    ↓
Approved
    ↓
Worker Approaching
    ↓
Worker Arrived
    ↓
Entry Authorised
    ↓
Visit Started
    ↓
Worker Departed
    ↓
Completed
```

Alternative states may include:

```text id="frw4da"
Rejected
Expired
Unable to Contact Resident
Unable to Access
Cancelled
Escalated
```

## 17. Alternative and exception journeys

### 17.1 Resident approves directly

The resident accepts the Visit through the application, intercom, or another recognised method.

### 17.2 Representative approves

The resident cannot respond, but an authorised representative approves the Visit.

### 17.3 Standing policy permits the Visit

The Place accepts the Visit automatically because:

* the provider is recognised;
* the reason category is allowed;
* the worker is assigned;
* the Time Window is acceptable;
* other policy conditions are satisfied.

### 17.4 Approval is refused

If Approval is refused:

* access should not be granted;
* the provider should be informed;
* the refusal should be recorded;
* the provider may contact the resident or follow care procedures.

### 17.5 No one responds to Approval request

The Place applies its policy.

This may result in:

* retry;
* provider contact;
* representative escalation;
* assisted entry;
* Visit expiry;
* no access.

### 17.6 Worker arrives before Approval

The worker may wait or contact the provider.

Automated entry should not proceed until the required Approval exists.

### 17.7 Visit expires before arrival

If the worker does not arrive within the permitted period:

* the Visit may expire;
* Authority should become invalid;
* the provider may issue an updated Visit or extension;
* the resident should be notified where appropriate.

### 17.8 Different worker arrives

The Place should validate the current Assignment.

A recognised provider employee without the active Assignment should not receive automated entry.

### 17.9 Provider changes the reason category

A material change may require the Access Policy to be evaluated again.

### 17.10 Provider requests broader access

A request for broader access than the Place policy permits should be rejected or require new Approval.

### 17.11 Resident requests the Visit during a call

The care provider may create the Visit while speaking with the resident.

The resident’s direct request may satisfy the Approval requirement where recorded appropriately.

### 17.12 Earlier scheduled Visit was missed

The unplanned Visit may link to the missed Visit.

The original Visit remains recorded as missed, failed, or incomplete.

The new Visit has its own Assignment and Authority.

### 17.13 Access system is unavailable

The Place may support:

* resident-operated entry;
* key-safe process;
* locally verifiable credential;
* provider-assisted confirmation;
* no access.

### 17.14 Worker finds an urgent concern

The worker may escalate through provider or emergency procedures.

OSDI may record that escalation occurred without storing sensitive details.

### 17.15 Unplanned Visit is cancelled

Cancellation should:

* revoke Authority;
* invalidate unused Credentials;
* notify the worker and Place;
* preserve the audit record.

### 17.16 Repeated unplanned Visit requests

The Place may detect repeated or unusual requests and require:

* stronger Approval;
* provider contact;
* review by the Place Operator;
* temporary suspension.

## 18. Evidence and audit

The Visit record should be able to answer:

* who requested or initiated the Visit;
* which provider created it;
* why it was categorised as unplanned;
* what authority basis applied;
* who was assigned;
* whether Approval was required;
* who approved it;
* when the worker arrived;
* how access was granted;
* when the worker departed;
* whether the entrance was secured;
* what exceptions occurred.

The audit record should not contain more care detail than is necessary to explain the Place interaction.

## 19. Privacy considerations

The implementation should minimise disclosure of:

* detailed welfare concern;
* clinical reason;
* safeguarding information;
* resident vulnerability;
* family circumstances;
* worker employment information;
* internal Place details;
* unrelated access history.

The resident should receive enough information to make an informed access decision without receiving unnecessary provider or worker data.

## 20. Security considerations

The implementation should guard against:

* false creation of unplanned Visits;
* misuse of an existing care relationship;
* forged provider requests;
* generic provider access without Assignment;
* manipulation of reason categories;
* bypass of Approval requirements;
* repeated access requests intended to pressure a resident;
* use of expired or cancelled Visit credentials;
* use at the wrong Place;
* broader access than the approved Visit requires;
* unplanned Visit being misrepresented as an emergency;
* compromise of representative Approval.

An unplanned Visit should not weaken identity, Assignment, or Place Authority controls.

## 21. Current-practice alignment

Care providers already perform short-notice and unplanned visits.

OSDI should allow them to retain existing processes for:

* deciding whether a Visit is needed;
* selecting a suitable worker;
* recording the care reason;
* contacting the resident;
* documenting care outcomes;
* managing safeguarding.

OSDI or NHS365 may support:

* Visit creation;
* Assignment;
* Place notification;
* Approval;
* Access Policy evaluation;
* temporary Authority;
* arrival and departure status;
* limited access evidence;
* exceptions.

## 22. Comparison with UC007 and UC008

UC007 covers a normal scheduled Visit.

UC008 covers replacement of the assigned worker while the Visit remains scheduled.

UC009 introduces:

* Visit creation at short notice;
* explicit authority basis;
* explicit Access Policy evaluation;
* Approval before access;
* Visit expiry;
* distinction between unplanned and emergency access;
* linkage to an earlier failed or missed Visit.

UC009 strongly supports treating the following as explicit concepts:

* Assignment;
* Approval;
* Access Policy;
* Authority Basis;
* Supersession or linkage between related Visits.

## 23. Common OSDI needs identified

UC009 suggests that an initial OSDI baseline may need to support:

* short-notice Service Visit creation;
* Visit type or scheduling classification;
* authority basis;
* active Assignment;
* Approval request and result;
* Place Access Policy evaluation;
* temporary Authority;
* Visit expiry;
* linked Visits;
* cancellation;
* arrival and departure;
* exception and escalation;
* audit.

## 24. Proposed NHS365 starter implementation

### 24.1 Care-provider application template

The provider template may allow a partner to:

* create an unplanned Visit;
* select a reason category;
* link an earlier missed Visit;
* assign a worker;
* request resident or representative Approval;
* view Approval status;
* receive access and completion updates;
* cancel or extend the Visit.

### 24.2 Care-worker application

The worker application may provide:

* active unplanned Visit display;
* Visit reason category;
* Place instructions;
* Approval status;
* approaching and arrival reporting;
* identity and Assignment presentation;
* access request;
* escalation options;
* departure and completion reporting.

### 24.3 Resident application

The resident or representative may:

* receive an Approval request;
* view provider and worker information;
* see the reason category;
* approve or reject the Visit;
* contact the provider;
* specify conditions;
* revoke Approval before entry;
* view completion status.

### 24.4 NHS365 platform services

The platform may provide:

* unplanned Visit creation;
* provider-authority validation;
* Assignment;
* Approval workflow;
* Access Policy evaluation;
* temporary Authority;
* credential generation and revocation;
* Visit expiry;
* linked-Visit references;
* notifications;
* audit.

### 24.5 Site agent

The site agent may receive only:

* active Visit identifier;
* current worker identity reference;
* valid Authority;
* permitted access Action;
* expiry.

The agent should not receive the detailed care reason.

## 25. Starter demonstration

A first demonstration could follow this sequence:

1. A scheduled morning Visit is recorded as missed.
2. The provider creates an unplanned welfare-check Visit.
3. The new Visit links to the missed Visit.
4. Worker B is assigned.
5. The resident receives an Approval request showing the provider, worker, reason category, and expected arrival.
6. The resident approves the Visit.
7. NHS365 creates temporary Authority for Worker B.
8. Worker B reports approaching and arrival.
9. NHS365 validates provider, Visit, Assignment, Approval, Place, and time.
10. The worker requests entry.
11. The site agent unlocks the entrance.
12. The worker enters and starts the Visit.
13. The worker later reports departure.
14. The entrance is confirmed secure.
15. The Visit is completed.
16. Temporary Authority expires.

A second demonstration could show representative Approval when the resident cannot respond.

## 26. Questions for refinement

1. What minimum information must identify the authority basis?
2. Which unplanned Visit categories may be pre-authorised by policy?
3. When is explicit resident Approval always required?
4. Can provider Approval ever substitute for resident or representative Approval?
5. How long should an unplanned Visit remain valid?
6. Should every unplanned Visit have a distinct identifier?
7. How should a missed scheduled Visit link to a follow-up Visit?
8. Should the resident see the detailed reason or only a reason category?
9. Can an unplanned Visit be converted into an emergency Visit?
10. Who may create unplanned Visits?
11. How should repeated requests from the same provider be rate-limited or reviewed?
12. Should Access Policy be evaluated centrally, locally, or both?
13. How should Approval revocation work after the worker begins travelling?
14. What happens if Approval is revoked after entry?
15. Does Authority Basis need to become an explicit OSDI Core concept?
16. Which rules belong in OSDI Core and which belong in the care profile?

## 27. Concepts validated

UC009 validates:

* Service Visit;
* Service Provider;
* Service Agent;
* Place;
* Identity;
* Credential;
* Assignment;
* Authority;
* Approval;
* Access Policy;
* Time Window;
* Status;
* Evidence;
* Exception;
* Completion;
* Cancellation.

It adds support for:

### Authority Basis

The recognised reason, agreement, policy, request, or delegated power that justifies creation of Authority for a Service Visit.

### Visit Classification

A simple indication of whether a Visit is scheduled, unplanned, urgent, or emergency.

### Related Visit

A reference linking one Service Visit to another, such as a follow-up to a missed Visit.

These concepts should be tested against emergency access before being finalised.

## 28. Initial conclusion

UC009 demonstrates that a legitimate care Visit can be created at short notice without abandoning the OSDI trust model.

The essential requirements remain:

* recognised provider;
* explicit Visit;
* assigned worker;
* clear authority basis;
* Place Access Policy;
* Approval where required;
* limited temporary Authority;
* arrival and departure status;
* auditable completion or exception.

The distinction between unplanned and emergency access is important.

An unplanned Visit remains subject to normal identity, Assignment, Approval, and Place policy controls, even when it must be arranged quickly.
