# UNIT-1

### Intro : 
- Definition : (We have 2-3 definitions but this was the one that I found the most relevant and above all, meaningful)

    - IT infrastructure consists of the equipment, systems, software, and
    services combined and used in common across an organization, regardless of the
    mission/program/project. IT Infrastructure also serves as the foundation
    upon which mission/program/project specific systems and capabilities are
    built. 

- But here's the catch : the definition also depends upon the one who is actually using the infrastructure. 

<div align="center"> 

<image src="The infrastructure model.jpeg" width="300" height="300">

</div>


1) **PROCESS INFORMATION BUILDING BLOCK**: 
    - Organisations implement business processes for their serving their tasks which are mostly organisation specific . 
    - Example : Business processes for an insurance firm can be 
        - creating a policy 
        - ticket for claims
        - payment invoices 
        - $\dots$ and so on
    - Functional management is the part of the system management components that is responsible for configuring the system to serve business needs 

2) **APPLICATION BUILDIND BLOCK**: 
    - This includes $3$ types of blocks : 
        - **Client Applications** :
            -  Generally run on end-user devices like PC,laptops etc.
            - Example : Web Browser , Notepad etc. 
        - **Office Applications** : 
            - They provide a standard server based application for organization level usage. 
            - Example : mail servers , portals, collaboration tools etc. 
        - **Business Specific Applications** :
            - They are one level up of Office application with very high specificity .
            - Example : 
                - **CRM** : Customer Relationship Management
                - **ERP** : Enterprise Resource Planning
                - **SCADA** : Supervisory Control And Data Acquisition
                - Some applications that are designed for specific business applications like **IMS** ( institute management system). 
            
    - Applications management is the part of the system management components that is responsible for configuring the system for other technical operations. 

3) **APPLICAITON PLATFORM BUILDING BLOCK**:
    - Many Application need some additional services (known as application platforms) that enable them to work. 
    
    - It's  more like a framework you need to actually build a working application but the framework is a bit more of a fundamental application. Like you'll need Sk-Learn or pytorch to build a machine learning or deep learning application. 
    - There are mainly $4$ types of Application  platform building tools : 
        - **Front end Servers** :
             - Act as web server to host applications that provide end user interaction with the application via web browser ( basically servers that host your website).
             - Example : 
                    - Apache HTTP Server 
                    - Microsoft Internet Information Services – IIS


        - **Application Servers**: 
            - The containers running the actual application . 
            - Example : 
                - IBM WebSphere 
                - Apache Tomcat
                - Red Hat JBoss
                - Windows .Net 

        - **Connectivity**: 
            - Consists of FTP servers, Extraction, Transformation andLoad (ETL) servers, and Enterprise Service Buses (ESBs).
            - Basically it's the services and infrastructure that allow different components of an application to communicate and exchange data with each other i.e  both within the application and with external systems. 
            - Example :
                -  Microsoft BizTalk
                -  the TIBCO Service Bus
                -  IBM MQ
                -  SAP NetWeaver PI 
        - **Databases**: 
            - Store the data. 
            - Example : 
                - Oracle RDBMS
                - IBM DB2
                - Microsoft SQL Server
                - PostgreSQL
                - MySQL

    - This part of the infrastructure is mainly managed by system managers who specialize in a specific technology. 
    
4) **INFRASTRUCTURE BUILDING BLOCKS**: 
    - This mainly consists of the hardware and protocol aspect of the infrastructure. 
        - **END USER DEVICE**:  PCs, laptops, mobile devices, printers etc. 
        - **OPERATING SYSTEM**
        - **COMPUTE** : Physical and virtual devices in datacentre. ( basically servers )
        - **STORAGE**
        - **NETWORKING** : mainly to connect all components. 
        - **DATACENTERS** : locations that host all the hardware. 



### NON FUNCTIONAL ATTIRBUTES
- They describe the qualitative behaviour of a system. 
- They may not be related directly to the primary functionalities of a system, but they do have a huge impact on the performance and overall reliability of the whole infrastructure. 

- They are : 
    - **Availability**
    - **Scalability**
    - **Reliability**
    - **Stability**
    - **Testability**
    - **Recoverability**

- Mainly we'll focus on security, performance and availability. 
- Many of the non functional attributes of an application are delivered by relying on the infrastructure. This can be realised by the below points : 

    - An application using an infrastructure that has several single point failures will not work out well no matter how well the application is built. 
    - If the infrastructure is not highly available then no matter the design of the application, it simply can't be scaled to a handle heavy usage. 


