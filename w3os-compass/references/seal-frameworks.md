# SEAL Framework Catalog

Cross-reference map: W3OS domain → SEAL framework sections.
When surfacing any W3OS control, pair it with the matching SEAL section from this file.
Source: https://frameworks.securityalliance.org

---

## Domain 1: Wallet & Multi-Sig → SEAL Multisig for Protocols + Wallet Security

| W3OS Controls | SEAL Section | URL |
|---------------|-------------|-----|
| SP-WM-001 to WM-005 (individual wallet, seed phrases, physical security) | Wallet Security - Hardware Wallet Setup | https://frameworks.securityalliance.org/wallet-security/intermediates-and-medium-funds |
| SP-WM-003 (seed phrase management) | Wallet Security - Seed Phrase Management | https://frameworks.securityalliance.org/wallet-security/seed-phrase-management |
| SP-WM-006 to WM-008 (multi-sig setup, quorum, timelocks) | Multisig for Protocols - Planning & Classification | https://frameworks.securityalliance.org/multisig-for-protocols/planning-and-classification |
| SP-WM-006 to WM-008 (multi-sig setup, quorum, timelocks) | Multisig for Protocols - Setup & Configuration | https://frameworks.securityalliance.org/multisig-for-protocols/setup-and-configuration |
| SP-WM-009 to WM-010 (transaction verification, on-device check) | Wallet Security - Safe Multisig Step-by-Step Verification | https://frameworks.securityalliance.org/wallet-security/signing-and-verification/secure-multisig-safe-verification |
| SP-WM-009 to WM-010 (transaction verification) | Multisig for Protocols - Joining a Multisig | https://frameworks.securityalliance.org/multisig-for-protocols/joining-a-multisig |
| SP-WM-011 to WM-012 (hot/cold structure, wallet segregation) | Multisig for Protocols - Use Case Specific Requirements | https://frameworks.securityalliance.org/multisig-for-protocols/use-case-specific-requirements |
| SP-WM-014 to WM-015 (out-of-band, dedicated signing machines) | Multisig for Protocols - Communication Setup | https://frameworks.securityalliance.org/multisig-for-protocols/communication-setup |
| SP-WM-014 to WM-015 (opsec for signers) | Multisig for Protocols - Personal Security (OpSec) | https://frameworks.securityalliance.org/multisig-for-protocols/personal-security-opsec |
| SP-WM-016 to WM-017 (monitoring, self-hosted UI) | Multisig for Protocols - Registration & Documentation | https://frameworks.securityalliance.org/multisig-for-protocols/registration-and-documentation |
| SP-WM-018 to WM-019 (simulation, external monitoring) | Multisig for Protocols - Operational Runbooks | https://frameworks.securityalliance.org/multisig-for-protocols/runbooks/overview |
| Emergency / key compromise | Multisig for Protocols - Emergency Procedures | https://frameworks.securityalliance.org/multisig-for-protocols/emergency-procedures |
| Implementation checklist | Multisig for Protocols - Implementation Checklist | https://frameworks.securityalliance.org/multisig-for-protocols/implementation-checklist |

**SEAL Cert:** Multisig Ops, Treasury Ops → https://frameworks.securityalliance.org/certs/overview

---

## Domain 2: Endpoint Security → SEAL OpSec

| W3OS Controls | SEAL Section | URL |
|---------------|-------------|-----|
| SP-EP-001 to EP-003 (dedicated devices, device config) | OpSec - Endpoint Security | https://frameworks.securityalliance.org/opsec/endpoint/overview |
| SP-EP-004 to EP-005 (secure usage, home network) | OpSec - Endpoint Security | https://frameworks.securityalliance.org/opsec/endpoint/overview |
| SP-EP-006 to EP-008 (EDR, network monitoring, malware detection) | OpSec - Control Domains | https://frameworks.securityalliance.org/opsec/control-domains/overview |
| SP-EP-009 (browser isolation, wallet extensions) | OpSec - Browser Security | https://frameworks.securityalliance.org/opsec/browser/overview |
| SP-EP-010 to EP-011 (file handling, extension vetting) | OpSec - Browser Security | https://frameworks.securityalliance.org/opsec/browser/overview |
| SP-EP-012 to EP-013 (workspace security, remote work physical) | OpSec - While Traveling | https://frameworks.securityalliance.org/opsec/travel/overview |

