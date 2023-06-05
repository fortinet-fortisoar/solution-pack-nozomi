| [Home](../README.md) |
|----------------------|

# Usage

Refer to [Simulate Scenario documentation](https://github.com/fortinet-fortisoar/solution-pack-soc-simulator/blob/develop/docs/usage.md) to understand how to simulate and reset scenarios.

To understand the process FortiSOAR follows to respond to alerts from **Nozomi Networks Central Management Console**, we have included a scenario &mdash; *Nozomi Networks Central Management Console* with this solution pack. 

Refer to the section *Nozomi Networks Central Management Console* to understand how this solution pack's automation addresses your needs.

# Nozomi Networks Central Management Console

## After Installation

1. Run the playbook - **MITRE ATT&CK > Fetch Latest Data** on ICS configuration of MITRE Connector from Playbook Collection - **00 - Use Case - Asset Management**  to get the Tactics, Techniques, Sub-techniques, Mitigation actions, Groups, and Software.

## Simulation mode

The simulation mode has some sample data that helps you get a better understanding of how the solution pack functions. The following steps help you use the solution pack with some included sample data.

- Browse to **Simulations** > **Nozomi Networks Central Management Console Scenario** scenario and click **Simulate Scenari**o.
- The following list of records is created.
    - **CVEs**:
        - CVE-2022-0847, CVE-2021-4034, CVE-2016-8562, CVE-2017-7269, CVE-2022-32296, CVE-2022-28356, CVE-2022-1734, CVE-2022-1199, CVE-2022-32205, CVE-2019-1125.
    - **ICS Advisory**:
        - ICSA-23-075-01 - Siemens SCALANCE, RUGGEDCOM Third-Party
        - ICSA-22-167-16 - Siemens SCALANCE LPE 4903 and SINUMERIK Edge
        - ICSA-22-167-09 - Siemens SCALANCE LPE9403 Third-Party Vulnerabilities
        - ICSA-16-327-01 - Siemens SIMATIC CP 1543-1 (Update A)
        - ICSMA-17-215-01 - Siemens Molecular Imaging Vulnerabilities
    - **KEV Alert**:
        - IICSA-23-075-01 - Siemens
        - ICSA-22-167-16 - Siemens
        - ICSA-22-167-09 - Siemens
        - ICSMA-17-215-01 - Siemens
        - ICSA-16-327-01 - Siemens
    - **Alert**:
        - Inactive protocol OFF
    
On creation of an alert in FortiSOAR from *Nozomi Network Central Management Console* following actions are taken:

- **At Alert Level**

    - Appliance details are represented in comments

    - Alerts are correlated with assets as per source and destination MAC addresses

        > **Note**: If an asset is not found for any MAC addresses, the asset is created for the same with MAC Address.

    - According to the `Asset ID` and `Vendor` for affected assets, alerts are correlated with CVEs and ICS Advisory, and comments are provided for each

    - According to the Source and Destination IP of an alert, nodes are fetched from Nozomi CMC. Each node is received as a new asset if found in Nozomi CMC.

    - Recent network activity is fetched from Nozomi CMC as an event for the alert's Source IP and Destination IP addresses

- **At Asset Level**

    - Appliance Details are represented in comments.

    - Assets are associated with any CVEs pulled from Nozomi CMC based on their Asset ID and, with ICS and KEV alerts discovered in the environment

    - According to the asset's vendor, it is correlated with any existing CVEs, ICS advisories, and KEV Alerts present in the environment.

    - Assets are connected with any of their node assets found for their correlated alert Source or Destination IP addresses

        > **Note**: The relevant module comments contain a complete list of the correlation details.

## Production mode

- To use this solution pack in a production environment, change the value of the global variable `Demo_mode` to `false`.

- Mark all the playbooks under the collections **02 - Use Case - ICS Advisory and CVEs** and **02 - Use Case - KEV Alert** as active.

| [Installation](./setup.md#installation) | [Configuration](./setup.md#configuration) | [Contents](./contents.md) |
|-----------------------------------------|-------------------------------------------|---------------------------|
