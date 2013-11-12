
# What CISOs Need to Know About Cloud Computing

## Introduction

As a CISO, one of the most difficult challenges is sorting the valuable wheat from the overhyped chaff, then figure out how it changes the risk to your organization. There are no shortage of technology and threat trends, and a CISO needs to not only determine which ones matter, but *how* they impact security. 

The rise of cloud computing is one of those truly transformative evolutions that fundamentally changes some of the core practices of security. Far more than an outsourcing model, it alters the very fabric of our infrastructure and our technology consumption and delivery models. Combined with mobile computing, it is likely a more radical shift than our initial adoption of the Internet. 

This series details the critical differences between cloud computing and traditional infrastructure that matter to security professionals, and where to focus security efforts. We will show that cloud doesn't necessarily increase risks, it shifts them, and even opens opportunities for significant security improvements.

###Different, But Not How You Think

Cloud computing is a radically different technology model, not merely a new form of outsourcing. It uses a combination of *abstraction* and *automation* to achieve previously-unheard of levels of efficiency and elasticity. Although, in the end, cloud computing still relies on traditional infrastructure for its foundation. It doesn't eliminate physical servers, networks, or storage, but allows organizations to use them in different ways for significant benefits.

Sometimes this means building your own cloud in your own datacenter, and other times it means renting infrastructure, platforms, and applications from public providers over the Internet. Practically speaking, most organizations will use combinations of both. Public cloud services eliminate most capital expenses and shift them to on-demand operational costs. Private clouds allow more *efficient* uses of capital expenses, tend to reduce operational costs, and increase the responsiveness of technology to internal needs.

The business benefits, and current adoption rates, lead us to believe cloud computing will likely become the dominant technology model over the next ten to fifteen years. As we make this transition *it is the technology that create clouds, not the increased use of shared infrastructure, that really matters for security*. If anything, multitenancy is an emergent property of cloud computing, not a defining characteristic.

###Security is Evolving for the Cloud

As you will see, cloud computing isn't more or less secure than traditional infrastructure, it is different. Some risks are greater, some are new, some are reduced, and some eliminated. The primary goal of this series is to provide an overview of where these changes occur, what you need to do about them, and when.

Cloud security focuses on managing the different risks associate with abstraction and automation. Mutitenancy tends to be more of a compliance than a security issue, and we will cover it.  Infrastructure and applications open up to network-based management using Internet-compatible APIs. Everything from core network routing to creating and destroying entire application stacks is now possible using command lines and web interfaces. The early security focus is on managing the risks introduced by highly dynamic virtualized environments, such as securing autoscaled servers, and broad network access, including a major focus on compartmentalizing cloud management. 

Over time the focus shifts to hardening the cloud infrastructure, platforms, and applications, and then adapting security to use the cloud to *improve* security. For example, the need for data encryption increases over time the more you migrate sensitive data into the cloud. However, the complexities of internal network compartmentalization and server patching are dramatically reduced as you rely more on cloud infrastructure. 

