## Architecture Principles

## Architecture Principle Decisions

### Platform Agnostic

Platform agnostic is a way of describing something that is portable between one or more platforms, whether cloud or on premises. The intent of remaining platform agnostic is to avoid vendor lock in, to protect against unnecessary fees, patents, and related business risks and to enable generically applicable solutions. 
This term can be used in many ways to different extents depending on the parties defining and implementing the solution. The following are some examples, showing how important the clarity of definition is when using this term.

##### 1. Purist Platform Agnostic
All aspects of the solution including architecture, supporting infrastructure, development language, installation process, operating system requirements and data stores are portable. This type has traditionally been developed in C and is smaller in scale due to the investment level required to accomplish its target. These solutions often cost as much or more on the testing portion of the development lifecycle as the actual design and development due because of the complex matrix that ensues when testing across all possible target infrastructures. A cornerstone of these implementations includes XCOPY/tarball style deployment due to a lack of common cross solution installer.

##### 2. Categorically Platform Agnostic
Several platforms will be selected as the potential targets of the solution to make commercially and business sound decisions for implementation. Two typical examples of these choices include the operating system and programming languages. The ability to develop, operate and support the solution is key and based upon corporate standards and available skillsets these become reasonable choices (e.g. if the entire company develops in Java it is reasonable decision is to use Java in the solution and limit the target platforms to where the Java Runtime is available). The architecture will remain like the Purist Platform Agnostic architecture in many cases, only differing in how the implementation begins to reduce the supported platforms.

##### 3. Provider-based Platform Agnostic
A platform independent architecture is created that introduces an abstraction via protocol, contract or convention over all services and infrastructure that may be specialized to the platform of choice. As an example, this variant allows for an architecture that dictates the use of a message queue (e.g. Service Bus, Rabbit MQ, Active MQ or Zero MQ), exposing it through either a common protocol such as AMQP or via a well crafted contract / façade. While most of this solution is platform agnostic out of the box, specialized or native infrastructure components and services can be used as a provider.

### Stack-based Platform Agnostic
A platform independent architecture in which supporting components are selected and delivered as part of the solution. The supporting components themselves are again platform agnostic in any of the categories listed. As an example, a solution could embed a database, message queuing system, etc. to reduce the required services of the underlying platform to lowest common denominator compute/storage/networking type of requirements.

[Continued from 3. provider-based platform agnostic – need to review whether the recommendation still holds] This form is the best of all worlds allowing for portability and avoiding vendor lock in while taking advantage of cost, support, and performance benefits of cloud native implementations.

When returning to customers that have opted for investing in platform agnostic implementations it is typically found that even 5 years later, they have not exercised the ability to migrate. The trade-off they made of cost, performance and often supportability for portability resulted in business advantage for negotiations but did not advantage them in the intended way. For this reason, variant 3 is the recommended approach to guide the platform agnostic architecture.

### Platform Openness 
In a time where customers are looking to advance, and pivot technologies platform openness has never been a more important choice. The term itself is rather nebulous and depending on the platform creator can result in “open solutions” that are not very open. Many people building open platforms will make statements such as “we will only use open standards”. While on the surface these statements are correct, the architects and implementers often imply additional intent, resulting in bad decisions and practices. To this effort it is recommended that the following definitions are used to help guide the architecting and buildout.

### Standard 
A norm or requirement for the execution of a repeatable task. While it is “usually” articulated in a formal document to establish the engineering criteria, methods, processes, and practices, it is not a requirement. As an example, Apache’s Parquet format is a commonly adopted method for file encoding although it may not be considered a standard in the same way that MQTT is. The important point is that Parquet is used by many companies with various libraries, tools and technologies that support it. This protects against “flash in the pan” technology decisions.

### Open Standard
An open standard is typically characterised by a standard that does not lock a customer in to a platform or impose undue costs. Typically, these have implementations offered tangentially to the definition that from multiple authors.  A key to an open standard is the lack of financial burden and or included patents or copyrights that may impose ownership or IP concerns for now or the future. 

The primary tenants of an open platform are 

* Data is exposed through open standards that allow for deep integration
* There are no patents or copyrights that will create financial or IP burdens for consumers
* Solution services, capabilities and feature-sets are available using open standards for customization and extension


An open platform DOES NOT mean that the platform data, services, capabilities, and feature-sets are only available through open standards. This allows for implementation specific performance, operations, and technology related decisions to offer a parallel path when required. For example offering the ability to access data from a data lake using an open standard such as OPC UA does not preclude the same data from being accessible via GRPC as well, enabling more advanced and lower latency paths. 