### AVAILABILITY
- As we know, everyone wants their services and systems available all the time(which can't be guaranteed ever) as the downtime or unavailability is noticed pretty quickly.
(Classic Example: How do we feel when any messaging service or any social media gets down.) 
- The availability of a system is usually expressed as a **percentage of uptime** in a
given time period (usually one year or one month). 
- What is uptime ? The total time for which the services were available for active use. 
- Typical requirements used in service level agreements today are **$99.8\%$ or $99.9\%$ availability per month** for a full IT system. 
- To meet this requirement, the availability of the underlying infrastructure must be much higher, typically in the range of $99.99\%$ or higher.
- $99.999\%$ uptime is also known as **carrier grade availability**.
- Factors used to calculate availability are : 
    -  **Mean Time Between Failures(MTBF)** : average time that passes between failures.
    - **Mean Time To Repair (MTTR)** : time it takes to recover from a failure.
    <div align="center">
    <image src="mean time between failure.jpg">
    </div>

---

- MTBF expressed in hours (how many hours will the component or service work without failure). 
- Formula
<div align="center">

**MTBF** $=\frac{\textbf{total time of operation}}{\textbf{number of failures}}$

</div>

- Method of calculation : 

    - testing time $=3$ months
    - number of disks $=1000$
    - Number of disks that failed in that duration = $5$
    - $\implies$ for one year, $5\times4=20$ disks would have failed (extrapolating the $3$ month testing results to a year) or alternatively we can say that the system failed $20$ times. 
    - Total run-time of disks $=1,000 \times 365 \times 24 = 87,60,000$
    - MTBF ${=\frac{\textbf{total  time of operation}}{\textbf{number of failures}}=\frac{87,60,000}{20}=4,38,000}$

    - Since here we're **extrapolating** the MTBF value for $1$ year (by calculating the values for $3$ months and then extending those values for $1$ year), in reality it only shows the uptime for initial months extending up-to $1$ year. 
    
    - UNOFFICIAL NOTE : 
         - **Why to extrapolate ?** In reality no one got time to test out this thing for a year. That's why keep things practical and test out for $1$ month or $3$ months and then say that yes , this shit can go on this hours of uptime before it ducks up. 

--- 

- **MTTR** is generally kept very low by having a service contract with a supplier and keeping some spare parts on-site for speedy repair. 
- **NOTE:** : 
    -  $\textbf{availability}\propto \frac{1}{\textbf{MTTR}}$ 
    -  $\textbf{availability}\propto \textbf{MTBF}$ 

<div align="center">

$\textbf{Availability} = \frac{\textbf{MTBF}}{\textbf{MTTR}+\textbf{MTBF}}\times 100\%$

</div>

- **Serial Availability** : when a **failure in one part causes the failure of the entire system**,the availability of such system is called Serial Availability. 

- For such systems availability is calculated by the product of availability of all the components. 

- Formula : 
<div align="center">

$\textbf{Serial Availability}=\prod_{}^{x \in components}Availability_{x}$

</div>



<div align="center">

<image src="serial availability.jpg" height="300" width="500">

</div>

- Say all the above said components are in series, therefore you to calculate the availability of the system, you need to multiply all the values in the availability column
i.e 
<div align="center">

$\text{availability}=0.9999200 \times 0.9999200 \times 0.9999733 \times 0.9999920 \times 0.9999840 \times 0.9999680 = 0.9997733 = 99.97733\%$

</div>

- $\implies$ The more components a system includes (and each component is critical for the total system) the lower the total availability becomes. 

- Hence we try to avoid many systems in series and rather keep them in parallel. 
- For parallel systems : 
- Say :
    - There are $N$ components out of which at max $M$ can fail. 
    - $\implies A_{M,N} = \sum_{i=0}^{M}\frac{N!}{i!\times(N-i)!}\times A^{N-i}\times(1-A)^i$
    - Special case given in the book : $M=1,N=2$
    - $A=1-(1-A_{x})^2$ 
    - $A_{x}$ is the availability of the component $x$ ( basically $2$ same type of components in parallel)
    ([SOURCE](https://eventhelix.com/fault-handling/system-reliability-availability/))


### SOURCES OF UNAVAILABILITY
- Human Errors
- Software Bugs
- Physical Defects
- Environmental Effect ( Earthquakes, Fire accidents etc.)
#### BATHTHUB CURVE 

<div align="center">

<image src="bathtub curve.jpg">

</div>


- In most cases the availability of a component follows a so-called bathtub curve.
- This says that a **component failure is most likely when the component is new**. 
-In the first month of use the chance of a components failure is relatively high. Sometimes a component doesn't even work at all when unpacked for the first time. This is
called a **DOA component – Dead On Arrival**.
- When a component still works after the first month, it is likely that it will continue working without failure until the end of its technical life cycle. 

### AVAILABILITY PATTERNS 
- **SPOF ( Single Point Of Failure )** is a component in the infrastructure that if fails can lead to downtime for the entire system ( complete disaster ). 
- One solution can be **RAID : Redundant Array of Independent Disks** can be used to handle SPOF in storage systems as  failure of one disk does not affect the availability of the storage system. 
- Other methods include Server Cluster, Double Networks, Dual Datacentres etc but they themselves are also not very SPOF proof. They may end-up sharing some common infrastructure behind the scenes and may lead to an unforeseen SPOF. 

- More reliable ways of making infrastructure SPOF proof are **redundancy, failover, and fallback**.

#### REDUNDANCY
Mainly involved **duplication of critical components in a single system**, to avoid
a SPOF. Redundancy is usually implemented in power supplies (a single component having two power supplies; if one fails, the other takes over and life goes on... ), network interfaces, and SAN HBAs (Host Bus Adapters) for connecting storage.

#### FAILOVER
It's an **automatic/semi-automatic switch-over to a standby system (component)**, either in the same or in another datacentre, upon the failure or abnormal termination of the previously active system (component). Examples Windows Server failover clustering, VMware High Availability and (on the database level) Oracle Real Application Cluster (RAC).

#### FALLBACK
It's a **manual switchover to an identical standby computer system in a different location**, typically used for disaster recovery. There are three basic forms of fallback solutions:
- **Hot site** : A fully configured fallback datacentre, fully equipped with power and cooling. The applications are installed on the servers, and data is kept up-to-date to fully mirror the production system. Sites of this type requires constant maintenance of the hardware, software, data, and applications to be sure the site accurately mirrors the state of the production site at all times.

- **Warm site** :It's a computer facility **readily available with power, cooling, and computers, but the applications may not be installed or configured**. But external communication links and other data elements, that commonly take a long time to order and install, will be present. It **needs less attention when not in use** and is much **cheaper**.

- **Cold site** : It's a site **ready for equipment to be brought in during an emergency, but no computer hardware is available at the site**. The cold site is **a room with power and cooling facilities**, but computers must be brought on-site if needed, and **communications links may not be ready**. Applications will need to be installed and current data fully restored from backups.
 

**NOTE** : SKIPPING BUSINESS CONITNUITY(Page No. 55 of PDF SECTION 4.4.4) (REASON : I didn't find it of much importance)


### PERFORMANCE 
- Generally disregarded when the system is performing fast and efficiently but highly criticized when the performance is slow and inefficient. 
#### PERCEIVED PERFORMANCE
- Refers to how quickly the **system appears** to perform a given task. 
- The user may be aware of the fact that the task assigned is complex and time consuming but just to make the user satisfied and calm, we tend to provide progress bars or splash screens so that the user may be able to see the progress of the task they assigned. 

### PERFORMANCE DURING INFRASTRUCTURE DESIGN
- We intend to support a basic required performance of a system even under increased load.
- Not only under normal state where systems work as expected but during special states, it should also have a minimum performance benchmark. These special states are mostly 
    - part failure
    - system maintenance 
    - backup
    - batch processing
- To determine the performance of a system, we use the below methods : 
    - **BENCHMARKING** 
        - A benchmark uses a specific test program to assess the relative performance of an infrastructure component. 
        - Benchmarking is used to assess the performance characteristics of computer hardware.
        - Example : 
            - The floating-point operation performance (**Floating Point Operations Per Second – FLOPS**)  
            - Number of instructions per second (**Million Instructions Per Second – MIPS**) of a CPU.
        - They measure the raw performance, not accounting the typical usage components under consideration.
    - **USER VENDOR BENCHMARKING**
        - Basically going to the big old players who are in the industry of IT Infrastructure management like oracle, IBM, AWS etc. 
    
    - **PROTOTYPING**
        - Build a prototype to estimate the performance at an early stage. 
        - This acts as a proof of concept and should be used to test the most tough/complex part of the project/infrastructure.
        - A proof of concept shows this at a time not too much money is spent yet and shows to both the project team and the customer that the project's highest risk has been taken care of .
        
    - **USER PROFILING**
        - It's used to predict the load a new software system will pose on the infrastructure, and to be able to create performance test scripts that put representative load in the infrastructure before the software is actually built.
        ( Basically predicting the usage)

        - This can be done by defining a number of user groups of the new system (also known as personas that will typically use our system) and by creating a list of tasks they will perform on the new system.
        
        - A limited number of personas will be interviewed and to get an idea of how they're going to use the system. This translates to a list of task that will be performed on the system. 

        - For every task we can an estimation can be given on as to how much and how often will the user use the system's resources and functionalities to get a task done. 

        - **SUMMARY** : Basically estimating the processes and their resource requirements for getting a certain number of jobs done. 

### PERFORMANCE OF RUNNING SYSTEMS 

1) **BOTTLENECKS**
- Performance of a system is based on the performance of all its components, and the interoperability of various components. 
- At times it happens that under high load, a **component may reach it's best performance or capacity**. 
- This may eventually cause the **overall system to slow down due the the limited performance of that single component**. 
- Therefore the **performance of a system as a whole is totally dependant on the performance of that one singe component**. 
- This component is referred to **bottleneck**. 


#### **BOTTLENECK LAW**
According to the **Bottleneck law**, every system, regardless of how well it works, has at least one bottleneck that limits its
performance. This is perfectly okay when the bottleneck does not negatively influence performance of the complete system under the highest expected load.

#### PERFORMANCE TESTING 
1) LOAD TESTING : Shows the system performance under the expected load. 
2) STRESS TESTING : Shows the system reaction to extreme load. Mainly done to check the breaking point of the system .
3) ENDURANCE TESTING : Shows system behaviour under expected load for a prolonged duration. 
<div align="center">

<image src="performance breakpoint.jpg" height="300" width="300">

</div>

- To carry out performance testing , the following process is followed : 
- **TLDR** : emulate some users using $1-2$ servers and use $1$ server to coordinate tasks and collect metrics for reporting and analytics. Generally the load is increased gradually to see the performance as the usage increases. Also the testing should be done in a production like environment because the development environment
has different settings and configurations from production and may provide unreliable results. 


### PERFORMANCE PATTERNS 
- Performance on the upper layers can be improved by optimising the application and database than just bluntly adding compute power. 
- **CACHING** 
     - retaining frequently used data in high speed memory, reducing access times to data
      thereby improving the overall performance.   
- **DISK CACHING**
     - Disks being mechanical in nature are inherently slow. 
     - To speed up reading of data, they implement disk caching. 
     - This is generally implemented within the storage block itself (the very hardware)
     but is also present in the OS as well. 
- **WEB PROXIES**
     - When users searches some information on internet, instead of fetching all requested data from the internet every time, the previously accessed data can be cached in a proxy server and fetched from there. 
     - This not only gives the user a faster speed perception but also reduces the overall load on the servers to query and get details. 
