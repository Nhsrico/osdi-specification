# Open Services Delivery Interface Specification

**OSDI — Open Services Delivery Interface**

> **Status:** Early Working Draft  
> **Version:** 0.1.0-draft  
> **Stability:** Subject to incompatible change  
> **Production use:** Not currently recommended

OSDI is an open, implementation-neutral specification describing how
authorised service organisations can interact securely, consistently,
and audibly with compatible places.

OSDI is intended to support the delivery of services including:

- parcel and goods delivery;
- medication and grocery delivery;
- domiciliary and community care;
- maintenance and installation visits;
- inspections and utility services;
- alarm response and emergency access.

OSDI defines a common semantic, behavioural, security, capability, and
conformance model. It does not require any particular smart-property
platform, identity provider, device protocol, cloud provider, or
implementation technology.

NHS365 is intended to become a reference implementation of OSDI. It is
not part of the OSDI specification, and compliant OSDI implementations
must not depend on NHS365.

## Repository structure

- `specification/` — normative and foundational specification chapters
- `profiles/` — service-specific OSDI profiles
- `schemas/` — machine-readable schemas and protocol descriptions
- `use-cases/` — non-normative end-to-end examples
- `decisions/` — significant specification design decisions
- `proposals/` — proposed changes and extensions
- `test-vectors/` — valid and invalid conformance examples
- `development/` — repository-maintenance and agent guidance

## Current phase

The repository is currently establishing the OSDI conceptual foundation:

1. scope and design principles;
2. terminology;
3. core information model;
4. service visit and service session lifecycles;
5. authority and capability abstractions;
6. event and security models;
7. initial conformance roles.

Detailed protocol bindings and production APIs will be developed after
the conceptual and behavioural models have stabilised.

## Specification status

Unless explicitly marked otherwise, all current documents are working
drafts. Normative requirements may change incompatibly before the first
stable release.

## Participation

External review, proposals, and contributions are welcome. The formal
contribution and governance processes are still being developed.

## Maintainer

The specification is initially maintained by NetHomeSolutions through
the public OSDI repository.