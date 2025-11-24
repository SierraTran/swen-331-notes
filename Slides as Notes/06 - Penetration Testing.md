# Penetration Testing

## Testing that Digs Deeper

- Penetration testing is about attempting to exploit as much as possible (ethically)
- Purposes
	- Demonstrate the person-hours required to break in 
	- Create a real scenario
- Compared to typical SE testing
	- Typical: "found a stracktrace! Report bug
	- Pentesting: "how can we use this stacktrace?"
	- Map out a long set of chains of attacks

## Preconditions

- Requires a working system
	- Not necessarily finished, but working
	- As networked as possible – for pivoting
	- Highly skilled testers
- Outsider
	- Not pre-knowing company secrets
	- Most companies hire out pentesters, but in-house pentesters are highly marketable
	- Can be a good "side-hustle" for you in existing dev organizations

## MITRE's ATT&CK & CAPEC

### ATT&CK

- A taxonomy of tactics and techniques for general-purpose pentesting knowledge
- Tactics: broad categories
- Techniques:
	- tool-agnostic approaches
	- somewhat technology-dependent
### CAPEC

- "Common Attack Pattern Enumeration and Classification"
- A dictionary of attack patterns
- Organized by mechanisms and domains
- Not covered in this lecture, but referenced in a few VotD

## ATT&CK (Enterprise version)

### ATT&CK Tactics

| Name                 | Description                                                                        |
| -------------------- | ---------------------------------------------------------------------------------- |
| Pre-ATT&CK           | The adversary is building capabilities and doing initial research                  |
| Initial Access       | The adversary is trying to get into your environment                               |
| Discovery            | The adversary is trying to figure out your environment                             |
| Privilege Escalation | The adversary is trying to gain higher-level permissions                           |
| Defense Evasion      | The adversary is trying to avoid being detected                                    |
| Credential Access    | The adversary is trying to steal account names and passwords                       |
| Collection           | The adversary is trying to gather data of interest to their goal                   |
| Execution            | The adversary is trying to run malicious code                                      |
| Persistence          | The adversary is trying to maintain their foothold                                 |
| Lateral Movement     | The adversary is trying to move through your environment                           |
| Command and Control  | The adversary is trying to communicate with compromised systems to control them    |
| Exfiltration         | The adversary is trying to steal data                                              |
| Impact               | The adversary is trying to manipulate, interrupt, or destroy your systems and data |

### ATT&CK Techniques

- There's a lot of techniques
- For this class, including exams, we'll focus on just a few key ones.
#### Key Techniques
##### Initial Access
- Drive-by compromise
	- Users visit malicious sites
	- e.g. executing JavaScript with a browser exploit in it that takes control of a machine
- Hardware additions
	- Introducing new hardware to the system
	- e.g. hardware keystroke loggers, keystroke injection, network sniffers, portable cell-phone towers
- Spearphishing
	- Confidence scamming exploiting the specific company
	- We see these at RIT all the time
##### Discovery
- Network and Service Scanning
	- Run tools to enumerate hosts and ports
	- Figure out what services are running
	- e.g. nmap, unicornscan
- Account Discovery
	- Find a listing of the existing accounts
	- e.g. /etc/passwd
##### Credential Access
- Brute Force
- Credential Dumping
	- e.g. dump a database table with credentials
	- e.g. copy the /etc/shadow file
- Valid Accounts
	- e.g. using default accounts
	- e.g. using discovered credentials from other access
##### Execution
- Command-line interface
	- e.g. ssh terminal, powershell
- Service execution
	- e.g. adding a new "service" to be executed
##### Persistence
- Bootkit
	- Place malware in the Master Boot Record of the HDD
	- Executed even after reformatting OS partition
- Scheduled task (also an Execution technique)
- Create account
- Component firmware
##### Privilege Escalation
- Process Injection
	- Execution arbitrary code in an existing, legit process space
	- e.g. Changing the path of a DLL at runtime, stack smashing, LD_LIBRARY_PATH
- setuid and setgid (we'll cover this later)

## CPTC, Kali, and OSCP

### Collegiate PenTesting Competition

- RIT helps and competes in an annual national competition (Oct-Nov)
- Like a varsity sport

### Kali Linux

- A distro designed for penetration testing
- TONS of tools, steep learning curve on many of them

### Offensive Security Certified Professional

- One of the best certs out there for pentesting
- About the effort of a college course
- 24-hour final exam where you have to break into every machine