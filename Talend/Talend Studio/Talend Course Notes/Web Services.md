# Web Services
---
##### What are web services
- Applications that communicate across a network
- Offer a standard way of inter-operation for different platforms and frameworks
- They are made available through a network endpoint
---
##### Web Services Description Langunage (WSDL)
- WSDL defines a contract between the consumer and web service provider
- Determines which operations are supported by the provider
- In Talend, operations on a web service can be invoked using the `tESBConsumer` component
---
##### `tESBConsumer` component
**Sample component configuration for request**
- Configure the consumer component to issue a SOAP request for city information by ZIP code
	- Provide the WSDL URL
	- Select **Port Name** and **Operation**

**Sample component configuration for processing response schema**
- The schema of the web service response can be complex
- Allows you to retrieve the schema and save it and can be saved to the repo
---
##### `tXMLMap` component
**Processing the XML web service response**
- Use the component to configure the request or process the response sent by the SOAP web service
- Similar to the `tMap` [[Data Processing#tMap Editor]|editor]] when processing the response data flow
	- Provides similar capabilities for routing and transforming data from one or more data sources
---