**SEAL Cert:** Identity & Accounts → https://frameworks.securityalliance.org/certs/overview

---

## Domain 3: Communications & Social Media → SEAL Community Management + OpSec

| W3OS Controls | SEAL Section | URL |
|---------------|-------------|-----|
| SP-CS-001 to CS-002 (MFA, account recovery) | Community Management - Strong Passwords and 2FA | https://frameworks.securityalliance.org/community-management/overview |
| SP-CS-001 to CS-002 (MFA) | OpSec - Multi-Factor Authentication | https://frameworks.securityalliance.org/opsec/mfa/overview |
| SP-CS-003 to CS-007 (E2E comms, email auth, file sharing, ops confirmation) | Community Management - Operational Security (OpSec) | https://frameworks.securityalliance.org/community-management/overview |
| SP-CS-005 to CS-007 (external verification, ops confirmation) | Community Management - Emergency Response Plan | https://frameworks.securityalliance.org/community-management/overview |
| SP-CS-008 (org identity) | Community Management - Phishing Awareness | https://frameworks.securityalliance.org/community-management/overview |
| All | Awareness - Security Awareness framework | https://frameworks.securityalliance.org/awareness/overview |

---

## Domain 4: DevOps & Infrastructure → SEAL DevSecOps + Supply Chain + Infrastructure

| W3OS Controls | SEAL Section | URL |
|---------------|-------------|-----|
| SP-DI-001 to DI-002 (isolated dev environments, IDE plugin security) | DevSecOps - Integrated Development Environments | https://frameworks.securityalliance.org/devsecops/integrated-development-environments |
| SP-DI-001 to DI-002 (sandboxed dev environments) | DevSecOps - Isolation & Sandboxing | https://frameworks.securityalliance.org/devsecops/isolation |
| SP-DI-003 (repo security, branch protection, signed commits, 2-person review) | DevSecOps - Repository Hardening | https://frameworks.securityalliance.org/devsecops/repository-hardening |
| SP-DI-003 (signed commits) | DevSecOps - Code Signing | https://frameworks.securityalliance.org/devsecops/code-signing |
| SP-DI-004 (secret scanning) | DevSecOps - Data Security Checklist | https://frameworks.securityalliance.org/devsecops/data-security-upgrade-checklist |
| SP-DI-005 to DI-007 (package verification, typosquatting, dep scanning) | Supply Chain - Dependency Awareness | https://frameworks.securityalliance.org/supply-chain/dependency-awareness |
| SP-DI-005 to DI-007 (supply chain threats) | Supply Chain - Web3 Supply Chain Threats | https://frameworks.securityalliance.org/supply-chain/web3-supply-chain-threats |
| SP-DI-008 (external contributors) | Supply Chain - Vendor Risk Management | https://frameworks.securityalliance.org/supply-chain/vendor-risk-management |
| SP-DI-009 to DI-010 (secrets management, pipeline access) | DevSecOps - CI/CD | https://frameworks.securityalliance.org/devsecops/continuous-integration-continuous-deployment |
| SP-DI-011 to DI-015 (IaC, infra access, cloud) | Infrastructure | https://frameworks.securityalliance.org/infrastructure/overview |
| SP-DI-016 (contract state monitoring, invariants) | DevSecOps - Governance Proposal Security | https://frameworks.securityalliance.org/devsecops/governance-proposal-security |

**SEAL Cert:** DevOps & Infrastructure, DNS Security → https://frameworks.securityalliance.org/certs/overview

