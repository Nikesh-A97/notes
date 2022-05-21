# Using Repository Metadata
##### Metadata in the repo
- Can save information in the repository and reuse 
- DB connection settings, schemas, file properties, etc

##### Metadata Usage
- Can select parameters such as DB credentials and data schemas 
- Built In 
	- properties are  manually configured at the component level
	- local to the component and cannot be reused
- Repository 
	- Properties are inherited from metadata in the Repository
	- Stored in the Repository can be re-used by different components and across jobs

##### Generic Schema
- Can be saved in the Repo
- Can be used by any component as they are not linked to a component  
- Used to configure different components with the same schema

##### Updating metadata
- Any updated changes to repo metadata  can be propagated to all Components and Jobs using it
- Must select the Components to update
- Can isolate the component from update, this changes the property type to built in
- Manually changing property type cuts the link
- Configuration still remains in the component after being cut
- Run impact analysis to see links between metadata and components
- Duplicate repo if metadata is regularly updated
- Use context variables in metadata defn. so settings update according to selected context

