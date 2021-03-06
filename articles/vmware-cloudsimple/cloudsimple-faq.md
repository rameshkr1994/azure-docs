---
title: FAQ - Azure VMware Solutions (AVS) 
description: Frequently asked questions for Azure VMware Solutions (AVS)
author: sharaths-cs
ms.author: b-shsury 
ms.date: 08/15/2019 
ms.topic: article 
ms.service: azure-vmware-cloudsimple 
ms.reviewer: cynthn 
manager: dikamath 
---
# Frequently asked questions about VMware Solution by AVS

## AVS service

**What is Azure VMware Solutions (AVS)?**

Azure VMware Solutions (AVS) transforms and extends VMware workloads to private, dedicated clouds on Azure in minutes. AVS takes care of provisioning, managing the infrastructure, and orchestrating workloads between on-premises and Azure. Because your apps run exactly the same on-premises and in Azure, you benefit from the elasticity and services of the cloud without the complexity of rearchitecting your apps. AVS lowers your total cost of ownership with a cloud consumption model that provides on-demand provisioning, pay-as-you-grow, and capacity optimization. See [What is VMware Solution on Azure by AVS](cloudsimple-vmware-solutions-overview.md) for features, benefits and scenarios.

**What is an AVS Private Cloud?**

An AVS Private Cloud is a private, dedicated cloud that consists of a high-performance compute, storage, and networking environment deployed on the Microsoft Azure infrastructure (hardware and datacenter space) in Azure locations. An AVS Private Cloud provides a native VMware 'platform as a service'. In VMware terms, each AVS Private Cloud contains exactly one instance of the vCenter Server. The vCenter Server manages multiple ESXi nodes contained in one or more vSphere Clusters, along with the corresponding Virtual SAN (vSAN) storage. An AVS service can contain multiple AVS Private Clouds in your Azure subscription. For more details, see [AVS Private Cloud overview](cloudsimple-private-cloud.md).

**Where is the AVS service available?**

AVS is available in East US, West US, and West Europe regions with additional regions coming soon.

**How do I enable my subscription for AVS?**

You can contact your Microsoft account representative at [azurevmwaresales@microsoft.com](mailto:azurevmwaresales@microsoft.com) to enable your subscription for the AVS service. Provide your subscription ID in the email for which you want AVS service enabled. 

**How do I access the AVS portal?**

You access the AVS portal from the Azure portal. For details, see [Access the VMware Solutions (AVS) portal from the Azure portal](access-cloudsimple-portal.md).

**How do I increase capacity for an AVS Private Cloud?**

To increase capacity, purchase additional nodes from the Azure portal and then use the nodes to expand your AVS Private Cloud from the AVS portal. You can add additional nodes to an existing vSphere cluster or add them to a new vSphere cluster. For details, see [Expand an AVS Private Cloud](expand-private-cloud.md).

**What happens to my AVS Private Cloud during maintenance?**

AVS provides notification several days prior to a scheduled maintenance interval. Maintenance is done in a non-disruptive way to ensure the availability of your AVS Private Cloud. Maintenance can be of the following types:

* **AVS infrastructure**. AVS infrastructure is designed to be highly available. During this type of maintenance interval, redundant components are updated one at a time to avoid any service interruption. You maintain access to your AVS Private Cloud vCenter, all virtual machines, the internet connection from your AVS Private Cloud, and connections to on-premises or Azure.
* **AVS portal**. During this type of maintenance interval, some features on the AVS portal may be disabled or inaccessible. The notification prior to the maintenance interval includes details on feature limitations while maintenance is taking place.

## Connectivity

**What are my connectivity options to the AVS region network?**

AVS provides the following connectivity options to connect to your AVS region network. Multiple options can be used at the same time.

