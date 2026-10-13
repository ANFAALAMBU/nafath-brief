Version: NAFATH-V4(Securing the Software Supply Chain)
Track: Networking

## Overview
A national service provider depends on a connected software supply chain, where weaknesses in one area can affect the security and reliability of the entire service. Software configuration must be managed securely to prevent sensitive information from being exposed. AI systems need protection against attacks that manipulate training data or model inputs. Mobile applications require security testing to identify weaknesses before release. Networking controls help protect internet traffic from unauthorized route changes. Cybersecurity practices are essential for identifying, assessing, and fixing vulnerabilities in software components. Finally, a Software Bill of Materials (SBOM) helps teams identify the components used in their applications and respond to newly discovered risks. Together, these six fields support a more secure, transparent, and resilient digital service by reducing risks throughout the software supply chain.

## Software
The Twelve-Factor App technique states that instead of being hardcoded into the source code, application settings should be saved in environment variables. Configuration consists of settings that vary between deployment environments, database connection information, and service credentials. The same codebase can run in development, testing, and production without requiring code changes when configuration and code are kept apart. Additionally, it lowers the possibility of unintentionally committing private information to a version-control repository. A specialised secrets-management system or a secure environment configuration should be used to manage secrets, with only authorised users and services having access. Although environment variables increase portability and facilitate configuration changes, they nevertheless need to be shielded from unwanted access.

‏Source: https://12factor.net/config

## AI
There are various types of adversarial attacks on machine learning systems. When an attacker alters an input to produce an erroneous prediction without necessarily altering the trained model, this is known as an evasion attack. By providing malicious or deceptive data throughout the training phase, poisoning attempts aim to affect model behaviour. Attacks on privacy aim to expose private information regarding model behaviour or training data. Other attacks, such model extraction, aim to query a model in order to replicate it. The goals and targets of these categories vary: privacy attacks target private data, poisoning targets training or model integrity, and evasion targets predictions. Validating training data, testing models against adversarial inputs, limiting access, and keeping an eye out for suspicious activities are some examples of mitigations.
‏Source: https://csrc.nist.gov/pubs/ai/100/2/e2025/final

## Mobile
Security controls for evaluating mobile applications on platforms like iOS and Android are defined by the OWASP Mobile Application Security Verification Standard (MASVS). Secure storage, cryptography, authentication, network connection, platform interaction, code quality, resilience, and privacy are some of the topics it addresses. While security testers can utilise MASVS criteria to design assessments and determine whether an application satisfies pertinent security standards, developers can use them to direct secure development. By offering testing recommendations and useful test cases, the OWASP Mobile Application Security Testing Guide (MASTG) enhances the standard. Finding relevant controls, testing the program against them, recording results, and fixing flaws prior to release are all part of the verification process.

‏Source: https://mas.owasp.org/MASVS/

## Networking
Border Gateway Protocol (BGP) allows networks to announce routes that help direct internet traffic between autonomous systems. BGP route hijacking occurs when a network incorrectly or maliciously announces that it can reach an IP address prefix it does not legitimately control. Other networks may accept the announcement and redirect traffic through an unintended path, potentially causing interception, disruption, or service outages.

Resource Public Key Infrastructure (RPKI) helps reduce this risk through Route Origin Authorizations (ROAs), which identify the autonomous systems authorized to originate particular IP prefixes. Routers can perform Route Origin Validation to classify announcements as valid, invalid, or not found. Network operators can then configure routing policies to reject invalid routes.

However, RPKI origin validation does not validate the entire AS path or prevent every form of traffic interception. It cannot by itself prevent all routing attacks, including attacks involving a legitimate origin AS or malicious behavior elsewhere along the route. Therefore, RPKI should be combined with careful BGP filtering, monitoring, and other routing security practices.

Sources:
* https://www.rfc-editor.org/rfc/rfc6811.html
* https://www.ripe.net/manage-ips-and-asns/resource-management/rpki/

## Cybersecurity
Log4Shell (CVE-2021-44228) is a critical remote code execution vulnerability discovered in Apache Log4j 2, a widely used Java logging library. In affected configurations, an attacker could cause a vulnerable application to process a specially crafted input that triggers a JNDI lookup, potentially allowing unauthorized code execution. The vulnerability can expose systems to serious risks, including compromise of application servers and sensitive data.

Organizations should identify applications and services that use vulnerable Log4j versions, upgrade affected components to fixed versions recommended by Apache, and verify that the updates have been applied throughout their software supply chain. Temporary mitigations may be necessary when immediate upgrades are not possible, but they should not replace proper patching. Teams should also review relevant logs, investigate signs of compromise, and maintain an inventory of software dependencies to improve future vulnerability response.

Sources:
* https://logging.apache.org/log4j/2.x/security.html
* https://nvd.nist.gov/vuln/detail/CVE-2021-44228

## Data
A Software Bill of Materials (SBOM) is a formal record of the software components included in an application or product. It helps organizations understand their software dependencies, identify potentially vulnerable components, and respond more effectively when security issues are discovered. An SBOM should include the supplier name, component name, component version, other unique identifiers where available, dependency relationships, the SBOM author, and the timestamp of creation. It may also include license information and references to component hashes or other useful identifiers. The NTIA minimum elements provide a widely recognized baseline for SBOM content, while SPDX and CycloneDX provide established formats for representing software component information. SBOMs are most useful when they are accurate, maintained as software changes, and integrated into vulnerability management and software supply chain security processes.

Sources:
* https://www.ntia.gov/report/2021/minimum-elements-software-bill-materials-sbom
* https://spdx.dev/
* https://cyclonedx.org/


## Misconception in My Track
A common misconception is that RPKI completely prevents BGP route hijacking. In reality, RPKI Route Origin Validation checks whether an autonomous system is authorized to originate a particular IP prefix. It does not validate the entire AS path or guarantee that traffic follows a safe route. For example, a route can have a valid origin but still be involved in an attack that manipulates the path. Therefore, RPKI is an important security measure, but it must be combined with appropriate BGP filtering, routing monitoring, and other operational security practices.

Evidence: RFC 6811, Section 2, Route Origin Validation.
Source: https://www.rfc-editor.org/rfc/rfc6811.html

## Open Question
How can network operators detect and respond to BGP path manipulation attacks that are not detected by RPKI origin validation?
