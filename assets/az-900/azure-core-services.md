# Azure Core Services
Zaczynamy!

![Microsoft AZ-900 Azure Fundamentals Exam - Digital Thought Disruption](https://digitalthoughtdisruption.com/wp-content/uploads/2020/01/image.png?w=389) 



## 1 Co jest w datacenter?

![Microsoft Data Centers | Motion design animation, Animation design, Motion  design](https://i.pinimg.com/originals/95/fa/54/95fa543775583cad8944f0fafa9f7d73.gif)

Podstawą będzie zrozumienie jak są budowane datacenters. Tutaj Mark Russinovich - CTO od Azura wyjaśnia. 

Wideo do obejrzenia[![Inside Azure datacenter architecture with Mark Russinovich](https://medius.studios.ms/video/asset/THUMBNAIL/B19-BRK3060?v=fd44debf50eb7819526783423d1eba3bef7235c1d6c04fc7e716cd984e4d2186)](https://www.youtube.com/watch?v=69PrhWQorEM) 


## 2 High level tour of Azure services 

- Azure Periodic Table https://azureperiodic.data3.com/ 

  ![The Azure Periodic Table - Data#3](https://www.data3.com/wp-content/uploads/2019/12/azure-blog-4-e1588117736708.png)

- Mając zbudowaną high level mapę serwisów, możemy zejść poziom niżej.


## 3 Azure Regions and Availability Zones
> The physical infrastructure for Azure starts with datacenters. Conceptually, the datacenters are the same 
as large corporate datacenters. They’re facilities with resources arranged in racks, with dedicated power, 
cooling, and networking infrastructure.
As a global cloud provider, Azure has datacenters around the world. However, these individual datacenters aren’t directly accessible. Datacenters are grouped into Azure Regions or Azure Availability Zones 
that are designed to help you achieve resiliency and reliability for your business-critical workloads.

![Building solutions for high availability using Availability Zones - High  Availability | Microsoft Docs](https://docs.microsoft.com/en-us/azure/architecture/high-availability/images/high-availability-001.png)

> A region is a geographical area on the planet that contains at least one, but potentially multiple datacenters that are nearby and networked together with a low-latency network. Azure intelligently assigns 
and controls the resources within each region to ensure workloads are appropriately balanced.
When you deploy a resource in Azure, you'll often need to choose the region where you want your 
resource deployed.
Note: Some services or virtual machine (VM) features are only available in certain regions, such as 
specific VM sizes or storage types. There are also some global Azure services that don't require you to 
select a particular region, such as Azure Active Directory, Azure Traffic Manager, and Azure DNS.

![Azure Launches Availability Zones in GA, Catching Up to Rivals | Data  Center Knowledge](https://www.datacenterknowledge.com/sites/datacenterknowledge.com/files/azure-availability-zones_0.jpg)

> Availability zones are physically separate datacenters within an Azure region. Each availability zone is 
made up of one or more datacenters equipped with independent power, cooling, and networking. An 
availability zone is set up to be an isolation boundary. If one zone goes down, the other continues 
working. Availability zones are connected through high-speed, private fiber-optic networks.

> Region pair - Most Azure regions are paired with another region within the same geography (such as US, Europe, or 
Asia) at least 300 miles away. This approach allows for the replication of resources across a geography 
that helps reduce the likelihood of interruptions because of events such as natural disasters, civil unrest, 
power outages, or physical network outages that affect an entire region. For example, if a region in a pair was affected by a natural disaster, services would automatically fail over to the other region in its region 
pair.

> Additional advantages of region pairs:
>  If an extensive Azure outage occurs, one region out of every pair is prioritized to make sure at least 
one is restored as quickly as possible for applications hosted in that region pair. 
> Planned Azure updates are rolled out to paired regions one region at a time to minimize downtime 
and risk of application outage.
> Data continues to reside within the same geography as its pair (except for Brazil South) for tax- and 
law-enforcement jurisdiction purposes.

- Wideo do obejrzenia

  [![](http://img.youtube.com/vi/C-nNw1mGwzE/0.jpg)](http://www.youtube.com/watch?v=C-nNw1mGwzE "")

- Sprawdźcie do którego datacenter macie najbliżej - http://azurespeedtest.azurewebsites.net/ - i o czym mówi "latency"

- koniecznie do przerobienia - https://docs.microsoft.com/en-us/learn/modules/explore-azure-infrastructure/ - zrozumienie rozłożenia datacenter, regionów, availability zones, parowania regionów i SLA jest kluczowe w pracy z Azure i będzie dużo pytań o to na AZ-900. 

## extra - Sovereign Regions
> In addition to regular regions, Azure also has sovereign regions. Sovereign regions are instances of Azure 
that are isolated from the main instance of Azure. You may need to use a sovereign region for compliance or legal purposes

Azure sovereign regions include: 
> US DoD Central, US Gov Virginia, US Gov Iowa and more: These regions are physical and logical 
network-isolated instances of Azure for U.S. government agencies and partners. These datacenters are 
operated by screened U.S. personnel and include additional compliance certifications

> China East, China North, and more: These regions are available through a unique partnership between 
Microsoft and 21Vianet, whereby Microsoft doesn't directly maintain the datacenters.

## 4 Azure Portal Tour 

- do przerobienia https://docs.microsoft.com/en-us/learn/modules/tour-azure-portal/

 ![An animated gif of the Azure portal. | Azure, Microsoft, Hosting services](https://i.pinimg.com/originals/70/da/dc/70dadc873c16a014ac7f0a824cdf7831.gif)



## 5 Azure Resource Groups and Resource Manager

![Create workspaces in the portal - Azure Machine Learning | Microsoft Docs](https://docs.microsoft.com/en-us/azure/machine-learning/media/how-to-manage-workspace/create-workspace.gif)



Zasoby grupujemy w Resource Groups. Zasoby tworzą architektury. Możemy eksportować definicję zasobu w postaci definicji JSON, tak by później przy zastosowaniu praktych DevOps automatyzować stawianie zasobów.

> Management group, subscriptions, and resource group 
hierarchy - You can build a flexible structure of management groups and subscriptions to organize your resources 
into a hierarchy for unified policy and access management. The following diagram shows an example of 
creating a hierarchy for governance by using management groups

Spójrzcie jak na Azure wygląda hierarchia głównych bytów: 
![rgs](![rgs](https://raw.githubusercontent.com/ekote/Azure-and-AI/main/assets/imgs/1.png))
 

Wideo do obejrzenia:[![](http://img.youtube.com/vi/gIhf-S7BCdo/0.jpg)](http://www.youtube.com/watch?v=gIhf-S7BCdo "")

- więcej o automatyzacji https://youtu.be/Ge_Sp-1lWZ4



## 6 Azure Compute Services: VM, VM Scale set, App Service, Functions, Container Instance, Kubernetes Service

Mówi się, że podstawową jednostką na chmurze jest wirtualna maszyna - Virtual Machine. Na Azure jest sporo różnych możliwości uruchamiania aplikacji - czasem będzie potrzebna VMka, ale gdy mamy kontener dockerowy, to może Azure Container Instances albo Azure Functions będzie lepszym wyborem. 

![Azure Content Spotlight - Virtual Machine Serial Console (Preview) -  Microsoft Tech Community](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/74074i8F8354A1CD037772)

Wideo do obejrzenia:
[![](http://img.youtube.com/vi/inaXkN2UrFE/0.jpg)](http://www.youtube.com/watch?v=inaXkN2UrFE "")

- do przerobienia materiał na microsoft learn https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-compute/





## 7 Azure Networking Services: Virtual Network (VNet), Load Balancer, VPN Gateway, Application Gateway, Content Delivery Network (CDN)

Wideo do obejrzenia:[![](http://img.youtube.com/vi/5NMcM4zJPM4/0.jpg)](http://www.youtube.com/watch?v=5NMcM4zJPM4 "")


- do przerobienia materiał na microsoft learn https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-networking/


#### Isolation and segmentation
Azure virtual network allows you to create multiple isolated virtual networks. When you set up a virtual network, you define a private IP address space by using either public or private IP address ranges. The IP range only exists within the virtual network and isn't internet routable. You can divide that IP address  space into subnets and allocate part of the defined address space to each named subnet.

For name resolution, you can use the name resolution service that's built into Azure. You also can configure the virtual network to use either an internal or an external DNS server.

#### Internet communications
You can enable incoming connections from the internet by assigning a public IP address to an Azure resource, or putting the resource behind a public load balancer.

#### Communicate between Azure resources
You'll want to enable Azure resources to communicate securely with each other. You can do that in one of two ways:
- Virtual networks can connect not only VMs but other Azure resources, such as the App Service Environment for Power Apps, Azure Kubernetes Service, and Azure virtual machine scale sets.
- Service endpoints can connect to other Azure resource types, such as Azure SQL databases and storage accounts. This approach enables you to link multiple Azure resources to virtual networks to improve security and provide optimal routing between resources.

#### Communicate with on-premises resources
Azure virtual networks enable you to link resources together in your on-premises environment and within your Azure subscription. In effect, you can create a network that spans both your local and cloud environments. There are three mechanisms for you to achieve this connectivity.
- Point-to-site virtual private network connections are from a computer outside your organization back into your corporate network. In this case, the client computer initiates an encrypted VPN connection to connect to the Azure virtual network.
- Site-to-site virtual private networks link your on-premises VPN device or gateway to the Azure VPN gateway in a virtual network. In effect, the devices in Azure can appear as being on the local network. The connection is encrypted and works over the internet.
- Azure ExpressRoute provides a dedicated private connectivity to Azure that doesn't travel over the internet. ExpressRoute is useful for environments where you need greater bandwidth and even higher levels of security

#### Route network traffic
By default, Azure routes traffic between subnets on any connected virtual networks, on-premises networks, and the internet. You also can control routing and override those settings, as follows:
- Route tables allow you to define rules about how traffic should be directed. You can create custom route tables that control how packets are routed between subnets
- Border Gateway Protocol (BGP) works with Azure VPN gateways, Azure Route Server, or Azure ExpressRoute to propagate on-premises BGP routes to Azure virtual networks


#### Filter network traffic
Azure virtual networks enable you to filter traffic between subnets by using the following approaches:
- Network security groups are Azure resources that can contain multiple inbound and outbound security rules. You can define these rules to allow or block traffic, based on factors such as source and destination IP address, port, and protocol.
- Network virtual appliances are specialized VMs that can be compared to a hardened network appliance. A network virtual appliance carries out a particular network function, such as running a firewall or performing wide area network (WAN) optimization.



#### connect virtual networks
You can link virtual networks together by using virtual network peering. Peering allows two virtual networks to connect directly to each other. Network traffic between peered networks is private, and travels on the Microsoft backbone network, never entering the public internet. Peering enables resources in each virtual network to communicate with each other. These virtual networks can be in separate regions, which allows you to create a global interconnected network through Azure. User-defined routes (UDR) allow you to control the routing tables between subnets within a virtual 
network or between virtual networks. This allows for greater control over network traffic flow.


## 8 Azure Storage Services: azure storage account, disc storage

Jeśli VMka jest podstawową "jednostką" computingu na Azure, to jaki serwis będzie podstawową usługą do przetrzymywania danych? 




![Azure Storage Services – Storage account – 4sysops](https://4sysops.com/wp-content/uploads/2016/04/Storage-account-architecture.png)



![Managing and implementing Azure storage – DB Cloud TECH](https://mostafaelmasry.files.wordpress.com/2020/03/azure-storage.png?w=712)

Kluczowe nagranie z perspektywy tworzenia jakichkolwiek aplikacji na Azure. Wideo do obejrzenia:[![](http://img.youtube.com/vi/_Qlkvd4ZQuo/0.jpg)](http://www.youtube.com/watch?v=_Qlkvd4ZQuo "")



Wideo do obejrzenia:[![](http://img.youtube.com/vi/UzTtastcBsk/0.jpg)](http://www.youtube.com/watch?v=UzTtastcBsk "")



![What's new in Azure Data Lake Storage Gen2](https://www.mssqltips.com/tipimages2/5986_whats-new-azure-data-lake-storage-generation-2.010.png)

Wideo do obejrzenia:[![](http://img.youtube.com/vi/2uSkjBEwwq0/0.jpg)](http://www.youtube.com/watch?v=2uSkjBEwwq0 "")



- do przerobienia 25minutowy moduł: https://docs.microsoft.com/en-us/learn/modules/intro-to-data-in-azure/



## 9 Azure Database Services: cosmos db, sql databases, Azure database for MySQL, Azure Database for PostgreSQL

Pliki możemy trzymać na Blobie, ale czego użyć, gdy potrzebna jest baza relacyjna lub dokumentowa?

Wideo do obejrzenia:[![](http://img.youtube.com/vi/RqD4nMyBazU/0.jpg)](http://www.youtube.com/watch?v=RqD4nMyBazU "")

- do przeczytania dokumentacja pomagająca zrozumieć kiedy jaki serwis użyć do przetrzymywania danych https://docs.microsoft.com/en-us/learn/modules/intro-to-data-in-azure/3-how-azure-storage-meets-your-business-storage-needs

![SQL Server 2017 e Azure SQL Managed Instance - Dirceu Resende](https://www.dirceuresende.com/wp-content/uploads/2017/04/azuremanagedinstanec.png)



## 10 Azure IoT Services

![Piramal Glass adopts Microsoft's Azure IoT to boost operational efficiency](https://assets.techcircle.in/uploads/article-image/2018/11/images/17151-16052-iot-1.gif)

![Processar dados de veículos em tempo real com a IoT - Azure Architecture  Center | Microsoft Docs](https://docs.microsoft.com/azure/architecture/example-scenario/data/media/architecture-realtime-analytics-vehicle-data1.png)

Wideo do obejrzenia:[![](http://img.youtube.com/vi/RHkqFxJWhr8/0.jpg)](http://www.youtube.com/watch?v=RHkqFxJWhr8 "")



## 11 Azure Big Data and Analytics

Wideo do obejrzenia:[![](http://img.youtube.com/vi/JUQXx0R0RfE/0.jpg)](http://www.youtube.com/watch?v=JUQXx0R0RfE "")





Azure Synapse to przyszłość, będziemy o nim rozmawiać. Na teraz zapoznajcie się bliżej z super użytecznym serwisem - Azure Databricks. 

Tutaj rysunek pokazujący co w nim jest możliwe:

![What is Azure Databricks? | James Serra's Blog](https://i2.wp.com/www.jamesserra.com/wp-content/uploads/2017/11/DataBricks1.png?resize=1947%2C1075&ssl=1)



Dlaczego Azure Synapse to przyszłość? 

![Simplify Data Analytics with Azure Synapse - Adatis](https://adatis.co.uk/wp-content/uploads/Synapse-Simplify-v3.gif)



## 12 Azure AI and ML 

![Installing Azure ML Estimator Dependencies from Remote GitHub Branches | by  Aaron (Ari) Bornstein | Microsoft Azure | Medium](https://miro.medium.com/max/3032/1*mrMYpVE62e5_a-Uy1I389g.png)

To wstęp do tematów, które będą poruszane po części przygotowawczej do AZ-900, czyli do AI i ML-a. Koniecznie należy zrozumieć co robi Azure Machine Learning i jak z niego korzystać. Wideo do obejrzenia:[![](http://img.youtube.com/vi/8aMzR8iaB9s/0.jpg)](http://www.youtube.com/watch?v=8aMzR8iaB9s "")






## 13 Azure Serverless Computing

Jeśli chcemy uruchomić funkcję albo zbudować flow funkcji to nie musimy iść w toporne narzędzia uruchamiane w kontenerach lub na VMkach. Od tego jest serverless computing i kilka usług jakie daje Azure. Szczególnie polecam zapoznać się z Azure Functions i Azure Logic Apps. Wideo do obejrzenia:[![](http://img.youtube.com/vi/ansa4M7iTmg/0.jpg)](http://www.youtube.com/watch?v=ansa4M7iTmg "")



Przykłady architektur:

![Serverless Microservices reference architecture - Code Samples | Microsoft  Docs](https://docs.microsoft.com/en-us/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)



![Implementing a Serverless Architecture | David Chou](https://dachou.github.io/assets/20181107-architecture-application.png)



## 14 Azure DevOps 


Jeśli korzystaliście z Jenkins, Teamcity, Travis CI czy innego narzędzia pozwalającego na budowanie i deployment aplikacji na dane środowisko, to użycie Azure DevOps będzie dla Was banalne. W tej części skupiamy się właśnie na serwisie Azure DevOps i jego możliwościach, które z jednej strony pozwolą na  przetrzymywanie (repozytorium) kodu, zarządzanie pracą zespołu i ticketami (JIRA), a z drugiej na budowanie pipelines do testowania i releases aplikacji.  

Wideo do obejrzenia:

[![](http://img.youtube.com/vi/8M4DN9hjAeY/0.jpg)](http://www.youtube.com/watch?v=8M4DN9hjAeY "")



![Azure DevOps - manage your application life cycle in cloud](https://subhankarsarkar.com/wp-content/uploads/2018/09/Azure-DevOps-SubhankarSarkar.png)



## 15 Mapy myśli - mindmap  

- Interaktywna - https://www.mindmeister.com/1644491891/azure-az-900-fundamentals?fullscreen=1 
- bardzo dobrze rozbudowane koncepty i usługi w Azure https://www.shanebart.com/wp-content/uploads/2019/09/AZ-900.pdf
- sporo trudniejsza bo wiele pojęć może być dla niektórych nieznanych - https://techcommunity.microsoft.com/t5/image/serverpage/image-id/162827i36D7ACCB57356775?v=1.0 - mapka dla osób, chcących więcej 



AZ-900 daje solidne podstawy i otwiera drogę do  

![Exam AZ-304: Microsoft Azure Architect Design | Testprep Training](https://www.testpreptraining.com/tutorial/wp-content/uploads/2020/07/Azure_Certification_Path1.png)

