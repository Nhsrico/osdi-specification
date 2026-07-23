# UC010 — Urgent or Emergency Access

**Document status:** Informative working draft
**Specification version:** 0.1.0-draft
**Use-case identifier:** UC010

## 1. Purpose

This use case describes access to a Place where delay may create a significant risk to life, health, safety, property, or essential welfare.

It covers two related but distinct situations:

* an **urgent service visit**, where rapid attendance is required but normal identity, assignment, and approval controls can still operate;
* an **emergency access event**, where immediate action may be required and normal approval may be unavailable, inappropriate, or lawfully overridden.

Examples include:

* an urgent welfare check;
* a medical emergency;
* fire or smoke response;
* police or emergency-service attendance;
* a triggered personal alarm;
* suspected incapacitation;
* gas, water, or electrical danger;
* a serious access or security incident;
* another event requiring immediate intervention.

The intended outcome is that authorised responders can obtain only the access needed to address the urgent or emergency situation, while preserving accountability, limiting unnecessary disclosure, and preventing emergency procedures from becoming a route for ordinary access.

This use case does not define the legal powers of emergency services, care providers, landlords, utilities, or public authorities. Applicable law and established emergency procedures remain authoritative.

## 2. Key distinction

OSDI should distinguish between urgency and emergency.

### 2.1 Urgent access

An urgent access request requires prompt action but still permits normal or accelerated validation.

An urgent visit should normally have:

* a recognised Service Provider;
* an identified Service Agent;
* an explicit Service Visit;
* an Assignment;
* an Authority Basis;
* Place Access Policy evaluation;
* Approval where required and available;
* limited temporary Authority.

Examples include:

* a same-day welfare check;
* urgent medication assistance;
* a care provider returning after a missed visit;
* an urgent maintenance response to prevent damage.

### 2.2 Emergency access

Emergency access may be required where:

* life or serious health is at risk;
* fire, flooding, gas, or another immediate hazard is suspected;
* the resident cannot respond;
* waiting for ordinary Approval would create unacceptable risk;
* an authorised emergency responder is exercising a recognised emergency power or procedure.

Emergency access may use exceptional Authority, but it should still be:

* attributable where practical;
* limited to the emergency purpose;
* time-bound;
* auditable;
* reviewable after the event.

Emergency classification should not be used merely to avoid normal access procedures.

## 3. Example scenario

A vulnerable resident has a personal alarm service connected to NHS365.

The alarm service receives:

* a personal alarm activation;
* no response from the resident;
* supporting information indicating possible incapacitation.

The alarm provider follows its normal verification procedure and requests urgent attendance.

A recognised responder is assigned.

Depending on the circumstances, the responder may be:

* an authorised care worker;
* a community responder;
* ambulance personnel;
* fire and rescue personnel;
* police;
* another approved emergency organisation.

The Place supports:

* an external gate;
* a controlled main entrance;
* an intercom;
* external entrance cameras;
* a local site agent;
* remote access release;
* internet and local credential validation;
* access and lock-state reporting.

The Place first attempts the configured contact and Approval sequence.

The resident does not respond.

The Access Policy permits emergency access where:

* the requesting organisation is in an approved responder category;
* the incident has an accepted emergency classification;
* the responder presents suitable identity or organisational credentials;
* the request is linked to an active emergency event.

The Place grants temporary access to the external gate and main entrance.

The responder enters, provides assistance, and later reports that the emergency access is no longer required.

The Place confirms that the entrance is secured where practical, revokes temporary Authority, records the event, and notifies appropriate parties.

## 4. Intended outcome

The use case is successfully handled when:

* an urgent or emergency need is identified;
* the request is classified appropriately;
* the responsible organisation and responder are recognised where practical;
* the Authority Basis is recorded;
* the Place applies the relevant urgent or emergency Access Policy;
* access is granted without avoidable delay where justified;
* access remains limited to the required Place and purpose;
* relevant Actions and state changes are recorded;
* temporary Authority ends when no longer required;
* the Place is left secure where circumstances permit;
* appropriate parties receive notification;
* the event is available for later review.