- **OPERATIONAL DATA STORES**
     - It's a read-only replica of a part of a database. 
     - Most read requests are redirected towards the ODS instead of the main database thereby reducing the load on the main Database. 
- **FRONT END SERVERS**
     - They store the most accessed parts of a web page like landing page or static images thereby reducing the load on the main web environment. 
- **IN MEMORY DATABASES**
    - Here, the whole database can be run from memory instead of from disk. 
    - In-memory databases are used in situations where performance is crucial (like in real-time SCADA systems). 
    - Special arrangements must be made to ensure data is not lost when a power failure occurs. 
- **SCALABILITY** 
    - It means the ease with which new components can be added or modified to the existing system to handle more load. 
    - There are 2 types of scaling : 
        - **VERTICAL SCALING** 
             - here we add resources to a single component. 
             - generally we add CPUs or memory to a server. 
             - 
        - **HORIZONTAL SCALING**( aka scale out )
             - Here we add more components to the infrastructure, such as adding a new web server in a pool of web servers, or adding disks in a storage system. 
             - It works best when the system is partitioned because in that case, individual components can be scaled up.

            <div align="center">

            <image src="partitioned system.jpg">

            $\Downarrow$

            <image src="web server addition.jpg">

            $\Downarrow$

            <image src="database addition.jpg">

            </div>

             - **NOTE** : Doubling the number of components does not necessarily double the performance. Because of overhead (for instance, the extra scheduling needed in multiprocessor systems, or buffering and link state issues in network connections) doubling components usually only provides about $70\% - 80\%$ performance increase. Adding more components leads to even more diminishing returns.
             - **TLDR For Note** : Doubling the resources also increases the efforts for scheduling the resources and increased network load. Doubling the resources only gives about $70\% - 80\%$ performance increase and not $100\%$ increase.
- **LOAD BALANCER**
    - Load balancer uses multiple components – usually servers – that perform identical tasks. 
    - Then redistributes the tasks to members in a server farm. 
    - Load balancer observes the current load on each server in the farm and redirects the  incoming requests to the least busy server. 
    - More advanced load balancers can spread the load based on the number of connections a server has, or the measured response time of a server. 
    - For a load balancer to work, servers must be functionally identical to each other
    - For instance, each web server in a load balancing situation must be able to provide the same information. 
    - Furthermore, the application running on a load balanced system must be designed to handle requests that can be handled by a different server. The application (or at least the load balanced parts of the application) must be stateless for this to work.

- **HIGH PERFORMANCE CLUSTER** 
     - High performance clusters provide a vast amount of computing power by combining many computer systems. 
     - Usually a large number of servers are used, connected by a high-speed network like gigabit Ethernet or InfiniBand. Such a combination of relatively small computers can create one large supercomputer.
     - **TLDR** :  Combine many computers into a cluster and connect them via high speed network and they act like a single large supercomputer. 

- **GRID COMPUTING**
     - **TLDR** : Many High Performing Clusters that are spread across different geographical locations. 

- **DESIGN FOR USE**
     - **TLDR** : Basically the design of the architecture should be according to the application it's going to be used for. 





# UNIT 2

### TCP IP PROTOCOL SUITE 
- TCP IP is a $4$ layered model. 
- The layers and the corresponding protocols used in them are : 
1) **APPLICATION LAYER**
     - It's responsible for end-to-end communication and error-free data delivery.
     - Main protocols present in this layer : HTTP , SSH , NTP
2) **TRANSPORT LAYER**
     - This layer exchanges data receipt acknowledgments and retransmit missing packets to ensure that packets arrive in order and without error. 
     - Main protocols present in this layer : TCP , UDP
3) **NETWORK LAYER**
     - Responsible for routing packets of data from one device to another across a network. It does this by assigning each device a unique IP address, which is used to identify the device and determine the route that packets should take to reach it.
     - Main protocols present in this layer are : IP , ICMP , ARP
4) **NETWORK ACCESS LAYER**
     - Responsible for generating data and initiating connection requests. It operates on behalf of the sender to manage data transmission, while the Network Access layer on the receiver's end processes and manages incoming data. 
     - Main protocols present in this layer are : LAN , WAN 


### LAN ( LARGE AREA NETWORK )
- Used to connect network devices in such a way that personal computers and workstations can share data, tools, and programs. The group of computers and devices are connected together by a switch, or stack of switches, using a private addressing scheme as defined by the TCP/IP protocol. 
- LAN covers a smaller geographical area (approximately few kilometres). 
- Data transmission speed is fast given the number of connections made. 
- Can be used to share peripheral devices such as printers and scanners.


### MAN ( Metropolitan Area Network )
- covers a larger area than that covered by a LAN and a smaller area as compared to WAN . 
- Range is about $5-50km$.
- It covers a large geographical area and may serve as an ISP (Internet Service Provider).


( DIDN'T FIND ANYTHING ABOUT HEIRARCHIAL LAN DESIGN )

### Multiservice Access Technologies 
- They are the network system infrastructure which allow multiple communication service like voice, image, video and internet etc. 
- They're designed to efficiently support diverse traffic types while optimizing bandwidth and simplifying network management.
- Mainly has $3$ layers :
1) **ACCESS LAYER** 
     - The most diverse part of the architecture that connects the end user to service provider's network. 
     - It supports transmission and receiving of diverse media types. 
     - Handles initial traffic aggregation and ensures reliable connectivity.
     - Supports both active (powered network elements) and passive (no powered components) solutions.
2) **AGGREGATION LAYER**
     -  collects traffic from multiple access nodes and prepares it for transport to the core network.
     - Implements VLANs, QoS policies, and traffic shaping.
3) **CORE LAYER**
     - connects the aggregation layer to the internet, data centres, and other service networks.
     - Routes large volumes of aggregated traffic efficiently.
     - Ensures redundancy, load balancing, and low-latency paths.
     - Supports signalling and session management for multiservice applications.

### WiFi Protocols 

- Full Form  : Wireless Fidelity
- The protocols were developed by IEEE
- Each standard has $2$ parameters :  
     - Speed : Base Unit : Mbps ( Mega bytes per second )
     - Frequency : Works in $2$ frequency bands : $2.4GHz$ and $5GHz$

<div align="center">
<image src="wifi protocols.jpg">
</div>


### VPN
- Virtual Private Network
- Acts as a private tunnel for your internet traffic, preventing anyone from tracking and monitoring online activity. 
- **WORKING**
     - Upon activating a VPN , it connects to a server provided by the VPN provider. 
     - Encrypts the data that is to be transmitted. 
     - The internet traffic is now routed through the VPN server, which can be located in any country. This makes it appear as though the browsing is being done from the server's location, masking our actual IP address.
     - Once the data reaches the server, it's decrypted and then sent to the desired location.
     - Once the response is received, the same route is followed for taking back the response to the user. 

| **VPN Type**      | **Description**                                                                 | **Use Case**                               | **Security** | **Speed**   |
|-------------------|---------------------------------------------------------------------------------|-------------------------------------------|-------------|------------|
| Remote Access VPN | Allows individuals to connect remotely to a network from anywhere.               | Remote workers, traveling professionals   | High        | Moderate   |
| Site-to-Site VPN  | Connects two networks securely over the internet.                               | Businesses with multiple locations        | Very High   | High       |
| Mobile VPN        | VPN for mobile devices ensuring uninterrupted access while switching networks.  | Healthcare, logistics, field workers      | High        | Moderate   |
| MPLS VPN          | A secure, efficient, and scalable solution for large enterprises.               | Large enterprises with multiple office sites | Very High   | Very High  |
| PPTP VPN          | An older VPN protocol known for speed but lacks security.                       | Legacy systems, basic VPN needs           | Low         | Very High  |
| L2TP/IPsec VPN    | Combines Layer 2 Tunnelling Protocol with IPsec for better security.             | Corporate environments, reliable security | High        | Moderate   |
| OpenVPN           | An open-source VPN protocol known for its flexibility and strong encryption.    | Advanced users, custom setups             | Very High   | Moderate   |
| IKEv2/IPsec VPN   | A fast and secure protocol that excels in mobile device use.                    | Mobile users, stable connections          | Very High   | High       |


