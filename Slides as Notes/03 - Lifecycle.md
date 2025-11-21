# Development Lifecyle & Principles

## A Ubiquitous Concern

- You can make a security mistake at every step of the development lifecycle
- ***Requirements*** that allow for privacy violations
	- e.g. secretary can view everyone's patient records
- Introducing a ***design*** flaw
	- e.g. giving plug-ins total access
- Introducing a ***code***-level vulnerability
	- e.g. [[Classic Buffer Overflow]]
- Missing a vulnerability in code ***inspections*** and ***testing***
- Introducing a vulnerability by regression in ***maintenance***
- Not facilitating a secure ***deployment***
	- e.g. installation defaults

## Security at Every Step

1. Requirements & Planning
	1. Abuse cases
	2. Risk assessment
	3. Threat Modeling
2. Design
	1. Architectural risk
	2. Secure design patterns
	3. Formalism
3. Implementation
	1. Vulnerability Taxonomy
	2. Input/Output Handling
	3. Auditability
4. Testing
	1. Penetration Testing
	2. Exploratory Testing
	3. Automated Testing
5. Deployment
	1. Networking & Cryptography
	2. Defaults
	3. Permissions

## Core Security Properties

- Software security breaks into these categories
	- Confidentiality
	- Integrity
	- Availability
- Very broad, multi-dimensional categories
- Some people add in "auditability", but we consider that part of "integrity"

### Confidentiality

- They system must not disclose any information intended to be hidden
	- e.g. your credit card information on a website
- Note: open source software can still be confidential

### Integrity

- The system must not allow assets to be subverted by unauthorized users
	- e.g. changing a prisoner's release date
- We must be able to trust what is in the system
	- The data being stored
	- The functionality being executed

### Availability

- The system must be able to be available and operational to users
	- e.g. bringing down Amazon.com
- These are extremely hard to protect against
	- _Any_ system performance degradation that can be triggered by a user can be used for denial of service attacks
	- Concurrency issues, infinite loop, or resource exhaustion

## Human Error Terminology

- Slips
	- Failure of **attention**
	- e.g. putting the wrong key in your car
	- e.g. messing up code indentation
- Lapses
	- Failure of **memory**
	- e.g. forgetting to put your keys in the car
	- e.g. forgetting to check for a null first
- Mistakes
	- Failure of **planning**
	- e.g. not taking construction into account on your way to work
	- e.g. trusting the metadata to be accurate instead of checking yourself

## Misc. Philosophies & Proverbs

### Defense in depth

- If they break into this, they can’t get any farther
- Think Middle-Age castles
- Original meaning of “firewall”, not today’s firewall

### Least privilege

- Every user or module is given the least amount of privilege it needs
- Evil: `sudo chmod –R a+rw /`

### Fail securely

- Exceptions put the system into weird states
- Error message information leak
- Take care of those exceptions properly!

### Security by obscurity

- You can’t rely upon being obscure to be secure
- Crowds are good at guessing
- Insiders are corruptible 
- Some notable exceptions: passwords, encryption keys

### Frameworks are optional

- Don't expect framework features to fix your security problems for you
	- e.g. ORMs, templating, CMSs, etc.
- Developers often bypass frameworks – even when they shouldn't
- You will still need to know how to USE your frameworks' features and what they do for you

### Detect and record

- Do both. Even if you can't always soft through that data ahead of time
- Post-mortem analysis

### Don't trust (input | environment | dependencies | * ) initially

- Know what to trust
- "Confused deputy" vulnerabilities
	- *Can you free me? The sheriff said so!*
- have a way to build trust after initial distrust

### Journey Before Destination

- Some practices are useful because of the journey they take you on:
	- Institutional knowledge transfer
	- Revealing stealth expectations
- Planning > Plan
- Warning: Gen. AI skips the journey and gives you the _illusion_ that you're being productive

### Secure by default

- Don't rely on your users to use it correctly
- Convention over configuration

### Keep it simple

- YAGNI (You aren't gonna need it)
- Speculative generality can be risky
- Minimize the attack surface

## Exercise: Spam Bot Server

Suppose we had a vulnerability in the RIT mail servers where you could send a special packet and it would bypass authentication for outgoing email. This allowed attackers to send emails using any account.

- Which of CIA does this violate?
	- Immediately? CIA of the email system?
	- ...as a secondary consequence? CIA of users?
- Using the following philosophies, discuss how each of these can be applied here:
	- Defense in Depth
	- Security by obscurity
	- Detect and record
	- Don't trust input