Eventually, we expect to see more security teams hook into the cloud fabric itself; bridging existing gaps between security tools and our infrastructure and applications with *Software Defined Security*. Using the same APIs and programming techniques that power cloud computing for highly-integrated dynamic, responsive security controls, and ([it is already being done today](https://securosis.com/research/publication/a-practical-example-of-software-defined-security)).

This series will lay out the key differences and suggestions on where security professionals should focus. Hopefully, by the end, you will look at cloud and cloud security in a new light, and definitely not consider cloud merely a new kind of outsourcing.

## How Cloud is Different for Security

In the early days of cloud computing, even some very well-respected security professionals claimed it was little more than a different kind of outsourcing, or akin to the multitenancy of a mainframe. The reality is the technology differences run far deeper, and as we will show these result in definitive changes in necessary cloud security controls. We know how to manage the risks of outsourcing or multi-user environments; cloud computing security builds on this foundation and adds some new twists. 

The crux of these differences boil down to *abstraction* and *automation*. The two technology pieces that truly separate cloud computing from basic virtualization and other well-understood technologies.

###Abstraction

Abstraction is the extensive use of multiple virtualization technologies to separate the compute, network, storage, information, and application resources from the underlying physical infrastructure. In cloud computing we use this to convert the physical infrastructure into a *resource pool* that is sliced, diced, provisioned, deprovisioned, and configured on-demand, using the automation we will talk about in a moment. 

It really is a bit like the matrix. Individual servers run little more than a hypervisor and connectivity software to link them into the cloud, and the rest is managed by the cloud controller. Virtual networks overlay the physical network, with dynamic configuration of all levels of routing. Storage hardware is similarly pooled together, virtualized, and then managed by the cloud control layers. The entire physical infrastructure, minus some dedicated pieces to manage the cloud, becomes a collection of resource pools. Servers, applications, and everything else runs on top of the virtualized environment.

Abstraction impacts security significantly in four ways:

* The resource pools are managed using standard, web-based (REST) Application Programming Interfaces (APIs). The infrastructure is fundamentally managed with network-enabled software.
* Security potentially loses visibility into the infrastructure. On the network we can't rely on physical routing for traffic inspection and management. We don't necessarily know which hard drives hold which data. 
* Everything is virtualized and portable. Entire servers can migrate to new physical systems with a few API calls or a click on a web page.
* We gain greater *pervasive visibility* into the infrastructure configuration itself. If the cloud controller doesn't know about a server, it can't function. We can map our complete environment with those same API calls.

We have so far focused on *Infrastructure as a Service*, but these same issues extend to *Platform* and *Software as a Service*, except we often have even less visibility.

###Automation

Virtualization has existed for a long time. The real power cloud computing adds is *automation*. In basic virtualization and virtual data centers we still rely on administrators to manually provision and manage our virtual machines, networks, and storage. Cloud computing turns over these tasks to the cloud controller to coordinate all these pieces (and more) using *orchestration*. 

Users ask for resources via web page or API call, like a new server on a particular subnet with 1 TB of storage, and the cloud determines how to best provision it from the resource pool, then handles installation, configuration, and coordinating all the networking, storage, and compute resources to pull everything together into a functional, accessible, server. No human administrator required.

Or, the cloud can monitor demand on a cluster and add and remove fully load-balanced and configured systems based on rules, such as average system utilization. Need more resources? Add some virtual servers. Systems under-utilized? Drop them back to the resource pool. In public cloud computing this keeps costs down as you expand and contract based on what you need. In a private cloud this frees resources for other projects or needs, but you still need a total resource pool to handle your overall demands. However, you are no longer stuck with under-utilized physical boxes in one corner of your data center, and under-capacity in another. 

The same applies to platforms (like databases or application servers), and software, since you can similarly expand and contract database storage or software application users or storage as needed, without additional capital investment.

In the real world it isn't always so clean. Heavy use of public cloud may exceed the costs of owning your own infrastructure. Managing your own private cloud is no-small task, ripe with pitfalls. And abstraction does reduce performance at certain levels, at least for now. But with the right planning, and as the technology continues to evolve, the business advantages are undeniable.

>The NIST model of cloud computing is the best framework for understanding cloud. It consists of five *Essential Characteristics*, Three *Service Models* (IaaS, PaaS, and SaaS) and four *Delivery Models* (public, private, hybrid and community). Our characteristic of *abstraction* generally maps to *resource pooling* and *broad network access*, while *automation* maps to *on-demand self service*, *measured service*, and *rapid elasticity*. We aren't proposing a different model, just overlaying the NIST model to better describe things in terms of security.

>Thanks to this automation and orchestration of resource pools, clouds are incredibly elastic, dynamic, agile, and resilient. 

But even more transformative is the capability for applications to *manage their own infrastructure* since everything is now programmable. The lines between development and operations blur for incredible levels of agility and resilience, which is one of the founding concepts of the *DevOps movement*. Then again, done improperly it can be disastrous.

###Cloud, DevOps, and Security in Practice: Examples

Here are a few examples that highlight the impact of abstraction and automation on security. If we highlight a security issue, we will address it later in this paper.

* **Autoscaling:** As mentioned above, many IaaS providers support autoscaling. A monitoring tool keeps an eye on server load and other variables. When average load of running virtual machines passes a threshold, new instances are launched using a base image and special initialization scripts. These scripts can automatically configure all aspects of the server, pulling metadata from the cloud or a configuration management server. Advanced tools can even configure entire application stacks. However, these servers may only exist for a short period of time, outside of vulnerability assessment windows. Or images may launch in the wrong zone, with the wrong network security rules. The images and initialization scripts may not be up to date for the latest security vulnerabilities, creating cracks in your defenses. 
* **Immutable Servers:** In autoscaling, we showed how the cloud can spontaneously orchestrate the addition and subtraction of servers and other resources, automatically. The same concepts can eliminate the need to patch. Instead of patching a running server, you use the same scripting and configuration management techniques, behind a virtual load balancer,  to launch new, up-to-date versions of a server and then destroy the unpatched virtual machines. 
* **Snapshots:** Cloud data typically relies on virtual storage, and even running servers use what are essentially virtual hard drives running on RAID. A snapshot is a near-instant backup of all the data on that storage volume, since it merely needs to copy one version of the data, without taking the system down on affecting performance. These snapshots are incredibly portable and, in public cloud, can be made public with a single API call. Or, you can write a program to snapshot all your servers at once (if your cloud has the space and performance). This is great for forensics, but also enables an attacker to copy your entire data center and make it public in about 10 lines of code.
* **Management Credentials:** The entire infrastructure deployed on the cloud is managed, even down to the network and server level, using API calls and perhaps web interfaces. Administrator tools typically keep these credentials in memory as environment variables or the registry, making them accessible without administrative control over the cloud admin's workstation. Also, most clouds don't even provide an audit log of these commands. Many organizations fail to compartmentalize the rights of these cloud admins, opening up the entire infrastructure with a single compromised system.
* **Software Defined Security:** With only 20 lines of code you can connect to your cloud over one API, your configuration management tool with another, and your security tool with a third. You can instantly assess the configuration and security of every server in your environment, without any scanning, in real time. This is nearly impossible with traditional security tools.

Snapshots highlights some of the risks of abstraction. Autoscaling, some risks of automation, and management credentials, the risks of both. But we also show in our Software Defined Security and immutable server examples potential advantages. We will dig into these in the next section, and just wanted to highlight the core differences. 

All this without once mentioning multitenancy or outsourcing. 

## Adapting Security for Cloud Computing

If you didn't already, you should now have a decent understanding of how cloud computing differs from traditional infrastructure. Now it's time to switch gears and provide guidance on how to evolve your security to address the shifting risks. 

These examples are far from comprehensive, but were selected to give a good start and a sample of how to think differently about cloud security.

###General Principles

As we keep emphasizing, adopting cloud necessarily increase your overall risks; some increase, some decrease, and the goal is to leverage the security advantages of cloud so you can move resources to cover the new gaps. There are a few general principles of approaching the problem that help put you in the proper state of mind:

* *You cannot rely on boxes and wires.* A fair bit of our security relies on knowing the physical locations of systems, and the network cables connecting them. Network traffic in cloud computing is virtualized, which completely breaks this model. Network routing and security are defined instead using software rules. There are even some advantages here, which are beyond the scope of this paper and we will detail in future research. 
* *Security should be as agile and elastic as the cloud itself.* Your security tools need to account for the highly dynamic nature of cloud, where servers might pop up automatically and only run for an hour before disappearing forever. 
* *Rely more on policy-based automation.* Wherever possible, design your security to use the same automation as the cloud itself. For example, there are techniques to automate (virtual) firewall rules based on tags associated with a server, instead of applying them manually.
* *Understand, and adjust for, the characteristics of the cloud.* Most virtual network adapters in cloud platforms disable network sniffing, so that risk drops off the list. *Security groups* are essentially virtual firewalls that surround every individual instance, meaning you get full internal firewalls and compartmentalization by default. Security tools can be embedded in images or installation scripts to ensure they are always installed, and cloud-aware ones can self configure. SAML can be used to provide absolute device and user authentication control to external SaaS applications. All of these (and more) are enabled by the cloud, once you understand cloud characteristics.
* *Integrate with DevOps.* Not all organizations are using DevOps, but aspects of DevOps principles are pervasive in cloud computing. Security teams can integrate with this approach and leverage it themselves for security benefits, such as automating security configuration policy enforcement.

>Defining DevOps
>DevOps is [an IT model that blurs the lines between development and IT operations.](http://en.m.wikipedia.org/wiki/Devops) Developers play a stronger role in managing their own infrastructure through heavy use of programming and automation. Since cloud enables management of infrastructure using APIs, it is a major enabler of DevOps. While it is incredibly agile and powerful, lacking proper governance and policies it can also be disastrous since it condenses many of the usual application development and operations check points.

These principles will get you thinking in cloud terms, but let's look at some specifics.

###Control the Management Plane

The management plane refers to the administrative interfaces, web and API, used to manage your cloud. It exists in all types of cloud computing service models: IaaS, PaaS, and SaaS. Someone who compromises a cloud administrator's credentials has the equivalent of unmonitored physical access to your entire data center, with enough spare hard drives, fork lifts, and trucks to copy the entire thing and drive away. Or blow the entire thing up with some explosives.

*We cannot possibly understate the importance in hardening the management plane. It literally provides absolute control over your cloud deployment, often including all your disaster recovery.*

There are five recommendations to secure the management plane:

* If you manage a private cloud, ensure you harden the web and API server, keeping all components up to date and protecting with the highest levels of web application security. This is no different than protecting any other critical web server.
* Leverage the Identity and Access Management features support by the management plane. Some providers offer very fine-grained controls. Most will also integrate with your existing IAM using federated identity. Give preference to your platform/provider's controls and...
* Compartmentalize with IAM. No administrator should have full rights to all aspects of the cloud. Many providers and platforms support granular controls, including roles and groups, you can leverage to restrict the damage potential of any single  developer or workstation being compromised. For example, you can have a separate administrator for assigning IAM rights, only allow admins to manage certain segments of your cloud, and further restrict them from terminating instances. 
* Add auditing, logging, and alerting where possible. This is one of the more-difficult problems in managing cloud security since few cloud providers audit administrator activity (such as who launched or stopped a server using the API). For now, you will likely need to use a third-party tool or work with particular providers that support necessary auditing.
* Consider using security or cloud management proxies. These tools or services proxy the connection between a cloud administrator and the public or private cloud management plane. They can apply additional security rules and fill the logging and auditing gap.

###Automate Host (Instance) Security

An *instance* is a virtual machine that is based on a stored template called an *image*. When you ask the cloud for a server you specify the image to base it from, which can include the operating system or a complete single-server application stack. The cloud then configures it using scripts that allows it to run, such as embedding administrator credentials, providing an IP address, attaching and formatting storage, and so on. 

Instances may exist for years or minutes, are configured dynamically, and can be launched nearly anywhere in your infrastructure, public or private. You can't rely on manually assessing and adjusting their security. This is very different than building a server in a test environment, performing a vulnerability scan, and then physically installing it behind a particular firewall and IPS. More security needs to be embedded in the host itself, and the images they are based on.

Fortunately, these techniques *improve your ability to enforce secure configurations.*

* Embed security in images and at launch. If you use your own images, you can embed security settings and agents in the base images, and set them to activate and self-configure (after connecting to their management server) when an instance launches. Alternatively, many clouds and images support passing initialization scripts to new instances, which process them during launch using the same framework the cloud uses to configure essential settings. You can embed security settings, including the installation of security software, into these scripts.
* Integrate with configuration management. Most serious cloud administrators rely on a new breed of configuration management tools to dynamically manage their systems with automation. Security can leverage these to enforce base security configurations, even down to specific application settings, that apply to all managed systems. Set properly, these configuration management tools handle both initial configurations and maintaining state, overwriting local changes when policy pulls or pushes occur.
* Dynamically configure security agents. When security agents are embedded into images or installed automatically on launch, default settings will rarely meet that system's particular security requirements. Thankfully, cloud platforms provide rich metadata on instances and the environment around them, including system configuration, network configuration, applications installed, etc. Cloud-aware security agents know to connect instantly to their management server on launch, and then self-configure based on policies that leverage this information. They can also update settings in near real time based on new policies, or changes in the cloud. 
* Security agents should be lightweight, designed for cloud, and cloud agnostic. You shouldn't need 8 different security agents for 12 different cloud providers, and the agents shouldn't materially increase your system resource requirements or struggle to communicate in a dynamic, virtual network. 
* Host security tools should support REST APIs. This allows you to integrate your security into the cloud fabric itself, when needed. The agents don't necessarily need to communicate with the management server over a REST API, but the management server should expose key functions via (secure) API. This allows you to, for example, write scripts to pull host security information, compare it to network security information, and make adjustments or generate reports. Or integrate security alerts and status from the host tool into your SIEM without additional connectors.

>[REST APIs](http://en.m.wikipedia.org/wiki/REST_API) are the dominant format for APIs in web-friendly applications. They run over HTTP and are much easier to integrate and manage compared to older SOAP APIs.

###Intelligently Encrypt

There are three reasons to encrypt data in the cloud, in the order of their importance:

* Compliance.
* To protect data in backups, snapshots, and other portable copies or extracts.
* To protect data from cloud administrators.

*How* you encrypt varies greatly depending on where the data resides and which particular risks concern you. For example, many cloud providers encrypt object file storage or your SaaS by default, but they manage the keys. This is often acceptable for compliance, but doesn't protect you against a management plane breach. 

We have written a [full paper on infrastructure encryption for cloud](https://securosis.com/Research/Publication/defending-cloud-data-with-infrastructure-encryption), and here are some requirements that apply across encryption scenarios:

* If you are encrypting for security (as opposed to a compliance checkbox) you need to *manage your own keys*. If the vendor manages the keys your data may still be exposed in the event of a management plane compromise.
* Separate key management from cloud administration. Sure, we are all into DevOps and flattening management, but this is one situation where security should manage outside the cloud management plane.
* Use key managers that are as agile and elastic as the cloud. Similar to our guidance on host security agents, your key manager needs to operate in an environment where servers appear and disappear automatically, and networks are virtual.
* Minimize SaaS encryption. The only way to encrypt data going to a SaaS provider is with a proxy, and encryption breaks the processing of data in the cloud provider. This reduces the utility of the service, so minimize which fields you need to encrypt. Or, better yet, trust the provider.
* Use *secure cryptography agents and libraries* when embedding encryption in hosts or IaaS and PaaS applications. The defaults on most crypto libraries used by developers are not secure. Either understand how to make them secure, or use libraries designed from the ground up for security.

###Federate and Automate Identity Management

Managing users and access in cloud introduces two major headaches:

* Controlling access to external services without having to manage them all as independent sets of users.
* Managing access to potentially thousands or tens of thousands of ephemeral virtual machines, some of which may only exist for a few hours.

In the first case, and often the second, federated identity is the way to go:

* For external cloud services, especially SaaS, rely on SAML-based federated identity linked to your existing directory server. If you deal with a lot of services this can become messy to manage and program yourself,  so consider one of the identity management proxies or services on the market designed specifically to tackle the problem.
* For access to your actual virtual servers consider managing users with a dynamic privilege management agent designed for cloud. Normally you embed SSH keys (or known Windows admin passwords) as part of an instances initialization process (the cloud controller handles this for you). This is highly problematic for privileged users at scale, and even straight directory server integration is often quite difficult. Specialized agents designed for cloud computing dynamically update users, privileges, and credentials at cloud speeds and scale.

###Adapt Network Security
 
 Networks are completely virtualized in cloud computing, although different platforms use different architectures and implementation mechanisms, complicating the situation. Despite that diversity, there are some consistent traits to focus on. The two biggest issues are:
 
 * Virtual networks may destroy normal network traffic visibility. A network firewall or IDS won't see traffic between two virtual machines on the same physical server, encrypted traffic between nodes, or traffic in certain Software Defined Networking (SDN) implementations. 
 * Images can be launched anywhere in your cloud, which means a server may pop up in an unexpected, unprotected, location. dynamic....."..."
 * 
 
 
* Adapt network security
    * Lose visibility, so may need to embed more in the host
    * Virtual appliances may not scale
        * Even when. They do, may not be economically viable
    * Need to be host aware
* Leverage cloud characteristics
    * Stateless security
        * You always know where ever server is, in real time
        * You can always know the configuration and have access to extensive metadata
        * Your network architecture is but an API call away
        * All is consumable using standard data formats and APIs
            * Incredible opportunity to integrate with cloud-aware security tools
    * Automated security
        * Set a security policy, link with DevOps, and have it enforced on every node
        * Centrally manage the network unreal time
        * Add a security abstraction layer, that is still part of the cloud management layer
    * Standardize security with PaaS
    * Software Defined Security

## Real world examples

* Embedding a security agent automatically
    * And validating every host is covered
* Controlling SaaS with SAML
* Compartmentalization AWS with IAM
* Hypersegregation with Security Groups

## Where to go from here

* This is only a high level overview to get you started
* The devil is in the details
* Future research


[*]: http://en.m.wikipedia.org/wiki/REST_API