An emergency may still be successfully handled even where normal completion steps, such as confirmation that an entrance is secured, cannot occur immediately.

## 5. Participants

### 5.1 Person at risk

The person whose life, health, safety, or essential welfare may be affected.

The person at risk may be:

* the resident;
* the care recipient;
* a visitor;
* another person at the Place.

### 5.2 Requesting party

The person, organisation, system, or sensor that causes urgent or emergency action to be considered.

Examples include:

* resident;
* family member;
* authorised representative;
* care provider;
* alarm receiving centre;
* neighbour;
* healthcare provider;
* emergency service;
* Place monitoring system;
* automated alarm.

### 5.3 Responding organisation

The organisation responsible for coordinating or performing the response.

Examples include:

* ambulance service;
* fire and rescue service;
* police;
* personal alarm provider;
* care provider;
* community response service;
* emergency maintenance provider;
* utility emergency service.

The Responding Organisation is the Service Provider for the emergency or urgent response.

### 5.4 Responder

The person or authorised system performing the urgent or emergency Visit.

Examples include:

* paramedic;
* firefighter;
* police officer;
* care worker;
* community responder;
* emergency engineer;
* another authorised responder.

The Responder is the Service Agent.

### 5.5 Place Operator

The person or organisation responsible for controlling normal service interaction at the Place.

The Place Operator may be unable to approve access during an emergency.

### 5.6 Authorised representative

A person or organisation permitted to act for the person at risk or Place Operator.

### 5.7 Emergency coordinator

A person, organisation, or system coordinating the response.

Examples include:

* emergency control room;
* alarm receiving centre;
* care-provider supervisor;
* dispatch system.

### 5.8 Place platform

The system responsible for evaluating the request and coordinating available Place Capabilities.

### 5.9 Local Place systems

Systems that may perform or support physical access, such as:

* gate controller;
* entrance lock;
* key-safe controller;
* alarm system;
* intercom;
* external camera;
* local edge agent;
* Home Assistant;
* building access system.

## 6. Scope boundaries

This use case describes interoperability for Place interaction.

It does not define:

* emergency-service dispatch;
* statutory powers of entry;
* clinical triage;
* incident command;
* criminal investigation;
* fire-fighting procedure;
* care safeguarding procedure;
* legal liability;
* emergency call handling;
* evidence rules for legal proceedings;
* national emergency credential systems.

OSDI may support these systems by carrying limited identity, Authority, access, status, and audit information.

## 7. Authority Basis

An urgent or emergency access request should identify its Authority Basis.

Possible Authority Bases include:

* direct request by the person at risk;
* Approval by an authorised representative;
* standing emergency access agreement;
* personal alarm service agreement;
* care escalation policy;
* statutory emergency authority;
* recognised responder procedure;
* immediate threat to life or safety;
* urgent hazard response;
* another defined basis.

The Place does not necessarily need detailed medical, legal, or incident information.

A high-level category may be sufficient, such as:

* medical emergency;
* fire or smoke alarm;
* welfare emergency;
* personal alarm activation;
* immediate property hazard;
* police emergency;
* urgent care escalation.

## 8. Visit Classification

The Service Visit should identify its classification.

Recommended initial classifications are:

* scheduled;
* unplanned;
* urgent;
* emergency.

The classification should influence Access Policy but should not by itself grant Authority.

An emergency Visit still requires a recognised Authority Basis and appropriate validation to the extent practical.

## 9. Event creation

An urgent or emergency Event may be created from:

* a person’s request;
* a responder request;
* a care-provider escalation;
* an alarm-system notification;
* a sensor event;
* an emergency-service reference;
* another trusted source.

The Event should be distinguishable from the Service Visit.

The Event describes the condition requiring attention.

The Service Visit describes the responder’s interaction with the Place.

One Event may lead to:

* one responder Visit;
* several responder Visits;
* access by several organisations;
* a later follow-up Visit.

## 10. Assignment

Where practical, a specific Responder should be assigned to the Visit.

The Assignment may identify:

* Responding Organisation;
* Responder identity;
* Service Visit;
* Event reference;
* effective time;
* expiry;
* responder role;
* Assignment status.

In rapidly developing emergencies, the responding organisation may initially assign:

* a responder team;
* a vehicle;
* a crew reference;
* an incident unit;
* another organisational assignment.

The precise individual identities may be confirmed later where immediate individual assignment is not operationally available.

## 11. Identity and assurance

### 11.1 Organisation identity

The Place should establish, where practical, that the request comes from a recognised Responding Organisation or trusted coordinator.

### 11.2 Responder identity

The responder should present identity appropriate to the requested access and circumstances.

Possible methods include:

* authenticated responder application;
* signed organisational credential;
* dispatch-issued temporary credential;
* emergency-service identity system;
* provider confirmation;
* local physical identification;
* direct control-room validation.

### 11.3 Reduced validation during immediate danger

Where delay would create serious risk, the Place may apply an emergency process that uses reduced or deferred validation.

Any reduced validation should be:

* explicitly permitted by policy;
* limited to recognised emergency conditions;
* recorded;
* reviewed afterwards.

Reduced validation should not mean anonymous, unbounded, or permanent access where attribution remains possible.

## 12. Approval and emergency override

### 12.1 Normal Approval

The Place may first attempt Approval from:

* resident;
* Place Operator;
* authorised representative;
* care coordinator;
* another configured party.

### 12.2 Approval unavailable

Approval may be unavailable because:

* the resident is incapacitated;
* communications fail;
* the authorised representative cannot be reached;
* immediate action is required.

### 12.3 Emergency override

The Access Policy may permit an emergency override where defined conditions are met.

An emergency override should identify:

* the active Event;
* Authority Basis;
* responding organisation;
* responder or responding unit;
* requested Place;
* permitted Capabilities;
* start time;
* expiry;
* reason category;
* approving policy or authority.

Emergency override should not automatically expose unrelated Place Capabilities, data, or areas.

### 12.4 Revocation

Emergency Authority should be revocable when:

* the Event is resolved;
* the request is withdrawn;
* the responder is no longer assigned;
* the credential is compromised;
* the Place determines that the request is invalid;
* another authority assumes control.

## 13. Access Policy

The Place Access Policy may define emergency behaviour by responder category and Event type.

Possible rules include:

### 13.1 Resident Approval preferred

Attempt resident contact first where delay is acceptable.

### 13.2 Representative escalation

Contact an authorised representative after no resident response.

### 13.3 Recognised responder access

Allow an approved responder organisation to obtain temporary access for defined emergency categories.

### 13.4 Control-room confirmation

Require confirmation from a recognised dispatch or alarm centre.

### 13.5 Local alarm correlation

Require or prefer correlation with a Place alarm or sensor Event.

### 13.6 Limited initial access

Grant access only to:

* external gate;
* shared entrance;
* main entrance;
* another minimum required Service Point.

### 13.7 Broader access by explicit escalation

Require a separate request for additional restricted areas or Capabilities.

### 13.8 No automated emergency release

Some Places may not support automated emergency release.

OSDI should still support:

* responder identification;
* intercom;
* key-holder contact;
* key-safe procedure;
* access instructions;
* audit.

## 14. Relevant Place areas

An urgent or emergency Visit may involve:

* public approach;
* external gate;
* shared building entrance;
* main residence entrance;
* internal circulation area;
* location of the person at risk;
* utility isolation point;
* alarm panel;
* plant room;
* another incident-relevant area.

The Place should expose only the areas and instructions needed for the Event.

A full property layout should not be disclosed unless necessary and authorised.

## 15. Relevant Place Capabilities

### 15.1 Emergency request receipt

The ability to receive or recognise an urgent or emergency access request.

### 15.2 Responder validation

