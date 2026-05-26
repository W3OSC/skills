# W3OS Domain Reference

Condensed W3OS standard for gap derivation. Source: https://github.com/W3OSC/web3-opsec-standard

For each domain: key MUST-level requirements and profile signals that indicate a gap.

---

## Domain 1: Wallet & Multi-Sig Management

**Profile signals that indicate gaps:**
- Treasury not on multi-sig → SP-WM-006 NON-COMPLIANT
- Safe quorum < 3-of-5 → SP-WM-007 NON-COMPLIANT
- No time-locks configured → SP-WM-008 NON-COMPLIANT
- No monitoring on Safe address → SP-WM-016 NON-COMPLIANT
- No dedicated signing devices mentioned → SP-WM-015 gap
- No transaction simulation in workflow → SP-WM-018 gap
- No external monitoring party → SP-WM-019 gap

**Key MUSTs:**
- `SP-WM-006` Treasury and contract admin MUST use on-chain multi-sig → *SEAL: [Planning & Classification](https://frameworks.securityalliance.org/multisig-for-protocols/planning-and-classification)*
- `SP-WM-007` Minimum 3-of-5 quorum required → *SEAL: [Setup & Configuration](https://frameworks.securityalliance.org/multisig-for-protocols/setup-and-configuration)*
- `SP-WM-008` Time-locks MUST be enabled; minimum 3-day delay → *SEAL: [Setup & Configuration](https://frameworks.securityalliance.org/multisig-for-protocols/setup-and-configuration)*
- `SP-WM-009` Signers MUST verify on 2+ devices via 2+ channels → *SEAL: [Safe Multisig Verification](https://frameworks.securityalliance.org/wallet-security/signing-and-verification/secure-multisig-safe-verification)*
- `SP-WM-010` Hardware wallet display MUST be manually verified before signing → *SEAL: [Hardware Wallet Setup](https://frameworks.securityalliance.org/wallet-security/intermediates-and-medium-funds)*
- `SP-WM-014` Transaction coordination MUST use E2E encrypted channels; links MUST NOT be clicked → *SEAL: [Communication Setup](https://frameworks.securityalliance.org/multisig-for-protocols/communication-setup)*
- `SP-WM-015` Multi-sig ops MUST run on dedicated, network-restricted devices → *SEAL: [Personal Security (OpSec)](https://frameworks.securityalliance.org/multisig-for-protocols/personal-security-opsec)*
- `SP-WM-016` All multi-sig addresses MUST be monitored; channels MUST be immutable → *SEAL: [Registration & Documentation](https://frameworks.securityalliance.org/multisig-for-protocols/registration-and-documentation)*

**SEAL Certs:** Multisig Ops, Treasury Ops

**Risk weight:** Very high for any org with on-chain assets or smart contract admin keys.

---

## Domain 2: Endpoint Security

**Profile signals that indicate gaps:**
- No EDR mentioned anywhere → SP-EP-006 gap
- Personal devices used for work (small team, no device policy) → SP-EP-001 risk
- No network monitoring tools referenced → SP-EP-007 gap
- Browser extensions unvetted (no policy) → SP-EP-011 gap
- Remote team with no workspace security policy → SP-EP-012/013 gap

**Key MUSTs:**
- `SP-EP-001` Each member MUST have a dedicated org device; personal devices MUST NOT be used → *SEAL: [Endpoint Security](https://frameworks.securityalliance.org/opsec/endpoint/overview)*
- `SP-EP-003` Full disk encryption MUST be required; screen lock ≤5 min → *SEAL: [Endpoint Security](https://frameworks.securityalliance.org/opsec/endpoint/overview)*
- `SP-EP-006` EDR SHOULD be deployed; active network monitoring MUST be in place if no EDR → *SEAL: [Control Domains](https://frameworks.securityalliance.org/opsec/control-domains/overview)*
- `SP-EP-007` All endpoints MUST have active network monitoring and firewall enabled → *SEAL: [Control Domains](https://frameworks.securityalliance.org/opsec/control-domains/overview)*
- `SP-EP-009` Wallet extensions SHOULD only run on a dedicated transaction-only browser → *SEAL: [Browser Security](https://frameworks.securityalliance.org/opsec/browser/overview)*

**SEAL Certs:** Identity & Accounts

**Risk weight:** High for teams with signing authority; medium for non-signing members.

---

## Domain 3: Communications & Social Media

**Profile signals that indicate gaps:**
- SMS 2FA detected on any account (X, Discord, email) → SP-CS-001 NON-COMPLIANT
- No SPF/DKIM/DMARC records on org domain → SP-CS-004 gap
- Discord/X accounts not linked from official sources → SP-CS-008 gap
- Prior social account compromise in history → SP-CS-001/002 critical
- No Signal or E2E encrypted channel for internal ops → SP-CS-003 gap

**Key MUSTs:**
- `SP-CS-001` All org communication accounts MUST have MFA; SMS MUST NOT be primary or backup → *SEAL: [Community Management - 2FA](https://frameworks.securityalliance.org/community-management/overview), [OpSec - MFA](https://frameworks.securityalliance.org/opsec/mfa/overview)*
- `SP-CS-002` SMS recovery SHOULD NOT be enabled on any account → *SEAL: [OpSec - MFA](https://frameworks.securityalliance.org/opsec/mfa/overview)*
- `SP-CS-004` SPF, DKIM, DMARC MUST be configured on org domain → *SEAL: [Community Management](https://frameworks.securityalliance.org/community-management/overview)*
- `SP-CS-006` Files from external parties MUST be sanitized before opening (Dangerzone, VirusTotal, Google Drive) → *SEAL: [Community Management - OpSec](https://frameworks.securityalliance.org/community-management/overview)*
- `SP-CS-007` Internal ops coordination MUST be confirmed in secure channel (video, E2E encrypted) → *SEAL: [Community Management - Emergency Response Plan](https://frameworks.securityalliance.org/community-management/overview)*

**SEAL Certs:** Identity & Accounts

**Risk weight:** High for orgs with active communities (Discord, Telegram, X). Prior compromise = critical.

---

## Domain 4: DevOps & Infrastructure

**Profile signals that indicate gaps:**
- No dep scanning in CI (no depenemy, Dependabot, Snyk, etc.) → SP-DI-007 NON-COMPLIANT
- No secret scanning in repos → SP-DI-004 gap
- No branch protection on main/prod branches → SP-DI-003 gap
- Unsigned commits → SP-DI-003 gap
- Single-person PR merges → SP-DI-003 NON-COMPLIANT
- Secrets visible in repo history → SP-DI-009 critical
- No IaC (manual infra setup) → SP-DI-011 gap
- No smart contract state monitoring → SP-DI-016 gap (for protocol orgs)
- External contributors with full repo access → SP-DI-008 gap

**Key MUSTs:**
- `SP-DI-003` Branch protection MUST be on prod branches; signed commits MUST be required; 2-person PR approval MUST be required → *SEAL: [Repository Hardening](https://frameworks.securityalliance.org/devsecops/repository-hardening), [Code Signing](https://frameworks.securityalliance.org/devsecops/code-signing)*
- `SP-DI-004` Repos MUST be continuously scanned for committed secrets → *SEAL: [Data Security Checklist](https://frameworks.securityalliance.org/devsecops/data-security-upgrade-checklist)*
- `SP-DI-007` All deps MUST be scanned for known vulns before deployment; version pinning MUST be used → *SEAL: [Supply Chain - Dependency Awareness](https://frameworks.securityalliance.org/supply-chain/dependency-awareness)*
- `SP-DI-009` Secrets MUST NOT be in source code; dedicated secrets management MUST be used → *SEAL: [DevSecOps - CI/CD](https://frameworks.securityalliance.org/devsecops/continuous-integration-continuous-deployment)*
- `SP-DI-010` Pipeline modifications MUST require multi-party approval; manual deploy permissions MUST NOT exist → *SEAL: [DevSecOps - CI/CD](https://frameworks.securityalliance.org/devsecops/continuous-integration-continuous-deployment)*
- `SP-DI-016` Invariant monitoring SHOULD be set up for deployed contracts (DeFi protocols) → *SEAL: [Governance Proposal Security](https://frameworks.securityalliance.org/devsecops/governance-proposal-security)*

**SEAL Certs:** DevOps & Infrastructure, DNS Security

**Risk weight:** High for any org with active development. Critical for protocols with deployed contracts.

---

## Domain 5: General Security

**Profile signals that indicate gaps:**
- No incident response runbook found → SP-GS-001 NON-COMPLIANT
- No security champion/owner on team → SP-GS-007 gap
- No leaked credential monitoring → SP-GS-018 gap
- Small team with shared credentials visible → SP-GS-009 NON-COMPLIANT
- SSO used for admin/financial access → SP-GS-011 gap
- SMS 2FA anywhere → SP-GS-011 NON-COMPLIANT
- No phishing training mentioned → SP-GS-005 gap
- North Korea / remote-hire risk (crypto-native org) → SP-GS-017 relevant

**Key MUSTs:**
- `SP-GS-001` Org MUST maintain documented incident response plans for all critical systems → *SEAL: [Incident Management - Detection & Response](https://frameworks.securityalliance.org/incident-management/incident-detection-and-response), [Playbooks](https://frameworks.securityalliance.org/incident-management/playbooks/overview)*
- `SP-GS-008` Password manager MUST be used; passwords MUST be unique, 20-32 chars, auto-generated → *SEAL: [OpSec - Password Management](https://frameworks.securityalliance.org/opsec/passwords/overview)*
- `SP-GS-009` Credential sharing MUST NOT occur; account delegation MUST be used where possible → *SEAL: [OpSec - Control Domains](https://frameworks.securityalliance.org/opsec/control-domains/overview)*
- `SP-GS-010` Admin privileges MUST be granted to minimum necessary roles only → *SEAL: [OpSec - Control Domains](https://frameworks.securityalliance.org/opsec/control-domains/overview)*
- `SP-GS-011` 2FA MUST be enforced on all accounts; SMS MUST NOT be used; SSO MUST NOT be used for sensitive access → *SEAL: [OpSec - MFA](https://frameworks.securityalliance.org/opsec/mfa/overview)*
- `SP-GS-012` Owner/superadmin accounts MUST be treated as break-glass; usage MUST trigger team alert → *SEAL: [OpSec - Control Domains](https://frameworks.securityalliance.org/opsec/control-domains/overview)*
- `SP-GS-014` to `SP-GS-017` Insider threat modeling, remote worker verification → *SEAL: [DPRK IT Workers](https://frameworks.securityalliance.org/dprk-it-workers/overview)*
- `SP-GS-018` Leaked passwords MUST be monitored; alerts MUST be instant and immutable → *SEAL: [OpSec - Continuous Improvement](https://frameworks.securityalliance.org/opsec/continuous-improvement-metrics)*

**SEAL Certs:** Incident Response, Identity & Accounts

**Risk weight:** High across all org types. No IR runbook = critical regardless of other controls.

---

## Domain 6: Financial Controls & Banking Security

**Profile signals that indicate gaps:**
- Single person controls bank account → SP-FC-004 NON-COMPLIANT
- No dual approval for wire transfers → SP-FC-004 NON-COMPLIANT
- SMS MFA on banking portals → SP-FC-001 NON-COMPLIANT
- No dedicated financial device → SP-FC-003 gap
- Payment recipients not whitelisted → SP-FC-008 gap
- No documented financial IR runbook → SP-FC-014 gap

**Key MUSTs:**
- `SP-FC-001` Banking portals MUST require strong MFA; SMS MUST NOT be used; hardware keys strongly recommended → *SEAL: [OpSec - MFA](https://frameworks.securityalliance.org/opsec/mfa/overview)*
- `SP-FC-003` Financial portal access SHOULD be on dedicated devices; MUST NOT be over public networks → *SEAL: [OpSec - Endpoint Security](https://frameworks.securityalliance.org/opsec/endpoint/overview)*
- `SP-FC-004` All outbound payments MUST require approval from at least 2 authorized individuals → *SEAL: [OpSec - Control Domains](https://frameworks.securityalliance.org/opsec/control-domains/overview)*
- `SP-FC-006` Payment initiator and approver MUST be separate individuals → *SEAL: [OpSec - Control Domains](https://frameworks.securityalliance.org/opsec/control-domains/overview)*
- `SP-FC-007` High-value payments MUST have out-of-band verbal confirmation before approval → *SEAL: [Incident Management - Playbooks](https://frameworks.securityalliance.org/incident-management/playbooks/overview)*
- `SP-FC-012` Real-time transaction alerts MUST be configured; delivered to 2+ people via 2+ channels → *SEAL: [OpSec - Control Domains](https://frameworks.securityalliance.org/opsec/control-domains/overview)*

**SEAL Certs:** Treasury Ops

**Risk weight:** Medium-high for orgs with fiat banking operations. Often overlooked in Web3 orgs.
