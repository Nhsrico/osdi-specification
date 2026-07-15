# Chapter 1 – Vision

**Document Status:** Normative Foundation
**Specification Version:** 0.1.0-draft

---

# 1. Vision

## 1.1 Purpose

The Open Services Delivery Interface (OSDI) defines an open, implementation-neutral framework for the secure interaction between authorised service organisations and compatible places.

OSDI provides a common conceptual, behavioural and security model that enables independent organisations and systems to cooperate when delivering authorised services to residential, commercial and community environments.

The specification is intended to support interoperability across diverse technologies, organisations and service domains while preserving security, privacy, accountability and user control.

---

## 1.2 Problem Statement

Many services require interaction with physical places.

Examples include:

* delivery of goods;
* delivery of medication;
* domiciliary care;
* maintenance visits;
* inspection services;
* emergency response;
* utility services;
* community support services.

Today these services typically rely upon proprietary integrations between individual organisations, identity providers, property management systems, building automation systems and smart devices.

These point-to-point integrations are often difficult to maintain, difficult to audit and difficult to extend. They limit interoperability, increase implementation cost and make it difficult for organisations to adopt new technologies or service providers.

OSDI seeks to provide a common framework through which independent systems may securely cooperate while remaining free to choose their own implementation technologies.

---

## 1.3 Objectives

The objectives of OSDI are to:

* define a common language for service interaction;
* separate service intent from implementation technology;
* provide a consistent security and trust model;
* enable interoperability between independent organisations;
* support multiple service domains using common abstractions;
* provide complete auditability of authorised interactions;
* support future capabilities without redesigning the core specification;
* encourage an open ecosystem of interoperable implementations.

---

## 1.4 Design Philosophy

OSDI does not standardise individual products or technologies.

Instead, OSDI standardises the interactions between independent systems.

The specification intentionally avoids dependence upon any specific:

* identity provider;
* building management system;
* smart property platform;
* cloud provider;
* communication protocol;
* device manufacturer;
* software framework;
* implementation architecture.

Implementations remain free to select technologies appropriate to their environment provided they conform to the OSDI specification.

---

## 1.5 Scope

OSDI defines:

* conceptual models;
* behavioural models;
* capability abstractions;
* information models;
* security models;
* interoperability requirements;
* conformance requirements.

OSDI intentionally does not prescribe implementation technologies.

---

## 1.6 Relationship to Existing Technologies

OSDI is intended to complement existing standards and technologies rather than replace them.

Examples include:

* identity and authentication systems;
* access control systems;
* building automation platforms;
* smart property platforms;
* communication protocols;
* cloud platforms;
* service management platforms.

OSDI provides a common interaction layer above these technologies by defining consistent concepts, behaviours and security requirements.

---

## 1.7 Guiding Principles

Every authorised service interaction should be:

* authenticated;
* authorised;
* capability-based;
* auditable;
* implementation-independent.

These principles underpin all subsequent chapters of the specification.

---

## 1.8 Long-Term Vision

The long-term vision of OSDI is to establish an open interoperability framework through which organisations may securely provide services to compatible places without requiring proprietary integrations between individual vendors or service providers.

OSDI aims to encourage an ecosystem in which service providers, property platforms, device manufacturers and identity providers can interoperate through common specifications while preserving competition, innovation and user choice.

---

## 1.9 Human-Centred Principle

Technology exists to support people.

OSDI recognises that service interactions ultimately exist to benefit individuals, households and communities.

Implementations should preserve human oversight, minimise unnecessary complexity and enable users to retain meaningful control over their environments and personal information.

Security, privacy and accessibility should be considered fundamental characteristics of every compliant implementation.

---

## 1.10 What OSDI Does Not Define

To avoid ambiguity, OSDI does not define:

* a transport protocol;
* a smart home protocol;
* a building automation protocol;
* an identity provider;
* a logistics management system;
* a care management system;
* vendor-specific device interfaces;
* user interface requirements.

Instead, OSDI defines the common interaction model that enables these systems to cooperate in a secure, interoperable and auditable manner.

---

## 1.11 Intended Audience

This specification is intended for:

* service providers;
* platform providers;
* property technology vendors;
* device manufacturers;
* identity providers;
* software developers;
* systems integrators;
* standards organisations;
* public sector bodies;
* researchers and solution architects.

---

## 1.12 Future Evolution

OSDI is designed to evolve over time.

Future versions may introduce new service profiles, capability definitions, protocol bindings and conformance levels without altering the fundamental conceptual model established by this specification.

Backward compatibility should be preserved wherever practical, while allowing the specification to respond to emerging technologies and service domains.
