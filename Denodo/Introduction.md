# Introduction to DataVirtualization for Architects

---

## What is Data Virtualization

![[Pasted image 20230926091619.png]]
- It is possible to write back to the data sources

## Denodo Architecture

![[Pasted image 20230926092143.png]]
- VQL is language is based on standard SQL with additional constructs and operators
- For every query the inhouse Metadata storage is read first
- Cache is used to store specific views, data is persisted so data is fetched from the cache first
- Cache relies on external storage to store data
- Multiple interfaces to connect to the abstraction layer
- Recently added GraphQL and MDX query support

## How does it work
![[Pasted image 20230926093657.png]]
- The layer is built with 2 main components
	- The base views
	- Derived Views
- The query optimizer pushes down complex operations to the source layer as much as possible
- For compliance purposes, monitoring reports can be produced
- Users can customize the security layer to impose restrictions
- Any standard monitoring tools can access the Denodo monitoring API tool can access as it's delivered through JMX

## Denodo Platform Architecture
![[Pasted image 20230926101209.png]]

## Data virtualization Reference Architecture
![[Pasted image 20230926102508.png]]
![[Pasted image 20230926103929.png]]