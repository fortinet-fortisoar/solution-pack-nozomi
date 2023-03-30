| [Home](../README.md) |
|--------------------------------------------|

# Usage

Refer to [Simulate Scenario documentation](https://github.com/fortinet-fortisoar/solution-pack-soc-simulator/blob/develop/docs/usage.md) to understand how to simulate and reset scenarios.

To understand the process FortiSOAR follows to respond to **Nozomi Networks Central Management Console**, we have included a scenario &mdash; `Nozomi Networks Central Management Console Scenario` with this solution pack. 

Refer to the section `Nozomi Networks Central Management Console` to understand how this solution pack automation addresses your needs.

# Nozomi Networks Central Management Console

### Step to be followed after installing SP:

1. Run the playbook - **MITRE ATT&CK > Fetch Latest Data** on ICS Configuration of MITRE Connector from Playbook Collection - `00 - Use Case - Asset Management`  to get the Tactics, Techniques, Sub-techniques, Mitigations, Groups and Software.

## Simulation mode

The simulation mode has some sample data that helps you get a better understanding of how the solution pack functions. Following steps help you use the solution pack with some included sample data.

- Browse to **Simulations** > **Nozomi Networks Central Management Console Scenario** scenario and click Simulate Scenario.
- List of Records gets created.
    - CVEs:
        - CVE-2022-0847, CVE-2021-4034, CVE-2016-8562, CVE-2017-7269, CVE-2022-32296, CVE-2022-28356, CVE-2022-1734, CVE-2022-1199, CVE-2022-32205, CVE-2019-1125.
    - ICS Advisory:
        - ICSA-23-075-01 - Siemens SCALANCE, RUGGEDCOM Third-Party
        - ICSA-22-167-16 - Siemens SCALANCE LPE 4903 and SINUMERIK Edge
        - ICSA-22-167-09 - Siemens SCALANCE LPE9403 Third-Party Vulnerabilities
        - ICSA-16-327-01 - Siemens SIMATIC CP 1543-1 (Update A)
        - ICSMA-17-215-01 - Siemens Molecular Imaging Vulnerabilities
    - KEV Alert:
        - IICSA-23-075-01 - Siemens
        - ICSA-22-167-16 - Siemens
        - ICSA-22-167-09 - Siemens
        - ICSMA-17-215-01 - Siemens
        - ICSA-16-327-01 - Siemens
    - Alert:
        - Inactive protocol OFF
    
On Creation of alert (source Nozomi Network Central Management Console) following things happens:

- At Alert Level
    - Appliance Details are represented in comments.
    - Alerts get correlated with Asset as per Source and Destination MAC Address. 
    > **Note**: Is Asset is not found for any MAC addresses, then asset gets created for same with MAC Address.
    - According to the `Asset ID` and `Vendor` for affected assets, alerts gets correlated with CVEs and ICS Advisory, and comments are provided for each.
    - According to the Source and Destination IP of an Alert, nodes are fetched from Nozomi CMC. Each Node are received as a new asset if fouund in Nozomi CMC.
    - Recent network activity are fetched from Nozomi CMC as an Event for Alert's Source IP and Destination IP
- At Asset Level
    - Appliance Details are represented in comments.
    - Assets gets associated with CVEs pulled from Nozomi CMC based on their Asset ID and, with ICS and KEV Alerts if any discovered in the environment.
    - According to the asset's vendor, it gets correlated with any existing CVEs, ICS advisories, and KEV Alerts is any present in the environment.
    - Asset get connected with their Nodes Asset if found any for their correlated alert Source or Destination IPs.
> **Note**: The relevant module comments contain a complete list of the correlation details.

## Production mode

- To use this solution pack in a production environment, change the value of the global variable `Demo_mode` to `false`.
- Playbook Collections **02 - Use Case - ICS Advisory and CVEs** and **02 - Use Case - KEV Alert**, mark all of the playbooks that are available as active.