The ability to validate the Responding Organisation, Responder, Assignment, or dispatch reference.

### 15.3 Contact and Approval

The ability to contact the resident, representative, Place Operator, or coordinator.

### 15.4 External gate access

The ability to grant access through an external boundary.

### 15.5 Main entrance access

The ability to open or permit entry through the main entrance.

### 15.6 Key-safe or key-holder support

The ability to provide or coordinate an approved physical-key process.

### 15.7 Intercom or voice communication

The ability to communicate with persons at the Place.

### 15.8 Access-state reporting

The ability to report whether an entrance:

* opened;
* closed;
* locked;
* remains unsecured;
* failed to operate.

### 15.9 Alarm information

The ability to provide limited incident-relevant alarm state where authorised.

Examples include:

* smoke alarm active;
* personal alarm active;
* water alarm active;
* intrusion alarm active.

### 15.10 Safety instructions

The ability to provide relevant Place instructions, such as:

* gate location;
* entrance route;
* known access limitation;
* key-safe location;
* accessible entrance;
* hazardous area warning;
* utility isolation location.

### 15.11 Evidence and audit

The ability to record:

* request;
* validation;
* override decision;
* access Actions;
* access state;
* Authority creation and expiry;
* exceptions.

### 15.12 Notification

The ability to notify configured parties that emergency access occurred.

Notification may be delayed where immediate notification could interfere with response or safety.

## 16. Information associated with the Event and Visit

The interaction may use:

* Event identifier;
* Event category;
* Event creation time;
* source of Event;
* urgency classification;
* Service Visit identifier;
* Responding Organisation;
* Responder or responding-unit identity;
* Assignment reference;
* Place identifier;
* Authority Basis;
* requested Capabilities;
* Approval attempts;
* override status;
* access instructions;
* Authority validity;
* arrival time;
* entry time;
* departure or release time;
* final status;
* exception information;
* audit references.

The Place should not normally receive:

* full medical details;
* complete emergency call recording;
* detailed law-enforcement intelligence;
* unrelated care records;
* unnecessary responder personnel data.

The responder should not normally receive:

* unrelated household routines;
* unrestricted camera access;
* unrelated access history;
* unrelated resident information;
* complete security configuration.

## 17. Normal urgent-access journey

### Step 1 — Urgent need is identified

A care provider, alarm service, resident, representative, or another recognised party identifies a need for prompt attendance.

### Step 2 — Urgent Visit is created

A Service Visit is created with:

* urgent classification;
* Authority Basis;
* Place;
* expected arrival period;
* requested access;
* expiry.

### Step 3 — Responder is assigned

A suitable responder is assigned.

### Step 4 — Place Access Policy is evaluated

The Place determines:

* whether the provider is recognised;
* whether the urgent category is permitted;
* what Approval is required;
* what Capabilities may be granted;
* what contact sequence applies.

### Step 5 — Approval is obtained where required

The resident or representative approves the Visit where practical.

### Step 6 — Temporary Authority is created

Authority is limited to the urgent Visit.

### Step 7 — Responder approaches and arrives

The responder reports approaching and arrival.

### Step 8 — Identity and Assignment are validated

The Place validates the current request.

### Step 9 — Entry is granted

The responder enters using the permitted access method.

### Step 10 — Urgent service is provided

The responder follows the applicable provider procedure.

### Step 11 — Departure is reported

The responder leaves or indicates that Place access is no longer required.

### Step 12 — Place is secured

The entrance is secured where circumstances permit.

### Step 13 — Authority ends

Temporary Authority expires or is revoked.

### Step 14 — Visit completes

The Visit is marked completed, escalated, failed, or completed with exception.

## 18. Normal emergency-access journey

### Step 1 — Emergency Event is raised

An emergency Event is created from a trusted or reviewable source.

### Step 2 — Emergency response is initiated

A recognised Responding Organisation accepts or is assigned to the Event.

### Step 3 — Responder or unit is assigned

