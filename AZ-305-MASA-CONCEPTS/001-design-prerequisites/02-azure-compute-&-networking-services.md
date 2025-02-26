# Azure compute and networking services 

- Azure Virtual Machines 
    - Infrastructure as a service (IaaS) in the form of a virtualized server and can be used in many ways
    - VM availability sets (To help you build a more resilient, highly available environment. Availability sets are designed to ensure that VMs stagger updates and have varied power and network connectivity, preventing you from losing all your VMs with a single network or power failure.)
        - Update domain
        - Fault domain
        
- Describe Azure virtual desktop
    -  Azure Virtual Desktop is a desktop and application virtualization service that runs on the cloud. It enables you to use a cloud-hosted version of Windows from any location. 
    - Enhace security using Entra ID
    - Multi-session windows 10/11 (Azure Virtual Desktop lets you use Windows 10 or Windows 11 Enterprise multi-session, the only Windows client-based operating system that enables multiple concurrent users on a single VM.)

- Azure Containers
    - Containers are a virtualization environment
    - VMs (cirtualize hardware) vs Container (virtualize OS)
    - Azure Container Instances (A platform as a service (PaaS) offering. Azure Container Instances allow you to upload your containers and then the service runs the containers for you)
    
    - Azure Container Apps (have extra benefits such as the ability to incorporate load balancing and scaling. These other functions allow you to be more elastic in your design.
    )
    - Azure kuberenetes service (Container Orchestration)
    - Usage (Containers are often used to create solutions by using a microservice architecture. This architecture is where you break solutions into smaller, independent pieces.)

- Azure Functions
    - Azure Functions is an event-driven, serverless compute option that doesn’t require maintaining virtual machines or containers

-  Application hosting options
    - Virtual machine (VM) give you maximum control of the hosting environment and allow you to configure it exactly how you want.
    - Containers, with the ability to isolate and individually manage different aspects of the hosting solution, can also be a robust and compelling option.
    - App Service
        - App service styles like:
            - Web apps (App Service includes full support for hosting web apps by using ASP.NET, ASP.NET Core, Java, Ruby, Node.js, PHP, or Python. You can choose either Windows or Linux as the host operating system.)
            - API apps (Much like hosting a website, you can build REST-based web APIs by using your choice of language and framework. You get full Swagger support and the ability to package and publish your API in Azure Marketplace. The produced apps can be consumed from any HTTP- or HTTPS-based client.)
            - WebJobs (for cronjonbs) You can use the WebJobs feature to run a program (.exe, Java, PHP, Python, or Node.js) or script (.cmd, .bat, PowerShell, or Bash) in the same context as a web app, API app, or mobile app. They can be scheduled or run by a trigger. WebJobs are often used to run background tasks as part of your application logic.
            - Mobile apps (Use the Mobile Apps feature of App Service to quickly build a back end for iOS and Android apps)
        - Handles (most of the infrastructure decisions you deal with in hosting web-accessible apps)        
            - Deployment and management are integrated into the platform.
            - Endpoints can be secured.
            - Sites can be scaled quickly to handle high traffic loads.
            - The built-in load balancing and traffic manager provide high availability.

- Azure Virtual Networking
    - Isolation and segmentation (Isolated VNets, IP address spacing into subnets, name resolution service, confiure VNet to internal/external DNS)
    - Internet communications (Public IP to resource)
    - Communicate between Azure resources
        1. Virtual Networks
        2. Service Endpoints
    - Communicate with on-premises resources
        1. Point-to-site virtual private network connections (the client computer initiates an encrypted VPN connection to connect to the Azure virtual network)
        2. Site-to-site virtual private networks (link your on-premises VPN device or gateway to the Azure VPN gateway in a virtual network)
        3. Azure ExpressRoute (dedicated private connectivity to Azure)
    - Route network traffic (Azure routes traffic between subnets on any connected virtual networks, on-premises networks, and the internet)
        1. Route Tables (allow you to define rules about how traffic should be directed. You can create custom route tables that control how packets are routed between subnets.)
        2. Border Gateway Protocol (works with Azure VPN gateways, Azure Route Server, or Azure ExpressRoute to propagate on-premises BGP routes to Azure virtual networks.)
    - Filter network traffic (filter traffic between subnets)
        1. Network Security Groups (contain multiple inbound and outbound security rules.)
        2. Network Virtual Environments (are specialized VMs that can be compared to a hardened network appliance. A network virtual appliance carries out a particular network function, such as running a firewall or performing wide area network (WAN) optimization.)
    - Connect virtual networks (can link virtual networks together by using virtual network peering. Peering allows two virtual networks to connect directly to each other.)

