# FedRAMP Notes

FedRAMP authorization is a security authorization process that validates a cloud service provider's adherence to U.S. federal government security standards, enabling them to work with federal agencies. It involves rigorous assessments by Third-Party Assessment Organizations (3PAOs) against NIST SP 800-53 requirements, resulting in a FedRAMP Authorization (ATO) that allows for repeated reuse by agencies, ensuring consistent security for sensitive federal data.

## FedRAMP Authorization Impact Levels

The certification process uses security controls based on National Institute of Standards and Technology (NIST) guidelines and categorizes authorizations into three impact levels based on data sensitivity.

* **FedRAMP Low:** For systems where a breach would cause limited adverse effect on an agency's operations, assets, or individuals. It has the fewest required security controls.
* **FedRAMP Moderate:** The most common level, covering controlled unclassified information where a breach could cause a serious adverse effect. This includes personally identifiable information (PII).
* **FedRAMP High:** For systems handling the government's most sensitive, unclassified data, where a breach could have a severe or catastrophic effect, such as financial ruin or loss of life.

## FedRAMP Authorization Process

### Key Components of FedRAMP Authorization

* **System Security Plan (SSP):** A critical document detailing the system's security posture.
* **Readiness Assessment (RAR):** A preliminary evaluation to determine if a CSP is ready for authorization.
* **Security Assessment Report (SAR):** A report from a Third-Party Assessment Organization (3PAO) detailing the security assessment findings.
* **Plan of Action and Milestones (POA&M):** A plan to address any identified security gaps.

### FedRAMP Certification Involves

* **Standardized Security Requirements:** FedRAMP provides a unified set of security controls and procedures based on NIST SP 800-53 and the Risk Management Framework (RMF).
* **Third-Party Assessments:** Cloud service providers (CSPs) must undergo independent security assessments by FedRAMP-accredited 3PAOs.
* **Continuous Monitoring:** CSPs are required to continuously monitor their security controls and report changes to federal agencies.
* **Authorization and Reuse:** Once a CSP obtains an Authorization to Operate (ATO), the assessment documentation can be reused by any federal agency, saving time and resources.

Cloud service providers can pursue FedRAMP authorization through one of two paths.

### 1. Agency Authorization

This is the most common and often faster path.

* **Find a federal agency sponsor:** The CSP must find an agency that wants to use its cloud service and is willing to invest resources to see it authorized.
* **Work with a 3PAO:** The CSP engages an accredited Third-Party Assessment Organization (3PAO) to conduct an independent security assessment.
* **Prepare documentation:** The CSP develops a detailed System Security Plan (SSP) and a Plan of Action and Milestones (POA&M) to document and address any identified security gaps.
* **Achieve Authority to Operate (ATO):** After reviewing the assessment and documentation, the sponsoring agency issues an ATO, authorizing the use of the service for that agency. The FedRAMP Program Management Office (PMO) confirms the status on the FedRAMP Marketplace.

### 2. Joint Authorization Board (JAB) Provisional ATO

This path is more competitive and suitable for cloud services with broad government demand.

* **Apply via FedRAMP Connect:** The JAB—composed of representatives from the Department of Defense, Department of Homeland Security, and General Services Administration—prioritizes potential candidates based on government-wide need.
* **Complete a Readiness Assessment:** If selected, the CSP undergoes a readiness assessment with a 3PAO to demonstrate it is prepared for a full security review.
* **Receive a Provisional ATO (P-ATO):** The JAB reviews the CSP's security package and issues a P-ATO, which other agencies can leverage when granting their own ATOs.

### Post-Authorization Requirements

FedRAMP Certification requires continuous monitoring to ensure compliance is maintained.

* **Monthly reporting:** CSPs must provide monthly vulnerability scan reports to agency customers and update their POA&M.
* **Annual assessment:** A 3PAO performs an annual security assessment to re-evaluate the service's security posture.

## FedRAMP Technical Requirements

### Control Baselines (Impact Levels)

FedRAMP defines **three security baselines** depending on the sensitivity of data:

* **Low Impact (125+ controls)** – public or non-sensitive data (e.g., websites).
* **Moderate Impact (~325 controls)** – Controlled Unclassified Information (CUI), most common for SaaS.
* **High Impact (421+ controls)** – highly sensitive federal data (law enforcement, healthcare, etc.).

All CSPs must implement the baseline that matches their target authorization level.