The responder identity, crew, vehicle, or incident unit is associated with the Visit where practical.

### Step 4 — Place is identified

The emergency request is matched to the intended Place.

### Step 5 — Contact is attempted where appropriate

The Place may attempt:

* resident contact;
* representative contact;
* intercom;
* control-room contact.

Contact attempts should not create unsafe delay.

### Step 6 — Emergency Access Policy is evaluated

The Place checks:

* Event classification;
* Authority Basis;
* Responding Organisation;
* available responder identity;
* requested Capabilities;
* policy conditions.

### Step 7 — Emergency Authority is issued

The Place creates limited temporary Authority.

### Step 8 — Access is granted

The required gate, shared entrance, or main entrance is opened or otherwise made accessible.

### Step 9 — Entry is recorded

The Place records available information about:

* access request;
* Authority;
* entry Action;
* time;
* access state.

### Step 10 — Emergency response proceeds

Responders manage the incident under their own procedures.

OSDI does not control the response activity.

### Step 11 — Additional access is requested if required

The responder may request further Place Capability access where available and justified.

### Step 12 — Emergency access is ended

The responder, coordinator, or Place platform indicates that the exceptional Authority is no longer required.

### Step 13 — Place is secured where practical

The entrance is closed or secured.

If this is not possible, an exception is recorded and a responsible party is notified.

### Step 14 — Notifications are issued

Appropriate parties receive notification according to policy.

### Step 15 — Post-event review is available

The event record supports later review of:

* who requested access;
* why;
* what policy applied;
* what was opened;
* when;
* which responder attended;
* when Authority ended;
* what exceptions occurred.

## 19. Example status sequence

An urgent Visit may use:

```text id="s2zn6n"
Urgent Need Identified
    ↓
Urgent Visit Created
    ↓
Responder Assigned
    ↓
Approval Requested
    ↓
Approved
    ↓
Responder Arrived
    ↓
Entry Authorised
    ↓
Visit in Progress
    ↓
Responder Departed
    ↓
Completed
```

An emergency Event may use:

```text id="j8vh4c"
Emergency Raised
    ↓
Response Dispatched
    ↓
Responder Assigned
    ↓
Emergency Authority Evaluated
    ↓
Emergency Access Granted
    ↓
Responder Entered
    ↓
Incident in Progress
    ↓
Emergency Access Ended
    ↓
Place Secured or Security Exception
    ↓
Closed
```

Provider and emergency systems may retain more detailed statuses.

## 20. Alternative and exception journeys

### 20.1 Resident responds and opens the entrance

No automated override is needed.

The Place may still record:

* emergency Event reference;
* responder arrival;
* resident-controlled entry;
* departure;
* outcome status.

### 20.2 Representative approves urgently

An authorised representative approves the responder’s entry.

### 20.3 Resident refuses access

For an urgent non-emergency Visit, access should normally not proceed unless another recognised authority applies.

For a statutory emergency response, the responder follows applicable law and procedure.

OSDI should record the basis used without attempting to determine legal validity.

### 20.4 No responder identity is available before arrival

A responding unit or dispatch reference may be used initially.

Individual responder identities may be associated later.

The Place policy may require control-room confirmation before remote release.

### 20.5 Several responder organisations attend

One Event may lead to several Service Visits or Assignments.

Each organisation should receive only the Authority it requires.

### 20.6 Emergency responder changes

The Assignment may be updated to another crew, vehicle, or individual.

Unused credentials should expire or be revoked.

### 20.7 Responder arrives at the wrong Place

Access should be denied where the request cannot be matched to the intended Place.

The rejection should avoid disclosing sensitive resident information.

### 20.8 Internet connection is unavailable

Possible offline methods include:

* locally verifiable emergency credential;
* resident-controlled entry;
* physical key-safe;
* control-room voice verification;
* local alarm correlation;
* physical emergency entry under responder procedure.

Offline emergency access should be explicitly designed and tested by implementations that claim to support it.

### 20.9 Place platform is unavailable

