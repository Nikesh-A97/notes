# CDC - Walkthrough
---
##### Use Case
- Situtations require you keep two or more DBs synchronized with each other.
- A centralized DW that you need to keep up to date with one more more subsidiary DBs
- Reloading entire DBs into the DW is not realistic
	- This is because it takes time and a lot of computing resources
- A CDC DB monitors tables for changes and contains records for updates, deletions and insertions
- ![[Pasted image 20220513164039.png]]