* **ExpressRoute connection from your on-premises datacenter to the AVS region network**. This is a high-speed, low-latency, secure private connection that uses Global Reach to bridge your on-premises ExpressRoute circuit to your AVS ExpressRoute circuit. For instructions on setting up the connection, see [Connect from on-premises to AVS using ExpressRoute](on-premises-connection.md).
* **ExpressRoute connection from your Azure virtual network to your AVS region network**. This is a high-speed, low-latency, secure private connection that uses virtual network gateways to bridge your virtual network on Azure to your AVS ExpressRoute circuit. For instructions on setting up the connection, see [Connect your AVS Private Cloud environment to the Azure virtual network using ExpressRoute](azure-expressroute-connection.md).
* **Site-to-Site VPN connection from your on-premises datacenter to your AVS region network**. This is a secure virtual private network from your on-premises VPN device to your AVS Private Cloud region. For details, see [Set up VPN gateways on AVS network](vpn-gateway.md).

**How do I connect to an AVS Private Cloud?**

You can view details of your AVS Private Cloud in the AVS portal. To connect to the vCenter that corresponds to your AVS Private Cloud, first verify that a network connection is established using Site-to-Site VPN, Point-to-Site VPN, or ExpressRoute. Then, launch the AVS portal from the Azure portal and click **Launch vSphere Client** on the Home page or on the AVS Private Cloud details page.

**What is the advantage of ExpressRoute circuits?**

An Azure ExpressRoute circuit is a high-speed, low-latency, secure connection. AVS provides a dedicated ExpressRoute circuit per region per customer. Using this circuit, you can establish a secure connection from on-premises or your Azure subscription.

**What are the network costs to connect to AVS? Do any egress charges apply between AVS and Azure, or across regions?**

There is no AVS charge for network egress. Azure standard rates apply to any egress traffic from your virtual network or from your on-premises ExpressRoute circuit.

## Networking

**What networking features are available for my AVS Private Cloud?**

You can provision VLANs (and their subnets) and firewall tables, and assign public IP addresses that map to a virtual machine running in your AVS Private Cloud. For details on networking features, see [VLANs and subnets overview](cloudsimple-vlans-subnets.md), [Firewall tables overview](cloudsimple-firewall-tables.md), and [Public IP address overview](cloudsimple-public-ip-address.md).

**How do I set up different subnets for my applications in my AVS Private Cloud?**

You create VLANs on your AVS Private Cloud from the AVS portal. After you create a VLAN, you can create a distributed port group on your AVS Private Cloud vCenter using the VLAN and create virtual machines that are connected to the distributed port group. You can enable firewall tables for the VLAN/subnet and define firewall rules to secure network traffic.

**What firewall settings are available for my AVS Private Clouds?**

You can configure rules for north-south and east-west traffic. The rules are defined in a firewall table. The firewall table can be attached to VLANs on your AVS Private Cloud. For details, see [Set up firewall tables and rules for AVS Private Clouds](firewall.md).

**Can I assign public IP addresses to VMs in my AVS Private Cloud environment?**

In the AVS portal, you can allocate a new public IP address and associate it with the private IP address of a virtual machine or an appliance. You can also create new firewall rules or apply existing firewall rules to allow traffic from specific ports and IP addresses in the portal. For details, see [Allocate public IP addresses for AVS Private Cloud environment](public-ips.md).

## Security

**What are my security options on AVS?**

AVS provides the following security features for securing your AVS Private Cloud environment:

* **Data at rest encryption**. You can encrypt data at rest residing on the vSAN storage in your AVS Private Cloud. vSAN supports external key management servers, which can be deployed in your Azure vNet or on-premises environment. For details, see [Configure vSAN encryption for your AVS Private Cloud](vsan-encryption.md).
* **Network security**. Control network traffic flow with firewall rules that apply between your AVS Private Cloud and the internet, your AVS Private Cloud and on-premises environment, or within subnets of your AVS Private Cloud.
* **Secure, private connection**. A secure, private connection is established between your on-premises network and your Azure subscription.

## Compute

**What kind of hosts are available?**