### WAN IP Addressing 
- A WAN IP address is the public-facing address assigned to the router by your Internet Service Provider (ISP). It identifies your network to the outside world.

NOTE : NEED TO DIVE INTO MORE DETAIL EVEN FROM SYLLABUS POINT OF VIEW.


### STORAGE BUILDING BLOCKS 
<div align="center">
<image src="storage model.jpg">
</div>

- **DISKS**
     - Mainly $2$ types are used : 
        - Mechanical hard disks
        - Solid State Drives (SSD)
     - Disks are connected to disk controllers using a command set. 
     - Command sets are nothing but protocols for communication between device and disk. 
     - There are 2 types of command sets : 
         - ATA :  Advanced Technology Attachment(aka IDE) 
             - Uses simple hardware. 
             - Mostly used in PCs
         - SCSI : Small Computer System Interface
             - set of standards for physically connecting and transferring data between computers (mostly servers) and peripheral devices, like disks and tapes. 
     - **MECHANICAL HARD DISKS**
         - Consist of vacuum sealed cases with one or more spinning magnetic disks on one spindle. 
         - Has many number of read/write heads that can move to reach each part of the spinning disks. 
         - Types : 
             - Serial ATA (SATA) disks
             - Serial Attached SCSI (SAS) disks
             - Near-Line SAS (NL-SAS) disks
    - **SOLID STATE DRIVES**
         - Doesn't have moving parts. 
         - It's based on Flash technology which is a semiconductor-based memory that preserves its information when powered off. 
         - SSDs are connected using a standard SAS disk interface. 
         - Due to no moving parts, they're faster than mechanical disks. 

### DISK CAPACITY : KRYDER'S LAW 
- the density of information on hard drives has been growing at a rate, increasing by a factor of $1000$ in $10.5$ years, which roughly corresponds to a doubling every $13$ months. 
<div align="center">
<image src="kryders law.jpg">
</div>

- **TAPES**
     - Tapes are suitable for archiving, since tape manufacturers guarantee a long life expectancy. 
     - Not suited for large storage of data. 


- **CONTROLLERS**
     - They connect disks and/or tapes to a server, typically implemented as a PCI expansion boards in the server.
     - Controllers implement high performance, high availability, and virtualized storage using RAID (Redundant Arrays of Independent Disks) technology. 
     - A controller virtualizes all physical disks connected to it, presenting one or more virtual disks, called Logical Unit Numbers (LUNs). 
     <div align="center">
     <image src="lun.jpg">
     </div>
     - Here the all the physical disks are fragmented into small pieces call physical extent. 
     - Using these physical extents, new virtual disks (LUNs) are composed and presented to the OS. 


### RAID
- There are $5$ levels of implementation for RAID : 
     - **RAID $0$ -**  Striping
     - **RAID $1$ -**  Mirroring
     - **RAID $5$ -**  Striping with distributed parity
     - **RAID $6$ -**  Striping with distributed double parity
     - **RAID $10$ -** Striping and Mirroring

[SOURCE FOR RAID THEORY](https://www.prepressure.com/library/technology/raid)

- **RAID $0$** : **STRIPPING**
    - TLDR : Data split into $2$ blocks and they are made available at the same time. This makes the IO operations fast. 
    - Problem : Fault intolerant. If one drive fails, data for that drive is lost.  
<div align="center">
<image src="raid0.jpg">
</div>

- **RAID $1$** : **MIRRORING**
     - TLDR : Take $2$ drives and make the same data available on both the drives . 
     - Problem :
         - Due to double writing of data, it's not memory efficient.  
         - That means the failed drive can only be replaced after powering down the computer it is attached to. 

<div align="center">
<image src="raid1.jpg">
</div>


- **RAID $5$** : **STRIPPING WITH PARITY**
     - TLDR : Data is stripped across the drives ( minimum $3$ required ). parity checksums of all the data blocks is distributed across all drives. So in case one drive fails, it's data can be reconstructed back . 
     - Problem  :
         - Small Throughput
         - Slow when data volume is large
          
<div align="center">
<image src="raid5.jpg">
</div>

- **RAID $6$** : **STRIPPING WITH DUAL PARITY**
     - TLDR : Same a RAID $5$ with the parity being duplicated . 
     - Problem : 
         - In an event of drive failure, throughput is severely affected. 
         - In case of drive failure, rebuild will take long time. 
          
<div align="center">
<image src="raid6.jpg">
</div>



- **RAID $10$** : **STRIPPING & MIRRORING**
     - TLDR : Mix of RAID $0$ and RAID $1$ i.e (figure will explain better). 
     - Problem : 
         - storage inefficient 
          
<div align="center">
<image src="raid10.jpg">
</div>


###  DATA DEDUPLICATION 
**TLDR** :  The deduplication system maintains a hast table which contains the mapping of memory pointers to hash value of the input data. Any duplicate data will not be stored (if the hash value was found in the hash table) but a pointer to the matching segment will be created.
<div align="center">
<image src="deduplication.jpg">
</div>
 
### CLONING AND SNAPSHOTS
- Both the processes intend to create a backup of the data. 
- **CLONING** : Creates one full-copy of the disk. This cloned disk can be split-off at a specific point in time, for instance to make a backup of the data, without touching the original disks that are still on-line (i.e the data on original disk is still under change due to write/delete operations).

- **SNAPSHOTS** : Snapshot represents a point of time of the data on the disk. 
From the time the snapshot is active, no write operation is allowed. All write operation is done in a separate disk volume in memory. read operations are permitted for the frozen data. In case of read operation for updated data, the data is retrieved from the disk volume. A backup is created while the snapshot state is active and as soon as it's over the data waiting to be written on the original data on the disk is written. 


### THIN PROVISIONING 

- Before jumping there , what's provisioning ? 
- It's basically the allocation and configuration of resources like storage, compute power, network capacity etc. 
- Now comes the $2$ types : 
- **THICK STORAGE** : 
     - when a storage volume is created, the entire allocated space is immediately reserved for that volume, even if it is not fully used . 
     - one user might have access to $40GB$ of storage. In thick provisioning, that user would continue to have exclusive access to the full $40GB$ even if they only use $20GB$.
- **THIN PROVISIONING** : 
     - It's based on the principle of overcommitting resources i.e presenting more logical storage to the user than the physical storage actually available. 
     - But how it's done ? 
     - A virtual storage is created ( way more than the actual physical storage in general say $1TB$) but only a small part of the physical memory is truly allocated ( say $100GB$) 
     - With time , as the application needs memory, more memory is allotted to it.
     - The resource consumption is monitored and resources are freed as soon as the usage goes low.  

### DIRECT ATTACHED STORAGE ( DAS )
- Basically local storage. 
- A storage system where one or more disks are connected via SATA protocol to a controller. 
- This controller provides a disk block to the computer organized by LUNs. 
- These LUNs are then used by OS to manage memory.
- In serves, DAS is mainly used for boot device or caching. 

### STORAGE AREA NETWORK (SAN): 
- A specialized storage network that consists of SAN switches, controllers and devices. 
- It's task is to connect large storage to multiple servers . 
- SAN physically connects these servers disk controllers via special networking technology like Fibre Channel 
- Data is accessed through LUNs (Logical Unit Numbers), which are partitions of storage volumes.

### Hardware Bus Adapters (HBAs) : 
- A hardware interface card that acts as a bridge between a server and storage devices in a network (Like SANs). 
- It's main job is to offload data transfer tasks from the server's CPU and provide high-speed data transmission between the server and storage devices. 



### SAN CONNECTIVITY PROTOCOLS 
- Needed to connect Storage Devices to Servers via SAN. 
- There are $3$ : 
     - Fibre Channel
     - FCoE
     - iSCSI
    
- (Syllabus has Fibre Channel I'll do that only)
- **FIBRE CHANNEL** :   
     - $2$ Layer Network protocol specially for transporting storage data blocks. 
     - operates at speeds of $2 \text{Gbit/s}$, $4 \text{Gbit/s}$, $8 \text{Gbit/s}$, or $16 \text{Gbit/s}$. 
     - Fibre Channel can run on both twisted pair copper wire (i.e. UTP and STP) and fibre optic cables.
     - This Protocol is very reliable, with guaranteed zero data loss. 
     - Each Fibre Channel device has a unique World Wide Name (WWN), which is similar to an Ethernet MAC address.
     - Fibre Channel can be implemented in $3$ different topologies : 
         - **Point-to-Point** :  Two devices are connected directly to each other.
         - **Arbitrated loop** (aka FC-AL) :  In this topology, all devices are in a loop. Most early Fibre Channel systems worked this way.
         - **Switched fabric** - All devices are connected to Fibre Channel switches, a similar concept as in Ethernet implementations. Most implementations today use a switched fabric.


### Network Attached storage (NAS) :
- It's a network device that provides a file system storage to the OS on a regular TCP/IP network. 
- It's generally an appliance ( basically it's own OS and hardware )that implements file services and holds the disk on which the data is stored ( In some cases NAS is used only as a gateway that provides file services but actual storage is present elsewhere) . 
- **Clustered NAS** : A NAS that uses distributed file system running simultaneously on multiple servers .


### SAN Vs NAS: 
|               SAN                     |               NAS                             |
|---------------------------------------|-----------------------------------------------|
| Provides block level storage          | Provides a shared file system                 | 
| Provides access to one server per LUN |Multiple servers can access the same filesystem|
| No such feature available             | Uses active directory service or LDAP for managing file permissions| 
|    No file level services available   |Provides redundancy, load balancing, replication, and snapshot technology|
|No default support for file recovery available | File recovery features like file-level snapshots and file un-deletion available| 



### OBJECT STORAGE : 
- A storage architecture where the data is stored as objects. 
- The object is defined as a file with metadata and a globally unique identifier called Object ID. 
- Metadata can be filename , date and time stamps, owner, access permissions, the level of data protection, and replication settings . 
- Each file ( object ) can be uniquely identified and accessed using it's object storage without knowing it's actual location. 
- Data in object storage can't be modified. Instead, if a file is to be modified, the original file must be deleted and a new file must be created, thereby creating a new
object ID. 
- Due to this, it's not suited for data needing frequent access and modification.
- But this is useful for storing archives, backups etc which isn't updated much.




### STORAGE SECURITY 
- Data at rest : This is data in the stored in disks and drives. 
- **DISK ENCRYPTION** : 
     - **Self-Encrypting Drives (SEDs)** : 
         - It's built on the device hardware itself.  
         - The data is auto encrypted before being written on the disk. 
         - Encryption keys are again stored in the disk itself. 
         - Authentication is required to access the data i.e the user needs to provide a password to start the boot sequence for decryption. 
     - **Cryptographic Disk Erasure (CDE)** : 
         - It's meant to delete the encryption key on the disk.
         - Same as deleting the disk data as the encrypted data can no longer be read from the disk. 

     - Disk encryption is primarily useful when disks are physically lost or stolen.
     - Disks in data-centres are rarely stolen, unlike laptops, desktops, or removable media.
     - Maintenance contracts between the vendor and data-centre may require returning failed disks to vendors.
     - If a failed disk cannot be erased, returning it without encryption risks data exposure.

- **TAPE ENCRYPTION** :
     - Since tapes are easy to carry, therefore encrypting them becomes more important than ever. 
     - self-encrypting tape drives are be used to encrypt data on the tapes. 
     - LTO tape drives come with AES-256 encryption in their hardware.
     - To access a tape, the original keys must be used to decrypt the data, as without keys, encrypted data becomes inaccessible and is effectively destroyed. 

- **SAN ZONING** :
     - A method in which Fibre Channel Devices are organised into logical groups within a SAN fabric. 
     - Devices within a SAN can only communicate with others in the same zone.
     - This restriction makes it harder for hackers and viruses to access all disks in a SAN.
     - The SAN switch inspects all packets on the fabric. It only forwards packets to ports that are authorized to receive them.
     - Zoning ensures that operating systems only see the LUNs associated with them, instead of all LUNs in the SAN. This prevents operating systems from altering data on disks that don't belong to them.

- **SAN LUN masking** : 
     - In this methodology, LUN available to some hosts and unavailable to other hosts. 
     - LUN masking is implemented primarily at the HBA level, not in the SAN switch.






# UNIT 3
### CLOUD COMPUTING
- It refers to the setup where the storage of data , access of data and computations on data , all $3$ are done on remote servers hosted on internet instead of using local server or hard-drive. 

### LAYERD ARCHITECTURE OF CLOUD COMPUTING 
- There are $4$ layers primarily : 
1) **APPLICAITON LAYER** :
     - This is the place where the applications based on cloud are located. 
     - They take advantage of automatic scaling for better performance, functionality and low cost. 
     - Applications are divided into Execution layers and Application layers.
     - Application layer determines whether communication partners are available or whether enough cloud resources are accessible for the required communication . 
     - To be specific , Application layer is responsible for processing IP traffic handling protocols like Telnet and FTP.