### Core Security Domains

### Access Control (AC)

* Multi-Factor Authentication (MFA) for privileged and remote access.
* Least privilege / role-based access control.
* Session timeouts, account lockouts, and user provisioning/deprovisioning controls.

### Audit & Accountability (AU)

* Detailed logging of user and admin actions.
* Time-stamped audit logs, protected from modification.
* Centralized log management and retention (at least 1 year online, 3 years offline).

### Configuration Management (CM)

* Approved and documented baseline configurations.
* Secure configuration standards (e.g., CIS Benchmarks, DISA STIGs).
* Change control process with security review.

### Incident Response (IR)

* Incident response plan aligned with federal requirements.
* Ability to detect, report, and escalate incidents quickly.
* Regular incident response exercises.

### System & Communications Protection (SC)

* Encryption **in transit and at rest** with **FIPS 140-2 (or 140-3) validated modules**.
* TLS 1.2 or higher for network connections.
* Network segmentation and boundary protections (firewalls, IDS/IPS).

### Vulnerability Management (SI)

* Continuous vulnerability scanning (OS, databases, web apps).
* Patch management and remediation timelines:

  * **High-risk:** 30 days
  * **Moderate:** 90 days
  * **Low:** 180 days
* Malware protection and integrity checks.

### Identification & Authentication (IA)

* Unique user IDs (no shared accounts).
* Strong password policies.
* MFA across all access points.

### System & Information Integrity (SI)

* Monitoring and alerting for unauthorized activities.
* Protection from known and zero-day exploits.
* Integrity checks for software, firmware, and hardware.

### Continuous Monitoring

* Monthly vulnerability scans (internal/external).
* Ongoing POA&M (Plan of Action & Milestones) updates.
* Annual independent assessment by a **3PAO**.

### FedRAMP-Specific Requirements

In addition to NIST controls, FedRAMP adds stricter requirements:

* **Use of FIPS-validated cryptography** (not just FIPS-compliant).
* **Personnel background checks** for CSP employees with privileged access.
* **U.S. data residency** for Moderate and High impact systems.
* **Specific reporting timelines** for incidents (within 1 hour of discovery).
* **Automated asset and configuration management** for Moderate/High.

## APPENDIX

### Resources

* **FedRAMP Security Controls Baseline**
  https://www.fedramp.gov/resources/documents/FedRAMP_Security_Controls_Baseline.xlsx

* **CSP Authorization Playbook**
  https://www.fedramp.gov/resources/documents/CSP_Authorization_Playbook.pdf

* **Agency Authorization Playbook**
  https://www.fedramp.gov/resources/documents/Agency_Authorization_Playbook.pdf

* **Continuous Monitoring Strategy Guide**
  https://www.fedramp.gov/resources/documents/CSP_Continuous_Monitoring_Strategy_Guide.pdf

### FIPS Validated Cryptography

* For FedRAMP, specifically **FIPS 140-2 (and now 140-3)** is the standard that governs cryptographic modules.

  FIPS = Federal Information Processing Standards

* **"Validated"** means that the encryption libraries or modules used have been **independently tested and certified by NIST's Cryptographic Module Validation Program (CMVP)** — not just that they claim to support the right algorithms.

  Official NIST CMVP Database:
  https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules

  * **FIPS-compliant** = uses approved algorithms (e.g., AES-256, SHA-256) but not necessarily tested/certified.
  * **FIPS-validated** = the specific implementation (library/module) has gone through **NIST validation testing** and is listed on the official CMVP database.

* **Data at Rest & In Transit**

  * All encryption of sensitive data must use a **FIPS 140-2/140-3 validated module** (e.g., OpenSSL in FIPS mode).
  * Applies to TLS, VPNs, SSH, disk/database encryption, and key management systems.

* **Operating System & Libraries**

  * CSPs must configure OS and middleware to use only FIPS-validated crypto.
  * Example: Enabling **FIPS mode in Windows** or Linux so that only validated modules are available.

* **Key Management**

  * Keys must be generated, stored, and managed with FIPS-validated crypto modules (e.g., AWS KMS, Azure Key Vault, HashiCorp Vault in FIPS mode).

* **Cloud Provider Services**

  * If leveraging IaaS/PaaS providers (AWS, Azure, GCP), you must verify that the services you're using are operating in **FedRAMP/FIPS-validated mode**.
