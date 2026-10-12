Version: NAFATH-V1
Track: Software

## Overview

One national login must work consistently in a mobile app and on government websites while limiting each service to the access it needs. OpenID Connect lets a client verify a user's identity; OAuth 2.0 scopes limit delegated access to protected resources. Android's permission model helps the app avoid collecting unrelated device data, while DNS over HTTPS can protect domain lookups on untrusted networks. An AI system may help flag unusual sign-ins, but it needs risk assessment, testing, monitoring, and a human review path. Phishing-resistant authentication helps prevent stolen login proofs from being relayed to fake sites. The authority must also determine how Oman's amended data-protection law applies to identity, biometric, and login data. This brief focuses especially on when OAuth 2.0 or OpenID Connect should handle login versus resource access.

## Software

OAuth 2.0 is an authorization framework: it lets an application obtain limited access to a protected service through scoped access tokens. On its own, it does not define a standard way to tell the client who authenticated. OpenID Connect adds an identity layer on top of OAuth 2.0 and returns an ID Token that the client validates. Use OpenID Connect for user sign-in; use OAuth scopes to delegate service-specific resource access.

Resource: OpenID Connect Core 1.0 incorporating errata set 2 - https://openid.net/specs/openid-connect-core-1_0.html

## AI

NIST's AI Risk Management Framework organizes work into Govern, Map, Measure, and Manage. Before launch, assign accountable owners; map who is affected and how false alerts could deny access; measure validity, reliability, privacy, security, explainability, and harmful bias across relevant groups. Set thresholds, human review and appeal, incident response, drift monitoring, and a safe fallback. A risk score should inform proportionate checks, not silently become an unreviewable decision.

Resource: Artificial Intelligence Risk Management Framework (AI RMF 1.0) - https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf

## Mobile

Android isolates apps and gates access to protected data or device functions through permissions. The app should request a dangerous permission at runtime only when a user reaches the feature that needs it, after explaining why, and should ask for the narrowest access available. If permission is denied, respect the decision and keep other features usable. A basic login flow should not ask for unrelated contacts, photos, or location.

Resource: Request runtime permissions - https://developer.android.com/training/permissions/requesting

## Networking

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
