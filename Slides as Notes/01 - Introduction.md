# What is Secure?

## Software Security And You

- Find one or two other people near you
	- Introduce yourself
	- What is your favorite software development technology? (language, tool, library, etc.)
	- Have you ever written software where security mattered?
		- Did you do anything about it then?

## How do you know?

- With those people, discuss this:
	- How do you know that you have delivered secure software?
		- Try to think of examples
		- What are your indicators?
		- How will you convince others that your software is secure?

## Discussion Takeaways

- Security is not black-and-white
- Security is "until proven insecure"
- Security "Theater"
	- Feeling safer vs. Being safer
	- People act on their perception of reality, not necessarily on reality
- Protections can be costly
	- e.g. personal liberty and privacy

Technology is key:
- Eliminating a Threat vs. Protection
- Vulnerability vs Exploit vs. Threat

## An Engineer’s Concern

- In SE, we teach you how to _build_ software
	... but not as much as _breaking_ software
- How do you know that you have built a system that cannot be broken into?
	- What evidence do you look for?
	- How do you know you're done?
	- How do you prioritize security against everything else drawing upon your time?
- SE is a zero-sum game
	"If I need to focus more energy on security, what should we take away?"

## VotD: Integer Overflow

- Let's take a look at one of the simplest vulnerabilities out there...
- Think on these questions:
	- How bad is this?
	- How do you find these?
	- How do you fix these?
	- How do you _prevent_ these with design?
	- How do you _prevent_ these with process?

## Vulnerability

- Informally, a bug with security consequences
- A design flaw or poor coding that may allow an attacker to exploit software for a malicious purpose
	- Non-software equivalent to “lack of shoe-examining at the airport”
	- E.g. allowing easily-guessed passwords (poor coding)
	- E.g. complete lack of passwords when needed (design flaw)
	- McGraw: 50% are coding mistakes, 50% are design flaws
- Alternative definition: “an instance of a fault that violates an (implicit or explicit) security policy”

## Exploit and Threat

- **Exploit**: a piece of software, a chunk of data, or a sequence of commands that takes advantage of a vulnerability in an effort to cause unintended or unanticipated behavior
	- i.e. maliciously using a vulnerability
	- Can be manual or automated
	- Viruses are merely automated exploits
	- Many different ways to exploit just one vulnerability
- **Threat**: two usages of the word
	- (a) An actor or agent that is a source of danger, capable of violating confidentiality, availability, or integrity of information assets and security policy
		- e.g. black-hat hackers
	- (b) A class of exploits
		- e.g. spoofing

## Protection

Protection against...

### exploits?

- Anti-virus, intrusion detection, firewalls, etc.

### threats?

- Use forensics to find & eliminate
- Policy, incentives, deterrents, etc.

### vulnerabilities?

- Engineer secure software

## Software Security is...

### NOT a myth but a reality

- Insecure software causes _immeasurable harm_
- Sony, NSA, Equifax, OPM, Anthem/Premera, Android, Browsers, Mueller report, SolarWinds, log4Shell... just read the news

### NOT an arcane black art

- Much of it seems arcane
	- Finding a severe vulnerability w/o source code
	- Crafting the exploit
	- Endless clever ways to break software
- But, you have much more knowledge than the attackers do
- Don’t just leave it to the experts, take responsibility for knowing security

### NOT a dire apocalyptic future

- Fear-mongering will not be tolerated here
- Risk management dictates that we deal with the _probable_ more than the _possible_

### NOT a set of features

- Secure software > Security software
- Although tools and experts are helpful,
	- You can't just deploy a magical tool and expect all vulnerabilities to disappear
	- You can't outsource all of your security knowledge
- Even if you are using a security library, know _how_ to use it properly

### NOT a problem for just mathematicians

- Cryptography
	- Is important and needed
	- Cannot solve all of your security problems
	- Pick-proof lock vs. open window
- Proofs, access control rules, and verification are helpful, but inherently incomplete

### NOT a problem for just networking and operating systems

- Software had security problems long before we had the internet
- If you left a window open in your house, would you try to fix the roads?

### A reality everyone must face

- Not just developers, all stakeholders
- The ability to prevent _unintended functionality_
	- At _all_ layers of the stack
	- In _all_ parts of your system

## Student Security Maturity

### Denial

_I don’t have to think about this. Let me just code._
_Leave it to the experts._
_I could never understand this anyway._

### Irrational fear, superstition

_EVERYTHING IS POSSIBLE NOW!!!_
_EVERY MITIGATION IS NECESSARY!!!_
_ENCRYPT EVERYTHING!!!_

### Bag of Tricks

_Let’s just try these tricks that worked in the past_
_We’ve done these 10 things. That’s a lot. Close enough, right?_

### Reasoned, Balanced, Defensive Mindset

_If we do X, we mitigate Y, which is worthwhile because of Z._