2) **PLATFORM LAYER** : 
     - The operating system and application software make up this layer.
     - The objective of this layer is to deploy applications directly on virtual machines. 
     - The user should be able to rely on the platform to provide them with Scalability, Dependability, and Security Protection. 
     - The platform layer's goal is to lessen the difficulty of deploying programmers directly into VM containers.
    
3) **INFRASTRUCTURE LAYER** : 
     - This layer serves as the Central Hub of the Cloud Environment, where resources are regularly added by utilizing a variety of virtualization techniques.
     - It's main task is to divide the physical resources into virtual resources using virtualization technologies.
     - Virtualization technologies like Xen, KVM, Hyper-V, and VMware are used to create a pool of compute and storage resources. 
     - Enables dynamic resource assignment which optimizes the resource consumption and performance of the application. 

4) **DATACENTRE LAYER** :
     - Responsible for Managing Physical Resources such as servers, switches, routers, power supplies, and cooling systems. ( BASICALLY Hardware handling )
     - Physical servers are connect through high-speed devices such as routers and switches to the data centre for fast paced data transfer and computing. 



### CLOUD DEPLOYMENT MODELS 
1) Public Cloud
2) Private Cloud
3) Hybrid Cloud
4) Community Cloud
5) Multi-Cloud

- **PUBLIC CLOUD** :
     - Here, infrastructure and services are provided over the internet to the general public or industries.
     - Service provider owns the infrastructure, and users pay on a subscription or per-use basis. 
     - Advantages:
         - Minimal Investment
         - No Setup Cost
         - No Infrastructure Management
         - No Maintenance 
         - Dynamic Scalability 
     - Disadvantages:
         - Less Secure
         - Limited Customization

- **PRIVATE CLOUD** : 
     - Dedicated to a single organization
     - Provides full control over infrastructure, security, and resources.
     - Managed by an organization's own IT department with firewall protection.
     - AKA Internal Cloud
     - Advantages:
         - Better Control
         - Higher Security & Privacy 
         - Supports Legacy Systems 
         - High Degree of Customization 
     - Disadvantages:

         - Less Scalable 
         - Higher Cost 

- **HYBRID CLOUD** : 
     - It's like a mix of public and private clouds with a specialized software.
     - Helps organizations to store sensitive data in private clouds while using public clouds for cost efficiency.
     - Advantages:
         - Flexibility & Control 
         - Cost Efficiency 
         - Secure 
    - Disadvantages:

         - Complex to Manage 
         - Slow Data Transmission 

- **COMMUNITY CLOUD** : 
     - It's a shared cloud infrastructure for multiple organizations with common goals or industry requirements.
     - Generally Managed by either a third party or a group of organizations.
     - Advantages:
         - Cost-Effective 
         - Higher Security 
         - Shared Resources
         - Supports Collaboration & Data Sharing 
     - Disadvantages:
         - Limited Scalability 
         - Rigid Customization 

- **MULTI CLOUD** : 
     - Uses multiple public clouds.
     - Distributes workloads across different cloud providers thereby reducing downtime.
     - Advantages:
        - Best Features of Multiple Providers 
        - Reduced Latency 
        - High Availability
    - Disadvantages:
         - Complex System
         - Security Risks

