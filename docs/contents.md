| [Home](../README.md) |
|----------------------|

# Contents

The **Nozomi Networks Central Management Console** solution pack contains the following resources.

## Connectors

| Name                                       | Version         | Description                                                                                                                                                                                                                                                                                                               |
|:-------------------------------------------|:----------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| File Content Extraction                    | v1.0.3 or later | Utility to extract text, artifacts, and metadata from almost any file. Internet connectivity is required for the connector to download dependent packages.                                                                                                                                                                |
| Fortinet FortiEDR                          | v1.3.0 or later | FortiEDR protects endpoints pre and post-infection, stops data breaches in real-time, and automatically orchestrates incident investigation and response. This connector facilitates automated operations related to events, forensics, and collectors.                                                                |
| Fortinet FortiDeceptor                     | v1.0.0 or later | FortiDeceptor is a deception-based Breach Protection Deceive, Expose, and Eliminate External and Internal Threats.                                                                                                                                                                                                         |
| Nozomi Networks Central Management Console | v1.0.0 or later | The Nozomi Networks Central Management Console (CMC) consolidates OT and IoT risk monitoring and visibility from Guardian, physical or virtual, appliances across your distributed sites. It integrates with your IT security infrastructure for streamlined workflows and faster response to threats and anomalies. |
| ServiceNow                                 | v3.2.0 or later | ServiceNow connector provides functionality to create, read, update, and delete records of table and catalog type                                                                                                                                                                                                         |

## Scenario Record Set

| Name                                                | Description                                                                                                                                      |
|:----------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------|
| Nozomi Networks Central Management Console Scenario | This Scenario adds 10 CVEs, 5 ICS Advisory, 5 KEV Alert and "Inactive protocol OFF" Alert. These data can be used to understand Nozomi Use Case. |

## Playbook Collection

### 02 - Use Case - Nozomi CMC

| Playbook Name                            | Description                                                                                                                      |
|:-----------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------|
| Scenario - Create Nozomi Alert           | Playbook generated sample CVEs, ICS Advisory, KEV Alert and Alert to understand Nozomi Use Case.                                 |
| > Create Scenario KEV Alert              | Playbook creates scenario KEV Alert.                                                                                             |
| Get Alert Details                        | Playbook execute post alert creation(source Nozomi CMC) and get Appliance Details, Assets, Node, Links and CVEs from Nozomi CMC. |
| > Get Appliance Detail                   | Playbook gets Appliance detail from Nozomi CMC by Appliance ID.                                                                  |
| > Get Assets Details                     | Playbook fetches assets from Nozomi CMC based on Alert's Source and Destination MAC Address.                                     |
| > Create Asset Record                    | Playbook create Asset Record and fetch CVEs from Nozomi by Asset ID.                                                             |
| > Get Node CVEs By Vendor Or By Asset ID | Playbook fetches CVEs from Nozomi CMC by vendor or by asset id.                                                                  |
| On Asset Creation                        | On Asset Creation (from Nozomi CMC) link it to existing KEV Alert (if any for same vendor).                                      |
| > Get Node CVEs                          | Playbook fetches CVEs from Nozomi CMC by Alert's assets vendor.                                                                  |
| > Get Nodes Of Alert IPs                 | Playbook get nodes from Nozomi CMC for Assets IP Address.                                                                        |
| > Get Links                              | Playbook get links from Nozomi CMC on the basis of Alert's Source IP and Destination IP.                                         |
| Get All Assets                           | Playbook retrieves all the assets from Nozomi CMC.                                                                               |
| Deploy Decoy And Isolate Assets          | This Playbook will deploy FortiDECEPTOR decoy on assets, isolates assets in FortiEDR and raise ticket in Service Now.            |

>**WARNING:** We recommend that you clone these playbooks before customizing to avoid loss of information while upgrading the solution pack.

| [Installation](./docs/setup.md#installation) | [Configuration](./docs/setup.md#configuration) | [Usage](./docs/usage.md) |
|----------------------------------------------|------------------------------------------------|--------------------------|
