
#What CISOs Need to Know about Cloud Computing

##Introduction

One of a CISO's most difficult challenges is sorting the valuable wheat from the overhyped chaff, and then figuring out what it means in terms of risk to your organization. There is no shortage of technology and threat trends, and CISOs need not to only determine which matter, but *how* they impact security.

The rise of cloud computing is one of the truly transformative evolutions that fundamentally change core security practices. Far more than an outsourcing model, cloud computing alters the very fabric of our infrastructure, technology consumption, and delivery models. In the long run, the cloud and mobile computing are likely to mark a larger shift than the Internet.

This series details the critical differences between cloud computing and traditional infrastructure for security professionals, as well as where to focus security efforts. We will show that the cloud doesn't necessarily increase risks -- it shifts them, and provides new opportunities for significant security improvement.

###Different, But Not the Way You Think

Cloud computing is a radically different technology model -- not just the latest flavor of outsourcing. It uses a combination of *abstraction* and *automation* to achieve previously impossible levels of efficiency and elasticity. But in the end cloud computing still relies on traditional infrastructure as its foundation. It doesn't eliminate physical servers, networks, or storage, but allows organizations to use them in different ways, with substantial benefits.

Sometimes this means building your own cloud in your own datacenter; other times it means renting infrastructure, platforms, and applications from public providers over the Internet. Most organizations will use a combination of both. Public cloud services eliminate most capital expenses and shift them to on-demand operational costs. Private clouds allow more *efficient* use of capital, tend to reduce operational costs, and increase the responsiveness of technology to internal needs.

Between the business benefits and current adoption rates, we expect cloud computing to become the dominant technology model over the next ten to fifteen years. As we make this transition *it is the technology that create clouds, rather than the increased use of shared infrastructure, that really matters for security*. Multitenancy is more an emergent property of cloud computing than a defining characteristic.

###Security Is Evolving for the Cloud

As you will see, cloud computing isn't more or less secure than traditional infrastructure -- it is *different*. Some risks are greater, some are new, some are reduced, and some are eliminated. The primary goal of this series is to provide an overview of where these changes occur, what you need to do about them, and when.

Cloud security focuses on managing the different risks associate with abstraction and automation. Mutitenancy tends to be more a compliance issue than a security problem, and we will cover both aspects. Infrastructure and applications are opened up to network-based management via Internet APIs. Everything from core network routing to creating and destroying entire application stacks is now possible using command lines and web interfaces. The early security focus has been on managing risks introduced by highly dynamic virtualized environments such as autoscaled servers, and broad network access, including a major focus on compartmentalizing cloud management.

Over time the focus is gradually shifting to hardening the cloud infrastructure, platforms, and applications, and then adapting security to use the cloud to *improve* security. For example, the need for data encryption increases over time as you migrate more sensitive data into the cloud. But the complexities of internal network compartmentalization and server patching are dramatically reduced as you leverage cloud infrastructure.