The responder may use existing emergency procedures.

OSDI unavailability must not be treated as preventing lawful or necessary emergency action.

### 20.10 Access controller fails

The responder may:

* use a physical key process;
* request a key holder;
* use another entrance;
* use lawful forced entry;
* follow organisation procedure.

OSDI may record the failure but does not direct forced-entry decisions.

### 20.11 Emergency classification is disputed

The Place may:

* require control-room confirmation;
* request stronger Authority Basis;
* deny remote release;
* preserve the request for review.

Immediate-life-safety situations may proceed under responder authority outside OSDI.

### 20.12 False or malicious emergency request

The Place should support:

* validation;
* denial;
* alerting;
* credential revocation;
* rate limiting;
* audit preservation;
* notification of the Responding Organisation.

### 20.13 Emergency Authority is not ended promptly

The system may:

* apply short expiry;
* require extension;
* prompt the responder or coordinator;
* automatically revoke unused re-entry after departure;
* notify the Place Operator.

Authority should not remain open-ended because the Event status was not updated.

### 20.14 Responder needs to admit another responder

The Access Policy may allow:

* responder-team credentials;
* separate Assignments;
* control-room approval;
* limited escort authority.

One responder should not automatically receive unlimited authority to admit unrelated persons.

### 20.15 Entrance cannot be secured afterwards

The system should:

* record the exception;
* notify the Place Operator or responsible service;
* preserve access-state information;
* request follow-up action;
* avoid falsely reporting successful security restoration.

### 20.16 Camera or evidence systems are unavailable

Emergency access should not normally be delayed solely because optional evidence capture fails.

The failure should be recorded.

### 20.17 Person at risk is not found

The responder follows its own procedure.

OSDI may record:

* entry occurred;
* Event remained unresolved or escalated;
* additional Visit or search support was requested.

### 20.18 Emergency is downgraded

An emergency Event may be reclassified as urgent or routine.

Any broader emergency Authority should end, and a new limited Authority should be issued if continued access is required.

### 20.19 Urgent Visit is escalated to emergency

A new emergency Event or updated classification should be recorded.

The increased Authority should be explicit rather than silently expanding the original urgent Visit.

## 21. Evidence and audit

The record should be sufficient to answer:

* what Event triggered the request;
* who or what raised it;
* what urgency classification applied;
* which Responding Organisation accepted it;
* which Responder, team, or unit attended;
* what Authority Basis was used;
* what Approval attempts occurred;
* whether emergency override was used;
* which Place Capabilities were requested;
* what access Actions occurred;
* when access was granted;
* when Authority ended;
* whether the Place was secured;
* what exceptions occurred.

Audit should support accountability without collecting unnecessary sensitive incident information.

## 22. Privacy considerations

Emergency response can involve highly sensitive information.

The implementation should minimise disclosure of:

* medical condition;
* disability;
* personal alarm history;
* household routines;
* resident vulnerability;
* responder operational information;
* internal Place layout;
* unrelated occupants;
* unrelated camera footage;
* unrelated alarm history;
* unrelated access credentials.

Only incident-relevant information should be shared.

Post-event access to records should be controlled according to role and purpose.

## 23. Security considerations

The implementation should guard against:

* false emergency requests;
* forged responder credentials;
* misuse of emergency override;
* ordinary service requests being labelled as emergencies;
* replay of emergency credentials;
* access at the wrong Place;
* open-ended Authority;
* unauthorised expansion to additional Capabilities;
* disclosure of vulnerable-person information;
* compromised alarm or dispatch systems;
* multiple parties claiming control of one Event;
* failure to revoke Authority;
* tampering with audit records;
* use of emergency access for surveillance or unrelated entry.

Emergency functionality should be designed so that it does not weaken normal Place security.

## 24. Safety principles

The following principles should guide emergency-supporting implementations:

1. OSDI should not delay necessary emergency action.
2. Human safety takes priority over preservation of normal workflow.
3. Emergency access should be limited to the required purpose where practical.
4. Identity and organisational attribution should be preserved where practical.
5. Reduced validation should be exceptional and policy-based.
6. Emergency Authority should be short-lived.
7. Failed technology should not prevent use of established emergency procedures.
8. Place occupants should be notified where appropriate and safe.
9. Every emergency override should be reviewable.
10. OSDI should not attempt to replace statutory or professional judgement.

## 25. Current-practice alignment

Emergency and urgent providers already use:

* dispatch systems;
* incident references;
* control rooms;
* responder identities;
* vehicle or crew assignments;
* key-holder lists;
* key safes;
* alarm receiving centres;
* forced-entry procedures;
* post-incident reporting.

OSDI should initially complement these practices by supporting:

* Place identification;
* access instructions;
* responder or organisation validation;
* temporary digital Authority;
* remote gate or entrance release;
* access-state reporting;
* limited notifications;
* audit linkage.

Early integrations should not require emergency services to replace their operational systems.

## 26. Comparison with UC007–UC009

UC007 establishes normal scheduled care access.

UC008 tests worker replacement.

UC009 tests legitimate unplanned access under ordinary trust controls.

UC010 introduces:

* urgent and emergency Visit classification;
* an Event distinct from a Visit;
* emergency Authority Basis;
* emergency override;
* reduced or deferred validation;
* responder teams or units;
* access where normal Approval is unavailable;
* shorter Authority lifetime;
* post-event review;
* interaction with established statutory and professional procedures.

UC010 confirms that urgent and emergency access should not simply be represented as an unplanned Visit with fewer controls.

## 27. Common OSDI needs identified

UC010 suggests that OSDI may need to support:

* Event;
* Event category;
* Event source;
* Visit classification;
* Responding Organisation;
* responder or unit Assignment;
* Authority Basis;
* Approval attempts;
* emergency override;
* Access Policy;
* short-lived emergency Authority;
* Capability-specific access;
* escalation and reclassification;
* Authority revocation;
* Place-security exception;
* post-event audit.

## 28. Proposed NHS365 starter implementation

### 28.1 Alarm or response-provider template

A starter provider application may allow a recognised partner to:

* create an urgent or emergency Event;
* state a reason category;
* identify the affected Place;
* assign a responder or unit;
* request defined Place access;
* receive Authority status;
* update arrival and incident status;
* end the access requirement;
* report exceptions.

### 28.2 Responder application template

The responder application may provide:

* secure authentication;
* assigned Event and Visit;
* Place navigation;
* current access instructions;
* responder credential presentation;
* arrival reporting;
* gate and entrance access requests;
* control-room contact;
* incident status;
* request for additional Capability access;
* departure or release reporting.

### 28.3 Resident or representative application

The application may:

* display an urgent Approval request;
* identify the requesting organisation;
* allow immediate approval where appropriate;
* show that emergency access occurred;
* provide a contact route;
* show a limited post-event access record.

The interface should avoid requiring user interaction during situations where the person may be incapacitated.

### 28.4 NHS365 platform services

The platform may provide:

* Event creation;
* provider and responder validation;
* Assignment;
* Authority Basis recording;
* urgent and emergency policy evaluation;
* Approval workflow;
* emergency override;
* short-lived credential issuance;
* Capability-specific Authority;
* notification;
* revocation;
* audit;
* post-event review support.

### 28.5 NHS365 site agent

The site agent may:

* receive active emergency Authority;
* validate the requested Capability;
* operate an external gate or main entrance;
* report access state;
* provide limited alarm context;
* revoke local access;
* operate during temporary cloud loss where supported.

The site agent should not receive unnecessary medical or incident details.

### 28.6 Home Assistant adapter

Where Home Assistant is used, NHS365 may map:

* external gate access to a suitable lock or cover entity;
* main entrance access to a lock entity;
* access-state confirmation to lock and contact sensors;
* alarm state to relevant alarm or binary sensor entities;
* notifications to configured Home Assistant services;
* external entrance evidence to an approved camera entity.