- Azure virtual private networks
    - A virtual private network (VPN) uses an encrypted tunnel within another network. VPNs are typically deployed to connect two or more trusted private networks to one another over an untrusted network (typically the public internet)
    - VPN gateways
        - Connect on-premises datacenters to virtual networks through a site-to-site connection.
        - Connect individual devices to virtual networks through a point-to-site connection.
        - Connect virtual networks to other virtual networks through a network-to-network connection.
        - Type of VPN (encryption-based) ( regardless of the VPN type, the method of authentication employed is a preshared key.s)
            1. Policy-based (specify statically the IP address of packets). This type of device evaluates every data packet against those sets of IP addresses to choose the tunnel where that packet is going to be sent through.
            2. Route-based ( IPSec tunnels are modeled as a network interface or virtual tunnel interface. IP routing (either static routes or dynamic routing protocols) decides which one of these tunnel interfaces to use when sending each packet.)
            3. Route-based VPN gateway
                - Connections between virtual networks
                - Point-to-site connections
                - Multisite connections
                - Coexistence with an Azure ExpressRoute gateway


- High-availability scenarios
    - Active/standby configuration
    - Active/active
    - ExpressRoute failover
    - zone-redundant gateway


- Azure ExpressRoute
    - Azure ExpressRoute lets you extend your on-premises networks into the Microsoft cloud over a private connection, with the help of a connectivity provider. This connection is called an ExpressRoute Circuit.
    - Features & Benefits
        - Connectivity to Microsoft cloud services across all regions in the geopolitical region.
        - Global connectivity to Microsoft services across all regions with the ExpressRoute Global Reach.
        - Dynamic routing between your network and Microsoft via Border Gateway Protocol (BGP).
        - Built-in redundancy in every peering location for higher reliability.
    - Connectivity
        - Microsoft Office 365
        - Microsoft Dynamics 365
        - Azure compute services, such as Azure Virtual Machines
        - Azure cloud services, such as Azure Cosmos DB and Azure Storage
    - Global connectivity
    - Dynamic routing
    - Built-in redundancy
    - ExpressRoute connectivity models
        - ExpressRoute supports four models that you can use to connect your on-premises network to the Microsoft cloud:
            - CloudExchange colocation (datacenter, office, or other facility being physically colocated at a cloud exchange, such as an ISP)
            - Point-to-point Ethernet connection (a point-to-point connection to connect your facility to the Microsoft cloud.)
            - Any-to-any connection (any-to-any connectivity, you can integrate your wide area network (WAN) with Azure by providing connections to your offices and datacenters.)
            - Directly from ExpressRoute sites (You can connect directly into the Microsoft's global network at a peering location strategically distributed across the world. ExpressRoute Direct provides dual 100 Gbps or 10-Gbps connectivity, which supports Active/Active connectivity at scale.)

- Azure DNS
    - Azure DNS is a hosting service for DNS domains that provides name resolution by using Microsoft Azure infrastructure
    - Benefits
        - Reliability and performance (Azure DNS are hosted on Azure's global network of DNS name servers, providing resiliency and high availability.)
        - Security (Azure DNS is based on Azure Resource Manager)
        - Ease of Use (Azure DNS can manage DNS records for your Azure services and provide DNS)
        - Customizable virtual networks
        - Alias records
    - Reliability and performance
    - Customizable virtual networks with private domains (Azure DNS also supports private DNS domains allowing you to use your own custom domain names in your private virtual networks)
    - Azure DNS also supports alias record sets. You can use an alias record set to refer to an Azure resource, such as an Azure public IP address, an Azure Traffic Manager profile, or an Azure Content Delivery Network (CDN) endpoint