We expect to eventually see more security teams hook into the cloud fabric itself -- bridging existing gaps between security tools and infrastructure and applications with *Software Defined Security*. The same APIs and programming techniques that power cloud computing can provide highly-integrated dynamic and responsive security controls -- [this is already happening](https://securosis.com/research/publication/a-practical-example-of-software-defined-security).

This series will lay out the key differences, with suggestions for where security professionals should focus. Hopefully, by the end, you will look at the cloud and cloud security in a new light, and agree that the cloud isn't just the latest type of outsourcing.

##How the Cloud Is Different for Security

In the early days of cloud computing, even some very well-respected security professionals claimed it was little more than a different kind of outsourcing, or equivalent to the multitenancy of a mainframe. But the differences run far deeper, and we will show how they require different cloud security controls. We know how to manage the risks of outsourcing or multi-user environments; cloud computing security builds on this foundation and adds new twists.

These differences boil down to *abstraction* and *automation*, which separate cloud computing from basic virtualization and other well-understood technologies.

###Abstraction

Abstraction is the extensive use of multiple virtualization technologies to separate compute, network, storage, information, and application resources from the underlying physical infrastructure. In cloud computing we use this to convert physical infrastructure into a *resource pool* that is sliced, diced, provisioned, deprovisioned, and configured on demand, using the automation we will talk about next.

It really is a bit like the matrix. Individual servers run little more than a hypervisor with connectivity software to link them into the cloud, and the rest is managed by the cloud controller. Virtual networks overlay the physical network, with dynamic configuration of routing at all levels. Storage hardware is similarly pooled, virtualized, and then managed by the cloud control layers. The entire physical infrastructure, less some dedicated management components, becomes a collection of resource pools. Servers, applications, and everything else runs on top of the virtualized environment.

Abstraction impacts security significantly in four ways:

* Resource pools are managed using standard, web-based (REST) Application Programming Interfaces (APIs). The infrastructure is managed with network-enabled software at a fundamental level.
* Security can lose visibility into the infrastructure. On the network we can't rely on physical routing for traffic inspection or management. We don't necessarily know which hard drives hold which data.
* Everything is virtualized and portable. Entire servers can migrate to new physical systems with a few API calls or a click on a web page.
* We gain greater *pervasive visibility* into the infrastructure configuration itself. If the cloud controller doesn't know about a server it cannot function. We can map the complete environment with those API calls.

We have focused on *Infrastructure as a Service*, but the same issues apply to *Platform* and *Software as a Service*, except they often offer even less visibility.

###Automation

Virtualization has existed for a long time. The real power cloud computing adds is *automation*. In basic virtualization and virtual data centers we still rely on administrators to manually provision and manage our virtual machines, networks, and storage. Cloud computing turns these tasks over to the cloud controller to coordinate all these pieces (and more) using *orchestration*.

Users ask for resources via web page or API call, such as a new server with 1tb of storage on a particular subnet, and the cloud determines how best to provision it from the resource pool; then it handles installation, configuration, and coordinating all the networking, storage, and compute resources to pull everything together into a functional and accessible server. No human administrator required.

Or the cloud can monitor demand on a cluster and add and remove fully load-balanced and configured systems based on rules, such as average system utilization over a specified threshold. Need more resources? Add virtual servers. Systems underutilized? Drop them back into the resource pool. In public cloud computing this keeps costs down as you expand and contract based on what you need. In private clouds it frees resources for other projects and requirements, but you still need a shared resource pool to handle overall demand. But you are no longer stuck with under-utilized physical boxes in one corner of your data center and inadequate capacity in another.

The same applies to platforms (including databases or application servers) and software; you can expand and contract database storage, software application server capacity, and storage as needed -- without additional capital investment.

In the real world it isn't always so clean. Heavy use of public cloud may exceed the costs of owning your own infrastructure. Managing your own private cloud is no small task, and is ripe with pitfalls. And abstraction does reduce performance at certain levels, at least for now. But with the right planning, and as the technology continues to evolve, the business advantages are undeniable.

>The NIST model of cloud computing is the best framework for understanding the cloud. It consists of five *Essential Characteristics*, three *Service Models* (IaaS, PaaS, and SaaS) and four *Delivery Models* (public, private, hybrid and community). Our characteristic of *abstraction* generally maps to *resource pooling* and *broad network access*, while *automation* maps to *on-demand self service*, *measured service*, and *rapid elasticity*. We aren't proposing a different model, just overlaying the NIST model to better describe things in terms of security.

>Thanks to this automation and orchestration of resource pools, clouds are incredibly elastic, dynamic, agile, and resilient.

But even more transformative is the capability for applications to *manage their own infrastructure* because everything is now programmable. The lines between development and operations blur, offering incredible levels of agility and resilience, which is one of the concepts underpinning the *DevOps movement*. But of course done improperly it can be disastrous.

###Cloud, DevOps, and Security in Practice: Examples

Here are a few examples that highlight the impact of abstraction and automation on security. We will address the security issues later in this paper.

* **Autoscaling:** As mentioned above, many IaaS providers support autoscaling. A monitoring tool watches server load and other variables. When the average load of virtual machines exceeds a configurable threshold, new instances are launched from the same base image with advanced initialization scripts. These scripts can automatically configure all aspects of the server, pulling metadata from the cloud or a configuration management server. Advanced tools can configure entire application stacks. But these servers may only exist for a short period, perhaps never during a vulnerability assessment window. Or images may launch in the wrong zone, with the wrong network security rules. The images and initialization scripts might not be up to date for the latest security vulnerabilities, creating cracks in your defenses.
* **Immutable Servers:** Autoscaling can spontaneously and automatically orchestrate the addition and subtraction of servers and other resources. The same concepts can eliminate the need to patch. Instead of patching a running server you might use the same scripting and configuration management techniques, behind a virtual load balancer, to launch new, up-to-date versions of a server and then destroy the unpatched virtual machines.
* **Snapshots:** Cloud data typically relies on virtual storage, and even running servers use what are essentially virtual hard drives with RAID. A snapshot is a near-instant backup of all the data on a storage volume, since it merely needs to copy one version of the data, without taking the system down on affecting performance. These snapshots are incredibly portable and, in public clouds, can be made public with a single API call. Or you could write a program to snapshot all your servers at once (if your cloud has the capacity). This is great for forensics, but also enables an attacker to copy your entire data center and make it public with about 10 lines of code.
* **Management Credentials:** The entire infrastructure deployed on the cloud is managed, even down to the network and server level, using API calls and perhaps web interfaces. Administrator tools typically keep these credentials in memory as environment variables or the registry, making them accessible even without administrative control over the cloud admin's workstation. Also, most clouds don't provide an audit log of these commands. Many organizations fail to compartmentalize the rights of cloud administrators, leaving their entire infrastructure open to a single compromised system.
* **Software Defined Security:** With only 20 lines of code you can connect to your cloud over one API, your configuration management tool with another, and your security tool with a third. You can instantly assess the configuration and security of every server in your environment, without any scanning, in real time. This is nearly impossible with traditional security tools.

Snapshots highlights some of the risks of abstraction. Autoscaling, some risks of automation, and management credentials, the risks of both. But Software Defined Security and immutable servers offer advantages. We will dig into specifics next, now that we have highlighted the core differences.

And all that without mentioning multitenancy or outsourcing.

##Adapting Security for Cloud Computing

If you didn't already, you should now have a decent understanding of how cloud computing differs from traditional infrastructure. Now it's time to switch gears to how to evolve security to address shifting risks.

These examples are far from comprehensive, but offer a good start and sample of how to think differently about cloud security.

###General Principles

As we keep emphasizing, taking advantage of the cloud poses new risks, as well as both increasing and decreasing existing risks. The goal is to leverage the security advantages, freeing up resources to cover the gaps. There are a few general principles for approaching the problem that help put you in the proper state of mind:

* *You cannot rely on boxes and wires.* Quite a bit of classical security relies on knowing the physical locations of systems, as well as the network cables connecting them. Network traffic in cloud computing is virtualized, which completely breaks this model. Network routing and security are instead defined by software rules. There are some advantages here, which are beyond the scope of this paper but which we will detail with future research.
* *Security should be as agile and elastic as the cloud itself.* Your security tools need to account for the highly dynamic nature of the cloud, where servers might pop up automatically and run for only an hour before disappearing forever.
* *Rely more on policy-based automation.* Wherever possible design your security to use the same automation as the cloud itself. For example there are techniques to automate (virtual) firewall rules based on tags associated with a server, rather than applying them manually.
* *Understand and adjust for the characteristics of the cloud.* Most virtual network adapters in cloud platforms disable network sniffing, so that risk drops off the list. *Security groups* are essentially virtual firewalls that on individual instance, meaning you get full internal firewalls and compartmentalization by default. Security tools can be embedded in images or installation scripts to ensure they are always installed, and cloud-aware ones can self configure. SAML can be used to provide absolute device and user authentication control to external SaaS applications. All these and more are enabled by the cloud, once you understand its characteristics.
* *Integrate with DevOps.* Not all organizations are using DevOps, but DevOps principles are pervasive in cloud computing. Security teams can integrate with this approach and leverage it themselves for security benefits, such as automating security configuration policy enforcement.

>Defining DevOps
>
>DevOps is [an IT model that blurs the lines between development and IT operations.](http://en.m.wikipedia.org/wiki/Devops) Developers play a stronger role in managing their own infrastructure through heavy use of programming and automation. Since cloud enables management of infrastructure using APIs, it is a major enabler of DevOps. While it is incredibly agile and powerful, lacking proper governance and policies it can also be disastrous since it condenses many of the usual application development and operations check points.

These principles will get you thinking in cloud terms, but let's look at some specifics.

###Control the Management Plane

The management plane is the administrative interfaces, web and API, used to manage your cloud. It exists in all types of cloud computing service models: IaaS, PaaS, and SaaS. Someone who compromises a cloud administrator's credentials has the equivalent of unmonitored physical access to your entire data center, with enough spare hard drives, fork lifts, and trucks to copy the entire thing and drive away. Or blow the entire thing up.

* We cannot overstate the importance of hardening the management plane. It literally provides absolute control over your cloud deployment -- often including all disaster recovery.*

We have five recommendations for securing the management plane:

* If you manage a private cloud, ensure you harden the web and API servers, keeping all components up to date and protecting them with the highest levels of web application security. This is no different than protecting any other critical web server.
* Leverage the Identity and Access Management features offered by the management plane. Some providers offer very fine-grained controls. Most also integrate with your existing IAM using federated identity. Give preference to your platform/provider's controls and...
* Compartmentalize with IAM. No administrator should have full rights to all aspects of the cloud. Many providers and platforms support granular controls, including roles and groups, which you can leverage to restrict the damage potential of a compromised developer or workstation. For example, you can have a separate administrator for assigning IAM rights, only allow administrators to manage certain segments of your cloud, and further restrict them from terminating instances.
* Add auditing, logging, and alerting where possible. This is one of the more difficult problems in cloud security because few cloud providers audit administrator activity -- such as who launched or stopped a server using the API. For now you will likely need a third-party tool or to work with particular providers for necessary auditing.
* Consider using security or cloud management proxies. These tools and services proxy the connection between a cloud administrator and the public or private cloud management plane. They can apply additional security rules and fill logging and auditing gaps.

###Automate Host (Instance) Security

An *instance* is a virtual machine, which is based on a stored template called an *image*. When you ask the cloud for a server you specify the image to base it on, which includes an operating system and might bring a complete single-server application stack. The cloud then configures it using scripts which can embed administrator credentials, provide an IP address, attach and format storage, etc.

Instances may exist for years or minutes, are configured dynamically, and can be launched nearly anywhere in your infrastructure -- public or private. You cannot rely on manually assessing and adjusting their security. This is very different than building a server in a test environment, performing a vulnerability scan, and then physically installing it behind a particular firewall and IPS. More security needs to be embedded in the host itself, and the images the instances are based on.

Fortunately, these techniques *improve your ability to enforce secure configurations.*

* Embed security in images and at launch. If you use your own images, you can embed security settings and agents in the base images, and set them to activate and self-configure (after connecting to their management server) when an instance launches. Alternatively, many clouds and images support passing initialization scripts to new instances, which process them during launch using the same framework the cloud uses to configure essential settings. You can embed security settings and install security software in these scripts.
* Integrate with configuration management. Most serious cloud administrators rely on a new breed of configuration management tools to dynamically manage their systems with automation. Security can leverage these to enforce base security configurations, even down to specific application settings, which apply to all managed systems. Set properly, these configuration management tools handle both initial configurations and maintaining state, overwriting local changes when policy pulls and pushes occur.
* Dynamically configure security agents. When security agents are embedded into images or installed automatically on launch, default settings rarely meet a system's particular security requirements. Thankfully, cloud platforms provide rich metadata on instances and their environment -- including system configuration, network configuration, applications installed, etc. Cloud-aware security agents connect instantly to the management server on launch, and then self-configure with policies leveraging their information. They can also update settings in near real time based on new policies or changes in the cloud.
* Security agents should be lightweight, designed for the cloud, and cloud agnostic. You shouldn't need 8 different security agents for 12 different cloud providers, and agents shouldn't materially increase system resource requirements or struggle to communicate in a dynamic and virtual network.
* Host security tools should support REST APIs. This enables you to integrate your security into the cloud fabric itself when needed. Agents don't necessarily need to communicate with the management server over a REST API, but the management server should expose key functions via (secure) API. This enables you to, for example, write scripts to pull host security information, compare it against network security information, and make adjustments or generate reports. Or integrate security alerts and status from the host tool into your SIEM without additional connectors.

>[REST APIs](http://en.m.wikipedia.org/wiki/REST_API) are the dominant format for APIs in web-friendly applications. They run over HTTP and are much easier to integrate and manage compared to older SOAP APIs.

###Intelligently Encrypt

There are three reasons to encrypt data in the cloud, in order of their importance:

1. Compliance.
2. To protect data in backups, snapshots, and other portable copies or extracts.
3. To protect data from cloud administrators.

*How* you encrypt varies greatly, depending on where the data resides and which particular risks most concern you. For example many cloud providers encrypt object file storage or SaaS by default, but *they* manage the keys. This is often acceptable for compliance but doesn't protect against a management plane breach.

We wrote a [paper on infrastructure encryption for cloud](https://securosis.com/Research/Publication/defending-cloud-data-with-infrastructure-encryption), from which we extracted some requirements which apply across encryption scenarios:

* If you are encrypting for security (as opposed to a compliance checkbox) you need to *manage your own keys*. If the vendor manages your keys your data may still be exposed in the event of a management plane compromise.
* Separate key management from cloud administration. Sure, we are all into DevOps and flattening management, but this is one situation where security should manage *outside* the cloud management plane.
* Use key managers that are as agile and elastic as the cloud. Like host security agents, your key manager needs to operate in an environment where servers appear and disappear automatically, and networks are virtual.
* Minimize SaaS encryption. The only way to encrypt data going to a SaaS provider is with a proxy, and encryption breaks the processing of data at the cloud provider. This reduces the utility of the service, so minimize which fields you need to encrypt. Or, better yet, trust your provider.
* Use *secure cryptography agents and libraries* when embedding encryption in hosts or IaaS and PaaS applications. The defaults for most crypto libraries used by developers are not secure. Either understand how to make them secure or use libraries designed from the ground up for security.

###Federate and Automate Identity Management

Managing users and access in the cloud introduces two major headaches:

* Controlling access to external services without having to manage a separate set of users for each.
* Managing access to potentially thousands or tens of thousands of ephemeral virtual machines, some of which may only exist for a few hours.

In the first case, and often the second, federated identity is the way to go:

* For external cloud services, especially SaaS, rely on SAML-based federated identity linked to your existing directory server. If you deal with many services this can become messy to manage and program yourself, so consider one of the identity management proxies or services designed specifically to tackle this problem.
* For access to your actual virtual servers, consider managing users with a dynamic privilege management agent designed for the cloud. Normally you embed SSH keys (or known Windows admin passwords) as part of instance initialization (the cloud controller handles this for you). This is highly problematic for privileged users at scale, and even straight directory server integration is often quite difficult. Specialized agents designed for cloud computing dynamically update users, privileges, and credentials at cloud speeds and scale.

###Adapt Network Security

Networks are completely virtualized in cloud computing, although different platforms use different architectures and implementation mechanisms, complicating the situation. Despite that diversity there are consistent traits to focus on. The key issues come down to loss of visibility using normal techniques, and adapting to the dynamic nature of cloud computing.

All public cloud providers disable networking sniffing, and that is an option on all private cloud platforms. A bad guy can't hack a box and sniff the entire network, but you also can't implement IDS and other network security like in traditional infrastructure. Even when you can place a physical box on the network hosting the cloud, you will miss traffic between instances on the same physical server, and highly dynamic network changes and instances appear and disappear too quickly to be treated like regular servers. You can sometimes use a virtual appliance instead, but unless the tool is designed to cloud specifications, even one that works in a virtual environment will crack in a cloud due to performance and functional limitations.

While you can embed more host network security in the images your virtual machines are based on, the standard tools typically won't work because they don't know exactly where on the network they will pop up, nor what addresses they need to talk to. On a positive note, all cloud platforms include basic network security. Set your defaults properly, and every single server effectively comes with its own firewall.

We recommend:

* Design a good baseline of Security Groups (the basic firewalls that secure the networking of each instance), and use tags or other mechanisms to automatically apply them based on server characteristics. A Security Group is essentially a firewall around every instance, offering compartmentalization that is extremely difficult to get in a traditional network.
* Use a host firewall, or host firewall management tool, designed for your cloud platform or provider. These connect to the cloud itself to pull metadata and configure themselves more dynamically than standard host firewalls.
* Also consider pushing more network security, including IDS and logging, into your instances.
* Prefer virtual network security appliances that support cloud APIs and are designed for the cloud platform or provider. For example, instead of forcing you to route all your virtual traffic through it as if you were on a physical network, the tool could distribute its own workload -- perhaps even integrating with hypervisors.
* Take advantage of cloud APIs. It is very easy to pull every Security Group rule and then locate every instance. Combined with some additional basic tools you could then automate finding errors and omissions. Many cloud deployments do this today as a matter of course.
* Whatever tools you use, they *must* be able to account for the high rate of servers appearing and disappearing in a cloud. Rules must follow hosts.

###Leverage Cloud Characteristics

This section is a bit more advanced, but you can reap significant security advantages once you start to leverage the nature of the cloud. Instead of patching, just launch properly configured new servers and swap using on a cloud load balancer. Find every single system in your cloud deployment, including extensive metadata, with a simple API call. Deploy applications to a Platform as a Service (PaaS) and stop worrying about misconfigured servers. Here are some real world examples and recommendations to get you started, but they barely scratch the surface:

* Use the *immutable servers* concept instead of patching. Few sysadmins patch servers without trepidation, and this is a frequent source of downtime. Eliminate the worry by running your applications behind cloud load balancers, and instead of patching servers, launch new ones with the updated software. Then slowly (or quickly) switch traffic to the new, 'patched' servers. If something doesn't work your old servers are still there and you can shift traffic back. It is like having a spare datacenter lying around.
* Leverage *stateless security* strategies to mange your environment in real time. Normally we rely on knowledge from scanners and assessments to understand our assets and environments, which can be out of date and difficult to keep complete. The cloud controller knows where everything is, how it is configured (to a degree), and even who owns or created it, so we have a constant stream of comprehensive real-time data. A server cannot exist in the cloud without the controller knowing about it. Your entire network architecture is but an API call away -- no scanners needed. Track and manage your security state in real time.
* Automate more security. Embed security configurations and agents into images, or inject them into instances when they launch. Every virtual machine, when launched, can automatically configure host-based security -- especially if they can communicate with a management server designed for the cloud. For example, a host can register itself with a configuration management server, then secure running services by default depending on what the host is intended for. You could even automatically adjust Security Group firewall rules based on the software services running on the host, who owns it, and where it is in your application stack.
* Standardize security with Platform as a Service. Hate patching database servers or configuring them properly? Struggle with developers and admins who open up too many services on application servers? Use Platform as a Service instead, and improve your ability to standardize security.
* Build a security abstraction layer. Nothing prevents your security team from using the same cloud APIs and management tools as administrators and developers. Configured properly, this provides security oversight and control without interfering with development or operations. For example you could restrict management of cloud IAM to the security team, enabling them to assume management of a server in case of a security incident. The security team could control key network Security Groups and security in production, while still allowing developers to manage it themselves in more isolated development environments. Embed a host security agent into every image (or instance, using launch scripts) and security gains a hook into every running virtual machine.
* Move to *Software Defined Security*. This concept is an extension of basic automation. Nothing prevents Security from writing its own programs using cloud APIs, and the APIs of security and operations tools, so you can create powerful and agile security controls. For example you could write a small program to find every instance in your environment that isn't linked into your configuration management tool, and recheck every few minutes. The tool would identify who launched the server, the operating system, where it was on the network, and the surrounding network security. You could, at a keystroke, take control of the server, notify the owner, and isolate it on the network until you know what it is for; then integrate it into configuration management and enforce security policies. All with perhaps 100 lines of code.

These should get you thinking, but they start to show how the cloud can nearly eradicate certain security problems and enable you to shift resources.