TLDR : 
<div align="center">

| **Cloud Model**  | **Key Features** | **Advantages** | **Disadvantages** |
|-----------------|-----------------|---------------|----------------|
| **Public Cloud** | Open to public, provider-owned infrastructure | Low cost, no setup, no maintenance, high scalability | Less secure, limited customization |
| **Private Cloud** | Dedicated to one organization, full control | High security, supports legacy systems, customizable | High cost, limited scalability |
| **Hybrid Cloud** | Mix of public & private clouds | Flexible, cost-efficient, secure | Complex management, slower data transmission |
| **Community Cloud** | Shared by multiple organizations with common goals | Cost-effective, secure, promotes collaboration | Limited scalability, rigid customization |
| **Multi-Cloud** | Uses multiple public clouds | High availability, reduced latency | Complex, security concerns |

</div>


### COMPUTE BUILDING BLOCKS 
- **PROCESSORS** :
     - A CPU ( Processor ) executes a set of instructions to get a task done. 
     - A typical CPU instruction set consists of a fixed number of instructions like ADD, SHIFT BITS, MOVE DATA, and JUMP TO CODE LOCATION etc.
     - Assembly Language is a set of English Mnemonics that map to Machine Instruction code which is in-turn mapped to a binary instruction. 
     - Assembly programming language is the lowest level programming language for computers . 
     - A CPU needs a high frequency clock to operate, generating clock cycles.
     - Each instruction needs a single or multiple clock cycles to complete.
     - The speed at which the CPU operates is defined in $GHz$ (billions of clock ticks per second). 
     - Because of these high clock speeds CPUs are able to execute instructions very fast.
     - Each CPU is designed to handle data in chunks. 
     - These chunks are called words which have with a specific size.
     - The word size is reflected in many aspects of a CPU's structure and operation. 

- **RAM** :
     - Random Access Memory
     - Any piece of data stored in RAM can be accessed in the same amount of time, regardless of its physical location.
     - Transistor based technology. 
     - Implemented using Integrated Circuits.
     - SRAM (Static RAM)

         - Uses flip-flop circuits to store data.
         - Requires $6$ transistors per bit.
         - Faster access times compared to DRAM.
         - Commonly used in cache memory and video RAM.

     - DRAM (Dynamic RAM)

         - Uses one transistor and one capacitor per bit.
         - Stores data as a charge in a capacitor $(charged = 1, discharged = 0)$.
         - More memory-efficient than SRAM due to fewer required components.
         - Needs regular refreshing to retain data .
         - Special hardware circuits handle the refresh process automatically.

- **INTERFACE** : 
     - Interfaces are the point of connection between the computer and external peripherals. 
     - External Interfaces : 
         - $RS-232$
         - USB
         - Thunderbolt
         - They use the connectors located outside the computer.
     - Internal Interfaces : 
         - PCI 
         - PCIe
         - They're located on the system board of the computer. 
    - **$RS-232$** : 
         - Standardized serial communication interface used for connecting electric typewriters, modems, and electronic terminals. 
    - **USB** :
         - Offers higher speeds, lower power consumption, and plug-and-play functionality.
         - The USB interface can provide operating power to attached devices. 
    - **THUNDERBOLT** : 
         - AKA Light Peak
         - Appeared first on Apple laptops.
         - It's backward compatible
     - **PCI**: 

          - Peripheral Component Interconnect. 
          - It's a shared parallel bus architecture. 
          - Allows communication between System board and PCI adapters 
     - **PCIe** : 
          - PCI Express  
          - It's a faster alternative, uses point-to-point serial links instead of a shared bus, with links built from multiple lanes (x1, x2, x4, etc).
          - A hub on the system board routes PCIe connections, allowing multiple devices to communicate simultaneously. 


### COMPUTE VIRTUALIZATION 
- AKA Server virtualization AKA Software Defined Compute
- It introduces an abstraction layer between computer hardware and the OS that uses the hardware. 
- Virtualization allows multiple OS to run on a single physical machine. 
- Virtualization decouples and isolates virtual machines from the physical machine 
and from other virtual machines by means of a virtualization layer.
- A virtual machine is a logical representation of a physical computer in software.
- Virtualization allows for new virtual machines to be provisioned as needed,
without the need for an upfront hardware purchase.  
- This saves a lot of time and cost effective.
- consolidating many physical computers as virtual machines on less number but bigger physical machines, huge amounts of money can be saved on hardware, power, and cooling as fewer physical machines are needed and so the cost of maintenance and chances of hardware failure is reduced.


### CONTAINER VIRTUALIZATION 
- OS was designed to handle a variety of tasks at a time. 
- But with time , dependencies, versions and application requirements change and handling them becomes difficulty in the same system. 
- This problem could be solved via virtualization i.e running a whole dedicated OS for a service but that's a huge overhead to bear. 
- Container virtualization is a server virtualization method in which the kernel of an
operating system provides multiple isolated user-space instances independent of each Other. 
- Containers look and feel like a real server from the point of view of its owners and users, but they share the same operating system kernel. 
- This isolation enables the operating system to run multiple processes, where each process shares nothing but the kernel.

- Benefits :  

     - **Isolation** : application and their components can be encapsulated in containers, each operating independently and isolated from each other thereby resolving the dependency conflicts if any.
     - **Portability** : since containers typically contain all components the application needs to function, including libraries and patches therefore, containers can be run on any infrastructure that is capable of running containers using the same kernel version.
     - **Easy deployment** : containers allow developers to quickly deploy new software versions, as their containers can be moved from the development environment to the production environment unaltered.

### MAINFRAMES 
- They are high performance computer made for high-volume, I/O intensive computing. 
- Mainframes are highly reliable and can typically run for years without a downtime.
- Much backup components are built in for critical processing, enabling hardware upgrades and repairs while the mainframe is operating without downtime.
They are expensive
computers, mostly used for administrative processes, optimized for handling
high volumes of data.
- They are expensive computers, mostly used for administrative processes and are optimized for handling high volumes of data.

- **ARCHITECTURE** :

<div align="center">
<image src="mainframe architecture.jpg">
</div>

-  Made up of :
- Processing Units (PUs),
- Memory, I/O channels 
- Control units
- External devices
- **Processing Units** : 
     - One question : why not call CPU ? 
     - Cause mainframes have multiple Processing Units therefore there's nothing central . 
     - Compilation of all the PUs in a mainframe is called a Central Processor Complex (CPC).

     - CPC is placed in its own cage inside the mainframe consisting of $1-4$  book packages. Each book package consists of processors, memory, and I/O connections. 
     - A book package is something similar to motherboard which is made of : 
          - PU 
          - RAM 
          - IO connections
     - Mainframes use custom made processors which are specially designed for high performance and high reliability computations.
     - They are optimized for handling large scale transactions, parallel processing, and high reliability.
     - While firmware configuration, each PU is assigned a specific task for which they are optimized like database processing, encryption, I/O operations etc. 
- **Main Storage** : 

     - Each book package contains $4-10$ memory cards which are hot swappable i.e they can be removed/replaced without powering off the machine.
- **Channels , ESCONS , FICONS** :
     - A channel is a pathways that provides a data and control path between I/O devices and memory.
     -  Channels can connect to control units directly or via switches. 
     - Specific slots in the I/O cages are reserved for specific types of channels, which include the following:
          - **Open Systems Adapter (OSA)**
          - **Fibre Connection (FICON)** 
          - **Enterprise Systems Connection (ESCON)**
- **Control Units** :
     -  They contains logic to work with a particular type of I/O device, like a printer or a
     tape drive.
     - Some control units can have multiple channel connections providing multiple paths to the control unit and its devices, increasing performance and availability.
     - Control units can be connected to multiple mainframes thereby creating a shared IO system.