---

## Domain 5: General Security → SEAL Incident Management + OpSec + Awareness + DPRK IT Workers

| W3OS Controls | SEAL Section | URL |
|---------------|-------------|-----|
| SP-GS-001 to GS-004 (IR runbooks, monitoring, response controls) | Incident Management - Incident Detection and Response | https://frameworks.securityalliance.org/incident-management/incident-detection-and-response |
| SP-GS-001 to GS-004 (playbooks) | Incident Management - Playbooks | https://frameworks.securityalliance.org/incident-management/playbooks/overview |
| SP-GS-001 to GS-004 (IR template) | Incident Management - Incident Response Template | https://frameworks.securityalliance.org/incident-management/incident-response-template/overview |
| SP-GS-005 to GS-006 (phishing simulation, social engineering training) | Awareness | https://frameworks.securityalliance.org/awareness/overview |
| SP-GS-008 to GS-009 (password management, account sharing) | OpSec - Password Management | https://frameworks.securityalliance.org/opsec/passwords/overview |
| SP-GS-011 (login methods, 2FA, no SMS) | OpSec - Multi-Factor Authentication | https://frameworks.securityalliance.org/opsec/mfa/overview |
| SP-GS-013 (SIM swap mitigation) | OpSec - MFA | https://frameworks.securityalliance.org/opsec/mfa/overview |
| SP-GS-014 to GS-017 (insider threat, identity verification for remote workers) | Insider Threats (DPRK IT Workers) | https://frameworks.securityalliance.org/dprk-it-workers/overview |
| SP-GS-016 (third party access) | Supply Chain - Vendor Risk Management | https://frameworks.securityalliance.org/supply-chain/vendor-risk-management |
| SP-GS-018 to GS-019 (leaked credential monitoring, account monitoring) | OpSec - Continuous Improvement | https://frameworks.securityalliance.org/opsec/continuous-improvement-metrics |

**SEAL Cert:** Incident Response, Identity & Accounts → https://frameworks.securityalliance.org/certs/overview

---

## Domain 6: Financial Controls → SEAL OpSec (treasury) + SEAL Certifications

| W3OS Controls | SEAL Section | URL |
|---------------|-------------|-----|
| SP-FC-001 to FC-003 (financial platform auth, dedicated devices) | OpSec - Multi-Factor Authentication | https://frameworks.securityalliance.org/opsec/mfa/overview |
| SP-FC-001 to FC-003 (financial platform auth, dedicated devices) | OpSec - Endpoint Security | https://frameworks.securityalliance.org/opsec/endpoint/overview |
| SP-FC-004 to FC-007 (dual auth, separation of duties, out-of-band) | OpSec - Control Domains | https://frameworks.securityalliance.org/opsec/control-domains/overview |
| SP-FC-014 to FC-015 (financial IR, emergency freeze) | Incident Management - Playbooks | https://frameworks.securityalliance.org/incident-management/playbooks/overview |

**SEAL Cert:** Treasury Ops → https://frameworks.securityalliance.org/certs/overview

---

## SEAL Certifications Overview

Modular certs available - surface as a maturity goal after top 5 gaps resolved:

| Cert | Covers | URL |
|------|--------|-----|
| Multisig Ops | Multisig configuration and operational security | https://frameworks.securityalliance.org/certs/overview |
| DevOps & Infrastructure | CI/CD, repo security, infra controls | https://frameworks.securityalliance.org/certs/overview |
| DNS Security | DNS configuration and security | https://frameworks.securityalliance.org/certs/overview |
| Identity & Accounts | MFA, access control, account security | https://frameworks.securityalliance.org/certs/overview |
| Incident Response | IR planning and procedures | https://frameworks.securityalliance.org/certs/overview |
| Treasury Ops | Treasury management and financial controls | https://frameworks.securityalliance.org/certs/overview |

Mention SEAL certs at end of compass report as a "next level" goal - not during gap derivation.