AVS offers these host types:

* **CS28 node:** CPU:2x 2.2 GHz, total 28 cores, 48 HT.  RAM: 256 GB.  Storage: 1600 GB NVMe cache, 5760 GB data (All-Flash). Network: 4x25Gbe NIC
* **CS36 node:** CPU 2x 2.3 GHz, total 36 cores, 72 HT.  RAM: 512 GB.  Storage: 3200 GB NVMe cache 11520 GB data (All-Flash).  Network: 4x25Gbe NIC
* **CS36m node:** CPU 2x 2.3 GHz, total 36 cores, 72 HT.  RAM: 576 GB.  Storage: 3200 GB NVMe cache 13360 GB data (All-Flash).  Network: 4x25Gbe NIC

**How are any hardware failures handled?**

All AVS infrastructure is continuously monitored by the AVS platform and our service operations teams. If a hardware failure is detected, a new node is added to your AVS Private Cloud and the failed node is removed.

## Storage

**What type of storage is supported on a AVS Private Cloud?**

AVS offers all-flash VMware vSAN storage with every AVS Private Cloud. Each vSphere is created with its own vSAN datastore. For details, see [AVS Private Cloud VMware components - vSAN storage](vmware-components.md#vsan-storage).

**Is encryption of data supported?**
Yes. You can set up the vSAN storage on your AVS Private Cloud to use a key management server (KMS) that is deployed on-premises or on Azure to encrypt data stored on vSAN.

**How are failed disks handled?**

AVS continuously monitors all hardware components of the AVS Private Cloud. If a disk failure is detected or a disk is identified as failing (based on heuristics), a new node is automatically added to the AVS Private Cloud. The node with the failed or failing disk is removed from the AVS Private Cloud.

## VMware

**How do I perform large-scale upload or migration of applications and data from on-premises?**

AVS provides a native VMware vSphere solution. All VMware tools for bulk data migration can be used with your AVS Private Cloud. Options include:

* VMware HCX for bulk migration of data.
* Cold migration of data using Storage vMotion from on-premises to AVS.

**Can I install any VMware tools?**

AVS provides a native VMware vSphere solution. All VMware tools used for managing your on-premises vSphere environment can be used on AVS. AVS supports a bring-your-own-license (BYOL) model for installing VMware tools.

**How are updates and upgrades managed?**

AVS manages and updates all infrastructure components of your AVS Private Cloud in a seamless non-disruptive manner. All updates and security patches released by VMware or infrastructure vendors are scheduled for update as soon as they are qualified by AVS.

AVS does not perform upgrades or updates of applications installed on the AVS Private Cloud.

## Azure Integration

**What Azure services are supported?**

AVS provides an Azure ExpressRoute connection to your subscription on Azure. All services running in your subscription can connect to your AVS Private Cloud. Examples include:

* **Azure Active Directory** as an identity source for your AVS vCenter.
* **Azure storage** for storing backups, images, and other data from your AVS Private Cloud.
* **Hybrid applications** with an application architecture that spans public and AVS Private Clouds. For example, you can create webservers in Azure that access application and database servers on your AVS Private Cloud.
* **Azure monitor** and **Azure security center** for workloads running on VMware support logging, performance metrics, and security management.

**How do I map my VMware tenants to Azure?**

AVS provides the unique ability to manage your VMware VMs on AVS Private Cloud from the Azure portal. A vCenter resource pool configured with desired resource constraints can be mapped to your subscription by your global administrator. 

**What licensing benefits do I get with Azure?**

With AVS, you can take advantage of the Azure Hybrid Usage Benefit and save up to 90% on licenses. This benefit preserves your investment in Microsoft licenses and lowers your TCO relative to other cloud solutions. You also get extended security updates for Windows Server 2008 and Microsoft SQL Server 2008. The bring-your-own-license (BYOL) model helps you keep costs low for common apps such as Veeam and Zerto. 
