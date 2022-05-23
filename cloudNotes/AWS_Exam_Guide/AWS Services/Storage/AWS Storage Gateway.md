# AWS Stroage Gateway
---
- A virtual device installed as a hypervisor or VM at on-premise DCs to integrate with AWS storage services

##### Storage Gateway
- File Gateway
	- Uses S3 Standard, IA, OZ IA as storage interface
	- Supports NFS and SMB protocol
	- Supports WORM (Write Once Read Many) file systems
- Tape Gateway
	- Uses Amazon Glacier
	- Stores data on virtual tape
	- Supports WORM
- Volume Gateway
	- Uses EBS
	- Supports iSCSI block protocol
- Stored Volume
	- Stores data locally
	- low-latencey access to data and backup
	- 32 volumes with sizes ranging from 1 - 16 TiB
- Cached Gateway
	- Stores recent data locally and the rest in S3
	- Can use 32 volumes with sizes ranging from 1 - 32 GiB    