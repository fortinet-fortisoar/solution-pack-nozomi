| [Home](../README.md) |
|----------------------|

# Installation

1. To install a solution pack, click **Content Hub** > **Discover**.
2. From the list of solution pack that appears, search for and select **Nozomi Networks Central Management Console**.
3. Click the **Nozomi Networks Central Management Console** solution pack card.
4. Click **Install** on the lower part of the screen to begin the installation.

## Prerequisites

The **Nozomi Networks Central Management Console** solution pack depends on the following solution packs that are installed automatically during the installation process &ndash; if not already installed.

| Solution Pack Name            | Version         | Purpose                                                             |
|:------------------------------|:----------------|:--------------------------------------------------------------------|
| SOAR Framework                | v2.1.0 or later | Required for Alerts, Assets, Incident Response modules              |
| SOC Simulator                 | v1.0.2 or later | Required for Scenario Module and SOC Simulator connector            |
| OT - Asset Management         | v1.0.0 or later | Required for Asset Modules and playbooks.                           |
| OT - Vulnerability Management | v1.0.0 or later | Required for CVEs, ICS Advisory and KEV Alert Module and playbooks. |

# Configuration

For the optimal performance of **Nozomi Networks Central Management Console** solution pack, you can install and configure the following connectors:

- **File Content Extraction** connectors to read file and extract text. To configure and use the File Content Extraction connector, refer to [Configuring File Content Extraction](https://docs.fortinet.com/fortisoar/connectors/filecontentextraction)

- **Fortinet FortiEDR** connectors to Isolate collectors. To configure and use the Fortinet FortiEDR connector, refer to [Configuring Fortinet FortiEDR](https://docs.fortinet.com/fortisoar/connectors/fortiedr)

- **Fortinet FortiDeceptor** connectors to Deploy Decoy on asset. To configure and use the Fortinet FortiDeceptor connector, refer to [Configuring Fortinet FortiDeceptor](https://docs.fortinet.com/fortisoar/connectors/fortideceptor)

- **Nozomi Networks Central Management Console** connector to fetch alert, assets, nodes, links and CVEs from Nozomi. To configure and use the Nozomi Networks Central Management Console connector, refer to [Configuring Nozomi Networks Central Management Console](https://docs.fortinet.com/fortisoar/connectors/nozomicmc)

- **ServiceNow** connectors to raise tickets. To configure and use the ServiceNow connector, refer to [Configuring ServiceNow](https://docs.fortinet.com/fortisoar/connectors/servicenow-v2-0-1)

| [Usage](./docs/usage.md) | [Contents](./docs/contents.md) |
|--------------------------|--------------------------------|