Home Assistant entity identifiers remain internal to NHS365.

## 29. Starter demonstrations

### 29.1 Urgent welfare visit

1. A care provider creates an urgent welfare Visit.
2. Worker B is assigned.
3. The resident receives an Approval request.
4. The resident approves.
5. NHS365 issues limited temporary Authority.
6. Worker B arrives and enters.
7. The Visit completes normally.

### 29.2 Personal alarm with no response

1. A personal alarm Event is received.
2. The alarm centre attempts resident contact.
3. No response is received.
4. A recognised responder is assigned.
5. NHS365 evaluates the emergency Access Policy.
6. Emergency Authority is issued.
7. The responder gains entry.
8. The responder ends the emergency-access requirement.
9. The Place confirms security or records an exception.
10. The event is available for review.

### 29.3 Emergency-service access with local system failure

1. An emergency Event is active.
2. The Place platform is unavailable.
3. The responder uses the established physical or statutory access procedure.
4. NHS365 later records that automated OSDI access was unavailable.
5. The incident remains valid even though OSDI did not control entry.

This demonstration confirms that OSDI supports emergency access but is not a single point of failure.

## 30. Questions for refinement

1. What is the minimum distinction between urgent and emergency?
2. Should Event become an explicit OSDI Core concept?
3. Who may classify or reclassify an Event?
4. Which organisations may request emergency override?
5. How should recognised responder categories be represented?
6. Is individual responder identity always required before entry?
7. How should responder teams and vehicles be represented?
8. What minimum Authority Basis must be recorded?
9. What validation may be deferred during immediate danger?
10. How should emergency credentials work offline?
11. How short should emergency Authority be?
12. How is Authority extended when an incident lasts longer?
13. What happens when several organisations need simultaneous access?
14. How should emergency access be distinguished from statutory forced entry outside OSDI?
15. Who receives post-event notification?
16. What information should be visible to the resident after the Event?
17. How should false emergency requests be reviewed?
18. How should a Place opt in to or restrict emergency integrations?
19. What emergency capabilities belong in OSDI Core versus an emergency profile?
20. How should implementations prove that OSDI is not a single point of failure?

## 31. Concepts validated

UC010 validates:

* Service Journey;
* Service Visit;
* Place;
* Service Provider;
* Service Agent;
* Identity;
* Assignment;
* Credential;
* Authority;
* Authority Basis;
* Approval;
* Access Policy;
* Capability;
* Status;
* Evidence;
* Exception;
* Completion;
* Cancellation;
* Supersession.

It strongly supports adding:

### Event

A recognised condition or occurrence that may cause one or more Service Visits or other responses.

### Urgency Classification

An indication of the required response speed and exceptional policy level, such as routine, urgent, or emergency.

### Emergency Override

A policy-controlled use of exceptional Authority where ordinary Approval or validation cannot be completed without unacceptable risk.

### Responding Unit

A team, crew, vehicle, control-room assignment, or other operational grouping that may act as the Service Agent identity until individual responders are known.

### Post-Event Review

A structured examination of emergency access, Authority, Actions, exceptions, and outcomes after the immediate situation has ended.

These concepts should remain lightweight and should not turn OSDI into an emergency-management standard.

## 32. Initial conclusion

UC010 demonstrates that OSDI can support urgent and emergency Place interaction while remaining subordinate to established legal, professional, and emergency procedures.

The common model remains useful:

* an Event identifies the condition requiring action;
* a Service Visit describes the interaction with the Place;
* a Responding Organisation assigns a Responder or unit;
* an Authority Basis justifies the request;
* the Place Access Policy determines what can be granted;
* emergency override provides exceptional but limited Authority;
* Actions and access state are recorded;
* Authority ends when no longer required;
* the event is available for later review.

The defining principle is that emergency access may be faster and may use exceptional policy, but it should not become anonymous, unlimited, or unauditable where those safeguards remain practical.