### Security and Compliance
Manufacturers have security and compliance requirements associated with various certifications and accreditations that must be proven and maintained. Additionally, many corporations layer their own enterprise and facility wide compliance on top that must be adhered to. Examples may include auditing, layered security, or data exfiltration protections. As a result, solutions built in these environments fail at the final stages for stop ship reasons related to security and compliance violations with one manufacturer identifying high double digits as their stop ship rate. To protect against this, the reference architecture will be built in a way that enables easy integration and adoption of the current security and compliance stances.
To support these requirements the following items should be viewed as requirements when the option arises.

* Network enabled services 
* Public endpoints should not be directly accessible without firewalls and security rules being applied
* Private over public circuits for data transfer when possible
* Ability to integrate network appliances with the customers existing appliance infrastructure (e.g. Network Virtual Appliances supported)
* Well known and accepted network architectures are adopted such as DMZs to protect the solution


### The Facility is an Extension of the Cloud
For most customers, the public cloud first became a concept in 2006 with the release of Amazon Web Services at which time it was viewed thought of as an outsourcing tool. Most customers at that time drove their companies in other directions as it was viewed as a Patriot Act or other data and IP risk. As this continued to unfold and other clouds such as Azure appeared on the market a movement started to convince enterprises that they can trust public cloud if they built the solution right and securely. Since this point constant evolutions in the security profile of these services have resulted in public cloud infrastructure often being more secure than the enterprise’s own data centers. 

Over the past 5 years customers have been building solutions that “burst to the cloud” or are “data center extensions”. While these efforts are valuable and drive a real business outcome, they do not provide a cloud first mindset. An example of this change is Microsoft’s own lead with the cloud shift that occurred several years ago, resulting in an entirely new level of innovation and fresh thinking. Following and expanding on this pattern it will be seen that the facilities are edges of the public cloud, just as they have always been viewed as edges of the enterprise. 

An example of this mindset is to shift from what analysis can be done in the cloud vs. what analysis cannot be done in the cloud due to risk because of network partitions etc. If these risks exist moving to a conversation around the minimum viable analytics options that must be executed on the edge to allow the business to function during the partition. 

This introduces the need to encourage a cooperative solution that extends from the cloud at the center to the outer reaches of the edges (facilities). This will include the decision to make all information accessible from or in the cloud. This does not mean all information must be streamed or low latency, but it should be available in the cloud for enterprise wide analytics and data mining.

### Information is the Center of Gravity
Over the years there have been several movements associated with centralize and decentralize motions, where it is currently in a centralize motion with the public cloud. As discussed in “The Facility is an Extension of the Cloud” the goal of the solution should be to make all information discoverable, accessible, and actionable based regardless on its location.

Information can be moved to and from the facilities and cloud as appropriate based upon different temperatures of information

### Cold Information
Cold information is typically moved to and from the cloud or facility based on a timer or the arrival of a file allowing for large batches as required for performance and scale. This has a higher latency and is typically used for post processing and analytics.  

### Hot Information
Hot information is typically moved to and from the cloud or facility through a streaming technique with a requirement of being to its endpoint with as low latency as reasonable. Examples of this may be tied to an alert on a piece of machinery that identifies a looming production outage.

### Warm Information
This information path is a combination of the Cold Information and Hot Information paths, where a condition that is transferred via the Hot Information path triggers a Cold Information transfer. For example, consider a rolling 2-minute window of vibrations that is being tracked for a generator. When a power spike occurs, it triggers a Hot Information data movement then immediately follows with a Cold Information movement of the vibrations file. 
Common data analysis patterns have existed for many years with two higher level domains that should be considered. 

### High Performance Computing (HPC) 
This is used when data is easier to move vs. coming up with enough processing power to perform the required operations over it. In this case the data is moved to the to the compute and processed in many smaller sets, only later being reconstituted into the results. 

### Big Data
In this is leveraged when data is too large or too high of velocity, so the compute is moved to the data to perform the operations. 
The solution should borrow concepts and decisions from these two domains when solving problems to identify locations of execution and where data should be maintained and at what velocity (information temperature). As an addition to this as much data as reasonably possible should be moved to the cloud for easy data science of the currently unknown scenarios, to avoid the requirement to do massive data moves in the future. Options should still exist to perform distributed analytics over the edges.

### Simplicity over Complexity
As history has taught us simplicity tends to win out over complexity if the simple solution can deliver on the required business needs. Reasons for this include lower chance of faults in operations and easier support by the responsible teams. When options exist and all solutions to the problem address the business solution select the simplest version with the assumption that adjustments can be made over time if required.

### Cost is a Factor
The technically correct or simplest architecture may not be the “right one” as a factor of cost. If the solution does not outweigh the strategic benefit or business value and gains it is not the correct architecture and should be adjusted. As this is a reference architecture there is no clear non functional requirement identifying a maximum cost so caution should be taken to allow for flexibility and scale on demand when possible, creating units of scale that are known entities of a defined capacity and cost, allowing the consumer to “dial their cost in” as appropriate.
