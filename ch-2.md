## cybersecurity threat landscape

- classifying cybersecurity threats
	- internal vs external
	- level of sophistication / capability
	- resources / funding
	- intent / motivation
- threat actors
	- unskilled attackers
	- hacktivists
		- motivated by greater good
	- organized crime
		- motivated by financial gain
		- cybercrime categories
			- cyberdependent crimes
				- DDOS, data compromise, ransomware, etc
			- CSAM
			- online fraud
			- dark web activity
				- ex: sale of illegal goods / services
			- cross cutting crime factors
				- social engineering, money mules, cryptocurrency abuse
	- nation state actors
		- APT (advanced persistent threat)
	- insider threat
		- shadow IT
			- when individuals / groups seek their own technology solutions without approval from org
	- competitors
		- stealing sensitive info from org for business advantage
	- types of adversaries
		- authorized attackers (white hat)
		- unauthorized attackers (black hat), malicious intent
		- semi authorized attackers (grey hat), without proper auth but w/ intent of informing targets
- attacker motivations
	- data exfil attacks
		- want to gain sensitive / proprietary info 
	- espionage attacks
		- orgs want info from other orgs (nation states attacking each other or corporations)
	- service disruption attacks
		- take down / interrupt critical systems / networks 
	- blackmail attacks
		- extort money / other concessions 
	- financial gain attacks
	- philosophical / political beliefs 
	- ethical attacks (white hat)
	- revenge attacks
	- disruption / chaos attacks
	- war
- threat vectors and attack surfaces 
	- attack surface: system / app / service w/ an exploitable vuln 
	- threat vector: how a threat actor would obtain access 
	- message based threat vectors
		- email (phishing)
		- sms (smishing)
		- voice calls (vishing)
		- social media 
	- wired networks
		- walk into org and compromise systems
	- wireless networks
		- access org's wifi / bluetooth
	- systems
		- individual systems can be threat vectors if not configured securely / have insecure software 
		- ex: exposed open service ports. legacy systems 
	- files / images
		- files w/ embedded malicious code
	- removable devices
		- usb drives
	- cloud
		- attackers scan cloud services for files with improper access controls to find api keys, passwords, etc
	- supply chain
		- attacking an org's vendors / suppliers to indirectly attack the org 
		- ex: tampering with a device or software to insert backdoors
		- MSP: managed service provider
			- service provider who provides an org with IT systems 
			- attackers who infiltrate an MSP network could use their access to their systems / networks 
- threat data and intelligence
	- threat intel: set of activities / resources available to those learning about changes in the threat environment 
		- can be used for predictive analysis to identify likely risks 
	- sources of threat intel
		- OSINT
		- commercial services w/ proprietary intel 
	- ex: IP addresses, emails, URLs, CVEs, etc
	- vulnerability databases: contain reports of vulns 
	- IoC: indicators of compromise 
		- ex: file signatures, log patterns
		- can be found in file / code repos that have threat intel 
- open source intelligence 
	- open source threat intel is intel from publicly available sources 
	- ex: CISA, Microsoft, SANS
- proprietary and closed source intel 
	- orgs create / make use of proprietary, closed source intelligence
	- they gather their own info and may create custom tools, analysis models, etc to gather, curate, and maintain their threat feeds
	- threat maps: provide geographical view of threat intel
- assessing threat intel 
	- timely?
	- accurate?
		- does it rely on one source or multiple sources?
		- are those sources reliable?
	- relevant?
- threat indicator management and exchange
	- use structured markup languages like STIX and OpenIOC 
	- structured threat information eXpression (stix)
	- ex
```
		{ "type": "threat-actor", 
		"created": "2019-10-20T19:17:05.000Z", 
		"modified": "2019-10-21T12:22:20.000Z", 
		"labels": [ "crime-syndicate"], 
		"name": "Evil Maid, Inc", 
		"description": "Threat actors with access to hotel rooms", 
		"aliases": ["Local USB threats"], 
		"goals": ["Gain physical access to devices", "Acquire data"], 
		"sophistication": "intermediate", 
		"resource:level": "government", 
		"primary_motivation": "organizational-gain" }
```

- information sharing organizations
	- Information sharing and analysis centers (ISACs) help infra owners and operators share threat info + provide tools and assistance 
- conducting your own research
	- good sources 
		- vendor security info websites
		- vuln + threat feeds from vendors, govt agencies, private orgs
		- academic journals, technical publications (eg: RFCs)
		- conferences / local industry group meetings 
		- social media of prominent security professionals 
	- TTP: tactics, techniques, and procedures
