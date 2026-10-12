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

DNS over HTTPS (DoH) sends DNS queries and responses over HTTPS to a configured resolver. TLS protects their confidentiality and integrity in transit, making it harder for a local network or on-path observer to inspect or alter lookups. It does not hide queries from the resolver, make the user anonymous, or encrypt the subsequent connection to a government website; destination IPs and traffic patterns can still reveal activity.

Resource: RFC 8484: DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/rfc/rfc8484

## Cybersecurity

Phishing resistance depends on a cryptographic proof bound to the legitimate verifier or channel, so a fake site cannot capture and relay a reusable code. NIST recognizes channel binding and verifier-name binding; WebAuthn/FIDO2 can provide verifier-name binding. SMS codes, authenticator-app OTPs, and manually entered out-of-band codes are not phishing-resistant, even if they add a second factor. Multi-factor status and phishing resistance are separate properties.

Resource: NIST Special Publication 800-63B - https://pages.nist.gov/800-63-4/sp800-63b.html

## Data

Royal Decree 68/2026 amended the law: Article 3(b) excludes personal-data processing by public authorities carrying out legally assigned functions. The authority should establish whether its login service falls within this exception. Otherwise, processing must respect transparency and dignity, usually requires explicit consent (subject to legal exceptions), protect confidentiality, limit retention, and meet breach, rights, permit and transfer rules. Article 14 gives people a right to object to automated decisions and requires human review.

Resource: Royal Decree 6/2022 Issuing the Personal Data Protection Law (Consolidated) - https://decree.om/2022/l20220006/

## Misconception in My Track

A common mistake is to treat OAuth 2.0 as the protocol that logs a person in. OAuth 2.0 grants limited authorization to access resources; it does not define a standard identity assertion by itself. OpenID Connect adds authentication to OAuth and provides an ID Token so a client can verify the user. The proof is in the OpenID Connect Core specification, Section 1, “Introduction,” which states that OAuth 2.0 does not define standard methods to provide identity information and that OpenID Connect implements authentication as an extension.

## Open Question

Which government services need the same identity claims, and how can the authority minimize claims shared with each service while preserving access?
