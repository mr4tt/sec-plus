## resilience and physical security

- resilience and recovery in security architecture
	- continuity of operations: ensuring operations will continue despite issues like system failures of natural disasters
	- common elements for redundancy 
		- geographic dispersion 
			- rule of thumb: data centers should be at least 90 miles apart 
		- separation of servers and other devices in data centers
			- avoid a single rack being a point of failure
		- multiple network paths (multipath)
			- severed cable, failed device
		- redundant network devices 
			- eg: multiple routers, firewalls, IPS
			- load balancing 
			- clustering
				- groups of computers together to perform the same task 
		- protection of power
			- uninterruptible power supply (UPS) systems provide backup power
			- generator systems 
			- design elements like dual supply or multisupply hardware ensure a power supply failure won't disable a server
			- managed power distribution units (PDUs) provide intelligent power management 
		- systems and storage redundancy 
		- platform diversity 
			- use diff vendors, cryptographic solutions
- architectural considerations and security
	- availability targets should be designed based on org requirements
	- resilience: part of availability, determines what type and level of potential disruptions can be handled
	- cost
	- responsiveness: ability of system to respond in a timely manner 
	- scalability
	- ease of deployment
	- risk transference
		- insurance, contracts, etc
	- ease of recovery 
	- patch availability / vendor support
	- inability to patch 
		- if high availability is required and you can't patch the system without downtime
	- power consumption
	- compute requirements 
- storage resilience
	- use redundant arrays of inexpensive disks (RAID)
		- either multiple disks with data striped (spread across disks) or mirrored (completely duplicated) and ensure data isn't corrupted / lost (parity)
	- backups
		- periodically back up all data or incremental data
		- Differential backups back up the changes since the last full backup
		- Incremental backups back up changes since the last backup
	- replication
		- as changes occur, copy the data to a new location
	- journaling
		- creates log of changes
		- may be slow for recovery purposes
	- recovery
		-  ability to recover from backups
		- recovery point objectives (RPOs)
			- determine how often backups are taken
		- recovery time objects (RTOs)
	- snapshot
		- captures state of system / device when backup completed
		- common for VMs, so you can restore to that point
	- images
		- similar to snapshot, but is a complete copy of a system down to the bit level of the drive
		- used by virtualization systems and virtual desktop infra (VDI)
	- backup media
		- tape
		- disks
			- both magnetic and SSDs are used
			- network attached storage (NAS) or storage area network (SAN) 
		- optical media 
			- blu-ray disks, DVDs
			- not commonly used for capacity reasons
		- flash media
			- microSD, USB
			- used for short term copies and sometimes long term backups
		- nearline backups: backup storage that's not immediately available, but can be retrieved in a reasonable amt of time
	- backup considerations
		- bandwidth requirements for backups and restoration
		- time and cost to retrieve files
		- reliability
		- security model requirements for backups

| RAID                             | description                                                                                                     | advantage                                                                                             | disadvantage                                                                                   |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| RAID 0 - striping                | data is spread across all drives in the array                                                                   | speedy, all capacity used                                                                             | not fault tolerant (drive lost = data lost)                                                    |
| RAID 1 - mirroring               | all data duplicated to another drive or drives                                                                  | high read speeds from multiple drives; if drive fails, data still available                           | uses 2x storage for same amt of data                                                           |
| RAID 5 - striping w/ parity      | data is striped across drives, w/ one drive used for parity (checksum); parity is spread across drives and data | data reads fast; reads slightly slower. drive failures can be rebuilt as long as only one drive fails | only tolerates one drive failure at a time; rebuilding arrays can be slow + impact performance |
| RAID 10 - mirroring and striping | requires 4+ drives; drives added in pairs; data is mirrored and striped across drives                           | combines advantage and disadvantages of both RAID 1 and RAID 0                                        | combines advantage and disadvantages of both RAID 1 and RAID 0                                 |
- response and recovery controls
	- response controls: controls for orgs to respond to an issue (like outage, compromise, disaster)
		- nonpersistence: ability to have systems that are spun up and shut down as needed
		- return to last known good config
		- scalability
			- vertical scaling: increasing capacity of a single server to handle more workload 
			- horizontal scaling: increasing number of systems to handle workload 
	- site considerations
		- hot sites
			- have all infra and data necessary to operate org
		- warm sites
			- have some or all systems needed to perform work required, but live data isn't in place
		- cold sites
			- have space, power, and usually connectivity, but not systems or data
			- least expensive
	- capacity planning for resilience and recovery
		- people
			- necessary to deal with increased scale and disasters
			- ensure you have sufficient number of staff
		- technology
			- understanding the tech that an org has deployed and its ability to scale
		- infra
			- underlying systems / networks may need to scale 
	- testing resilience and recovery controls / designs
		- tabletop exercises: discussions between personnel to validate the plan 
		- simulation exercises: drills / practices where personnel simulate what they would do in an actual event 
		- parallel processing exercises: move processing to a hot site or alternate / backup system to validate it works 
		- failover exercises: test full failover to an alternate site 
- physical security controls
	- implement site security plan based on threats / risks relevant to each location 
	- fences
	- bollards (poles to block vehicles)
	- lighting
		- bright lighting discourages intruders
	- access badges
	- guards
		- visitor logs
		- expensive, can be socially engineered
	- video surveillance, cameras, sensors 
		- motion recognition cameras
		- object detection cameras
			- ex: making sure a jewel isn't moved
		- CCTV: displaying what a camera is recording on a screen
		- sensors:
			- infrared: look at heat radiation
			- pressure sensors: detect changes in pressure
			- microwave sensor: can detect motion thru materials and can work thru more temps than infrared
			- ultrasonic: set off by machinery / other vibrations
- detecting physical attacks
	- 3 types of physical attacks
		- brute force
		- RFID cloning
		- environmental attacks
			- eg: targeting heating / cooling system, sprinkler system, etc 