- **MAINFRAME VIRTUALIZATION** :
     - the designing of a mainframe is always done with the perspective of virtualization. 
     - A single mainframe can run a multiple virtual machines with each virtual machine acting a mainframe in it's own . 
     - Mainframes offer Logical Partitions ( LPARs) and they act as a separate mainframe where each LPAR run with it's own OS. 
     - Furthermore, we can also define the maximum number of processes a LPAR can run. 


### X $86$ Servers 

- It's a server architecture. 
- **ARCHITECTURE** :
- Consists of a CPU from a X $86$ family.
- The X $-86$ architecture is mainly defined by the X $-86$ chipset.
- The old X $-86$ chips used a north-bridge south-bridge architecture. 
     <div align="center">
     <image src="X86-architecture.jpg">
     </div>

     - FSB ( Front Side Bus ) connected CPU to the north-bridge for high speed data transfer. 
     - Furthermore the north-bridge connected RAM and PCIe bus. 
     - The south-bridge connected the slower components like BIOS,SATA adapters, USB ports, PCI bus.
     - North-bridge and south-bridge are connected by DMI (Direct Media Interface). 

- The new X $-86$ architecture, the north-bridge and south-bridge are replaced by PCH (Platform Controller Hub) architecture. 
     <div align="center">
     <image src="PCH-based-X-86-architecture.jpg">
     </div>
     
     - The functionality of the south-bridge is managed by the the PCH chip that directly connects to the CPU via the same old DMI. 
     - The north-bridge functions are now transferred to the CPU.

( Just know the diagrams and you'll be done with it)


### SUPER COMPUTERS 
- It's architecture was designed to maximise the calculation speed. 
- Used for tasks like weather forecasting calculations, oil reservoir simulations, the rendering of animation movies etc. 
- Graphics Processing Units (GPUs) are also used together with CPUs to accelerate specific calculations. 
- Where a CPU consists of a few cores that are mainly optimized for sequential serial processing, a GPU has mainly a parallel architecture consisting of many of smaller and way more efficient cores designed for handling multiple tasks simultaneously. 



### COMPUTE AVAILABILITY 
- Making Servers highly available can be achieved by the following ways : 
1) Hot Swappable Components
2) Parity and ECC memory 
3) Lock-stepping

------

1) **Hot Swappable Components**
- Hot swappable components are the components like memory, CPUs, interface
cards, and power supplies that can be installed, replaced, or even upgraded while the
server is in a running state.
- What's important here is that the virtualization and operating systems using the server hardware must be aware that components can be swapped while the system is on the run. 

2) **Parity and ECC memory** 
- Parity bits are used to detect memory errors by adding an extra bit to ensure an even or odd number of ones in a byte. 
- If a bit flips, the parity checker detects an error but cannot identify or fix the flipped bit.
- This identification and fixing of the flipped bit is done by ECC (**Error Correction Code**). 
- These ECC memory chips use Hamming Code or Triple Modular Redundancy (TMR) for detecting and correcting the flipped bit. 
- Hamming code can correct single bit errors occurring in data whereas TMR memory is able to repair two failing bits. 
- Multi-bit errors in the same memory location are extremely rare and don't pose
much of a threat to memory systems. 

3) **Lock-Stepping**
- It's is an error detection and correction technology for servers. 
- In this correction method, multiple systems perform the same calculations and compare results. 
- If the results match, the calculations are correct.
- If they differ, an error is detected. 
- With two systems, errors can be identified but not corrected, while using more systems allows for correction through a voting mechanism.
- This technique ensures high reliability but is costly and hence is mainly used in critical systems. 
- Lockstepping works by synchronizing systems per atomic transaction, comparing results at each step.


### COMPUTE PERFORMANCE
( Basically discussing techniques for boosting performance)
But before jumping into all that , one important thing : 
**MOORE'S LAW** : It states that the number of transistors on a chip doubles approximately every two years, leading to exponential growth in computing power. 

- INCREASING CPU POWER 
     - We can modify the following metrics for speeding up computations done via CPU : 
          - increasing the clock speed 
          - caching
          - prefetching
          - branch prediction
          - pipelines 
          - use of multiple cores
1) **INCREASING CLOCK SPEED** :
- CPU clock speed is measured in Hertz $(Hz)$ – clock ticks or cycles per second. 
- The CPU processes instructions stored in memory. These instructions need to be fetched, decoded, executed and the result must often be written back to memory. 
- Each step in the sequence is executed when an external clock signal is changed from $0$ to $1$ (the cock tick). The clock signal is supplied to the CPU by an external oscillator.
- Depending on the type of CPU instruction, one or more clock ticks are needed to
execute the instruction. 
- Thereby increasing the clock speed, more number of instructions can be executed in a given unit time. 
- The oscillator speed is used for other parts of the system board. This speed is known as the Front Side Bus (FSB) speed.

- A multiplier is a clock multiplier circuit that maintains the ratio of the oscillator speed to the clock speed. 
- A higher multiplier means higher clock speed for a CPU. 
- Note that the multiplier only affects the CPU and not the FSB. 
- Therefore we can say that increasing the oscillator frequency affects both the CPU and the FSB Speed but the multiplier only affects the CPU's speed. 

2) **CPU CACHING** : 
- We have SRAM and VRAM . 
- SRAM ( static ) is fast but expensive.
- DRAM ( dynamic ) is cheap but slow. ( Used in main memory )
- Solution ? 
- Hybrid solution : Put caches of VRAM on SRAM.
- The cache temporarily stores frequently used data from slower RAM to speed up access.
- This avoids the slow fetch process from main memory, improving CPU performance.
- Main memory RAM runs Slower than the Cache memory. 
- Most CPU contains $2$ levels of cache : 
- Level $1$ cache and Level $2$ cache. 
- Level $1$ cache is faster and smaller. 
- If we want to run the CPU with $0$ latency, we keep Level $1$ cache close to the CPU core as compared to Level $2$ cache. 
- The Level $1$ cache gets it's data from Level $2$ cache which in-turn gets it's data form RAM. 
- Level $1$ Cache is split into $2$ parts Read and Write whereas Level $2$ is both Read and Write in the same chip.
- Multi-core CPU have a $3^{rd}$ type of Cache which is common to all the cores. 


3) **PIPELINES**
-  Pipeline allows multiple instructions to be processed simultaneously at different stages. 
- While one instruction is being executed, the next instruction can be fetched, and another can be decoded, creating an overlap and increasing processing speed.
- The width of the pipeline is the same as the number of instruction stages. 
- Ideally this leads to one instruction being executed per available clock tick. 
- But because some instructions need the output from the previous instruction as input,
therefore, these instructions are held/kept waiting until the previous instruction has completed its current stage. 

4) **PREFETCHING AND BRANCH PREDICTION**
- Whenever the CPU needs data for performing computations, it first searched it's level $1$ & $2$ caches for finding it.
- In case it's not found then it asks RAM to fetch the data for him. 
- This is slow . 
- Here Prefetching comes into picture :  when the CPU fetches an instruction from RAM, the system also loads the next expected instructions into the cache. 
- This helps ensure the CPU gets data quickly without waiting for RAM access.
- But at times there are JUMP instruction in the flow thereby missing out data from the cache. 
- To reduce this , the CPU predicts when it's going to get a JUMP instruction and preloads that instruction into the cache before hand. 

5) **SUPERSCALAR CPU**
- These CPUs can process multiple instructions per clock . 
- This is achieved by sending multiple instructions to redundant functional units within a single CPU core. 
- These functional units include components like the Arithmetic Logic Unit (ALU), bit shifters, and multipliers, which execute instructions in parallel through multiple data paths.
- The CPU must analyse data dependencies between instructions. 
- A dispatcher circuit reads instructions from memory, determines which ones can run simultaneously, and assigns them to different execution units. 
- This parallel execution greatly improves performance but also makes the CPU’s internal logic significantly more complex.

6) **MULTICORE CPU**
- High clock speed results into the heating up of the CPU thereby limiting the compute speed.
- A multi-core processor is a CPU with multiple separate cores, each with their own cache. 
- It is the equivalent of getting multiple processors in one package. 
- If these cores were placed on a single chip without any modification, the chip would consume twice as much power and generate a large amount of heat. 
- To solve this, the cores in a multi-core CPU run at a lower frequency to
reduce power consumption.
- This leads to reduced load on a single Core and thereby allowing parallel computation to be performed at a CPU level. 

