<h1>High-Availability Web Architecture: Load Balancers, DNS, & Scalable App Services</h1>


<h2>Description</h2>
This project demonstrates the deployment of a dual-layered web infrastructure in Microsoft Azure. It utilizes IaaS (Infrastructure as a Service) for maximum control and PaaS (Platform as a Service) for modern scalability. The architecture ensures that applications remain online through automated health monitoring, traffic distribution, and zero-downtime deployment strategies.
<br />
<br />


<h2>Tools & Technologies:</h2>

- <b2> Traffic Management: Azure Load Balancer (Standard), Health Probes, Load Balancing Rules.  </b2>
- <b2> DNS Administration: Public & Private DNS Zones, A-Record Management. </b2>
- <b2> Compute & PaaS: Azure App Services, App Service Plans, Windows Server VMs (IIS).  </b2>
- <b2> DevOps & Continuity: Deployment Slots, Auto-scaling Rules.  </b2>
- <b2> Security: App Service Authentication. </b2>
</b2>


<h2>Architecture Highlights:</h2>

- <b2> DNS Resolution & Namespace Management: Configured a DNS hierarchy to ensure internal and external resources could communicate via human-readable hostnames. </b2>
  - <b2> Validation: Verified the "A-Record" mapping using nslookup in PowerShell to ensure the DNS zone correctly pointed to the Load Balancer IP. </b2>
- <b2> High-Availability Load Balancing (IaaS): To prevent single points of failure, an Azure Load Balancer was deployed to manage traffic across multiple Web Servers. </b2>
  - <b2> Health Monitoring: Implemented TCP Health Probes to monitor the heartbeat of backend instances. </b2>
  - <b2> Traffic Distribution: Configured rules to balance port 80 traffic across the backend pool. </b2>
  - <b2> Verification: Confirmed the Healthy status of all nodes in the Load Balancer dashboard and verified traffic was successfully served. </b2>
  <p align="center">
    <img width="960" height="437" alt="5c - load balancer insights showing healthy servers" src="https://github.com/user-attachments/assets/9fc03cec-b9cc-46c1-88b1-bd62d05b28c0" />
      <br />
    Load balancer insights showing the backend pool of healthy servers
    <br />
  </p>


- <b2> Scalable Web Apps & Auto-scaling (PaaS): Configured Autoscale Rules in Azure App Service plan based on CPU metrics to ensure the application automatically adds capacity during traffic spikes and reduces it during downtime to save costs. </b2>
- <b2> Zero-Downtime Deployment: Utilized deployments, configuring a Staging slot for testing, then performed a Swap operation to move the app into Production. </b2>
  <p align="center">
    <img width="960" height="511" alt="8d - regular app slot vs second app slot" src="https://github.com/user-attachments/assets/bc570c0e-8d40-47aa-97b8-b56fc7680a35" />
      <br />
    Web app production slot vs staging slot (pre swap)
    <br />
  </p>
  <p align="center">
    <img width="960" height="530" alt="8d - s configure swap to swap production web app with second slot web app" src="https://github.com/user-attachments/assets/9f91befd-5e6d-40e3-9ccc-2b00f1c70515" />
      <br />
    swap action configuration
    <br />
  </p>
  <p align="center">
    <img width="960" height="511" alt="8d - s swap successfully configured" src="https://github.com/user-attachments/assets/aabce591-e34d-426a-815c-7830add70d1a" />
      <br />
    Web app production slot vs staging slot (post swap)
    <br />
  </p>
- <b2> Identity-Based Security Exploration: Explored the integration of Authentication/Authorization at the App Service level. This involves an identity provider such as Microsoft Entra ID or Google and App Registrations to ensure only authorized users can access the web interface. </b2>

<h2>Lesson Learned:</h2>

- <b2> PaaS vs IaaS: While Load Balancers offer great control for VMs, App Services provide a much faster time to market with built-in features like slots. </b2>
- <b2> Importance of Probes: Discovered that a Load Balancer is only as smart as its Health Probe. Properly tuning the frequency and threshold is vital for high availability. </b2>
- <b2> Predictive Scaling: Learned how to properly balance Autoscale (cool down) periods to prevent the system from scaling in/out too rapidly. </b2>
- <b2> DNS Propagation: Testing via Private DNS is a critical step for validating infrastructure before a domain is publicly registered. </b2>
</b2>

<h2>Summary</h2>
This project bridges the gap between traditional networking and modern cloud-native deployment. Successfully implementing Load Balancers, DNS zones, and App Service Swaps demonstrates the ability to build, secure, and scale an enterprise-level web environment in Azure. <br />

For a detailed breakdown of the technical implementation, specific configurations, and in-depth analysis, please refer to the [Full Project Report](https://github.com/TaiwoG1/AzureWebArchitecture/blob/main/Azure_DNS_Web%20Servers_Load_Balancers_and_App_Servers_Web_apps.pdf) <br />

