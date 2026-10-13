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


## Cybersecurity

## Data

## Misconception in My Track

## Open Question
