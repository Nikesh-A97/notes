# AWS S3
---
![[awsCloudNotes#Amazon Simple Storage Service S3]]
![[awsCloudNotes#Amazon S3 Storage Classes]]
![[awsCloudNotes#Amazon S3 Storage Pricing]]
![[storage_classes.png]]
##### S3 Security
Private access by default, use bucket polices to enable different access 
- User-based
	- IAM Policies
- Resource-based
	- Bucket Policies
	- Bucket and Object Access Control Lists

##### Other information
- Versioning features, must be enabled at both source and destination
- S3 Transfer Acceleration - long distance  with minimum latency using CloudFront edge locations
- ACLs tp control acces to objects and buckets
- Provides cross account access
- Can replicate objects across region or the same
- Can host static websites

##### Amazon S3 Glacier
- Cheapest storage
- Retrieval Options
	- Expedited ( 1 - 5 minutes )
	- Standard ( 3 - 5 hours )
	- Bulk ( 5 - 12 hours )