7) **HYPER THREADING**
- It allows a single physical CPU core to function as two logical processors, enabling it to run two threads simultaneously. 
- This improves efficiency by keeping the processor pipelines busier, though it does not double performance like adding real cores. 
- Hyper-threading requires both CPU and BIOS support to function.

### COMPUTE SECURITY 
1) **PHYSICAL SECURITY** :
- Servers should have USB ports disabled in BIOS to prevent unauthorized access. 
- BIOS must be password Protected.
2) **VIRTUALIZATION SECURITY** : 
- Use of Virtualization introduces security risks in it's own ways.
- Firewalls and Intrusion Detection Systems (IDSs) in the hypervisor
should be deployed. ( hypervisor is a software that allows multiple Virtual machines to run on a single device )
3) **DMZ SECURITY** : 
-  Use separate physical machines for servers inside the De-Militarized-Zones to ensures better isolation and security from external threats, even when running virtual machines.
4) **SYSTEM MANAGEMENT CONSOLE** : 
- This console manages all the virtual machines running. 
- This console should have Strict access control, separation of duties, and logging user activities to provide a secured physical machine are essential for protection.

### OPERATING SYSTEMS

### POPULAR OS 
- zOS
- Linux
- Windows
- IBM i(OS/$400$)
- Open VMs
- UNIX
- BSD 
- OpenBSD


### OS AVAILABILITY 
- To make OS available all times, Failover Clustering is used. 
### FAILOVER CLUSTERING
- A  failover cluster is a group of independent servers (nodes) that work together to ensure high availability of applications.
- Each server runs an identical operating system and is connected to other nodes via a network.
- The cluster is managed by cluster software, which detects failures and automatically shifts workloads from a failed node to another available node.

- **How does this work ?**

- Failover Clustering  groups related application components into a resource pool (also called an **application package**). This package contains all necessary scripts and configurations required to **start, stop, monitor, and migrate** an application between cluster nodes.

- Each resource pool consists of:

     - **Application Name & Identifier** – Unique identifier for the application.
     - **Start Script** – Commands to start the application.
     - **Stop Script** – Commands to stop the application.
     - **Monitor Script** – Continuously checks application status and initiates a restart or failover if it stops responding.
     - **Virtual IP Address** – Ensures applications remain accessible after failover.
     - **Storage Mount Points** – Defines which disks must be available for the application.

- If a node fails, the cluster software automatically moves the resource pool to another node and remounts storage, ensuring continuous availability.

- Failover cluster relies on a redundant network of physical Ethernet connections for communication between nodes. This network is mainly used for:

     - Heartbeats – Small packets sent between nodes to check their availability.
     - Membership Updates – Nodes inform each other of their operational status.
     - State Change Notifications – When a failure occurs, nodes receive notifications to take appropriate action.

- If a node stops producing heartbeats, the clustering software assumes the node to have failed and triggers a failover process .

- Most of the failover clusters use shared memory. This means that : 
     - Every active application has exclusive access to a disk. ( though only one node is allowed to mount and use that particular disk.)
     - When an application fails over to another node, the same data remains accessible.
     - The cluster software automatically remounts the correct storage to the new active node.

- Thought most use shared memory , but essentially there are $2$ types of Cluster Storage : 
     - **Shared-Nothing Clustering**:
          - Only one node accesses a given disk at any time.
          - After a failover, the disk is remounted on the new active node.
          - This approach prevents data conflicts.
     - **Distributed Lock Management (DLM) Clustering**
          - Multiple nodes can simultaneously access the same storage.
          - A lock management system ensures data integrity.
          - Used in advanced clustering setups requiring concurrent access.

- Every active application in a failover cluster has a standby counterpart on a passive node. 
- The passive node remains idle until needed. If an active node crashes due to any reason, the passive node takes over immediately.
- Basically it's a fallback node which remains inactive and becomes active only when the main node fails .

- When applications restart on another node, they go through standard crash recovery:
     - The file system checks and repairs corrupted data before re-mounting on the memory.
     - The application itself performs it's necessary recovery procedures implemented internally.

- **TYPES OF CLUSTERING ARCHITECTURE** : 

     1)  **$N+1$ Clustering** : 
          - N nodes actively run applications.
          - $1$ spare node remains idle until a failure occurs.
     2) **$N+2$ or $N+3$ Clustering**:

          - Multiple spare nodes for increased redundancy.
          - Example: $4$ active nodes and $2$ spares ($4+2$ setup).
     3) **N to N Clustering**:
          - No dedicated spare nodes.
          - Every node keeps some spare capacity to handle failovers.
          - More efficient than N+1 because all resources are used.

- **SPLIT BRAIN PROBLEM** :
- Suppose we have even number of clusters get split into $2$ equal halves and loose connection between them. 
- So each half in itself is working but isn't aware of the other half's status. 
- Due to this $2$ scenarios may occur : 
     1) The first half assumes the other half is failed. 
          - A failover condition is triggered and one half tried to take up the workload of the other half (which in reality is still running)
          - This is fatal as this may lead to data-overwriting and data-corruption. 
     2) Both the halves assume that they lost the cluster. 
          - In this scenario, all the nodes shut-down
          - This causes unnecessary downtime.
- To Solve this problem we use the concept of Quorum Disk. 
- A quorum disk is a shared disk that acts as a virtual third node in the cluster.
- The quorum disk belongs to only one node at a time.
- If a node fails or loses connection, it releases the quorum disk.
- The surviving node gets control of the quorum disk and wins the majority vote.
### OS SECURITY 
- The following measures can be taken for ensuring the safety and security of OS : 
1) **PATCHING** : 
- Operating system vendors provide patches to fix bugs, close security holes, or improve functionality.
- Patches come in three types: 
     - **regular patches** for low-priority fixes, 
     - **hot-fixes** for urgent security flaws, and service packs, which bundle multiple updates. 
- While applying patches promptly is recommended, they should be tested before deployment to avoid potential issues that may affect the functionality of the OS.

2) **HARDENING** : 
- It's a process in which an operating system disables all unnecessary services, removes unused accounts, and apply security patches. 
- A standardized configuration template ensures that all systems maintain consistent security levels throughout the infrastructure.

3) **VIRUS SCANNING** : 
-Installing virus scanners on vulnerable operating systems that helps them protect against malware and other sorts of threats. 
- To minimize performance impact while scanning, virus scanners are configured in such a way that they focus on high-risk files and directories based on some risk assessment parameters.

4) **HOST BASED FIREWALLS** : 
- Host-based firewalls are built into almost all operating systems providing an extra security layer by blocking unwanted network traffic. 
- They use rule sets to allow or deny communication based on source/destination IPs, ports, and processes. 
- They block the suspicious and malicious network connection requests and packets. 

5) **LIMITING USER ACCOUNTS**

- Default user accounts should be removed or should have their passwords changed to prevent unauthorized access. 
- Super user accounts (root, administrator etc) should only be used for assigning permissions, with secure passwords stored safely.
- Encrypted passwords should never be disclosed to avoid brute force attacks.

### IMPROVING PERFORMANCE OF OS 
1) **INCREASING MEMORY**: 
- OS needs memory for a smooth functioning. 
- When an application needs more memory, it can simply do it in 2 ways :
     1) By sending less used memory pages to disks (Paging)
     2) by moving an entire application's allocated memory to disk (swapping)
- Unused memory is utilized for disk caching and improving performance.
- More memory allows better disk caching thereby reducing disk read times.

2) **DECREASING KERNEL SIZE** : 
- Some OS allow disabling unused kernel features to reduce kernel size.
- A smaller kernel improves efficiency and security.
- Disabling unused kernel features simplifies it thereby reducing the chances of crashing. 
- Since kernel is always to be present in the memory, therefore a small kernel will consume less memory and therefore increases the performance. 
- The Boot-time also reduces upon downsizing the kernel. 
- To create a smaller kernel, the kernel must be recompiled or re-linked.