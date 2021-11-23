# How To
### If you want to learn about Workflows, here are educational videos: [Part 1](https://youtu.be/VqTixS0G-nw), [Part 2](https://youtu.be/xUcHkxeRBmo), [Part 3](https://youtu.be/LNrJCJW0EGI), [Part 4](https://youtu.be/VrHTZZTYYno)

### Workflows are available from XMC version 8.1.5 as beta feature. Fully supported since XMC version 8.2 GA and XIQ Site Engine
* Import the sctript = Open the web GUI -> Tasks -> Workflow -> Import...

# XIQ Site Engine (XMC) Reporting Workflows
| Workflow name | Description | Comment | Version |
| ------------- | ----------- | ------- | ------- |
|[Aggregated report Device Down](xwf/Aggregated_report_Device_Down-8.5.1.60v20.xwf?raw=true)|This workflow creates aggregated report over the time. Instead of 300 emails if 300 devices go down, you will get one email with a list of 300 devices.|Create Alarm for Device Down based on contact lost and as action assign this workflow. You can define the aggregation time in minutes in the workflow Input. Define email recipients.|8.5.1.60v20|
|[Link Aggregate Alarm](xwf/Link_Aggregate_Alarm-8.4.0.115v8.xwf?raw=true)|This workflow creates one email for each link down event. Instead of 2 emails if the link goes down, you will get one email with all link details.|Create Alarm for Link Down based on selected trap (you can copy or modify the original alarm) and as action assign this workflow. Define email recipients.|8.4.0.115v8|
|[ERS inventory](xwf/ERS_Devices_Report-8.4.2.30v111.xwf?raw=true)|This workflow creates one email with CSV file attached. All ERS devices are there with IP, serial numbers, and many details.|Select ERS devices. Check your ERS devices do have defined Network OS.|8.4.2.30v111|
|[ERS port counters](xwf/ERS_por_counters_report-8.4.2.38v39.xwf?raw=true)|This workflow creates one email with CSV file attached. Ports with the defined property above the defined threshold are in the list.|Select ERS devices. Define property (e.g. Dropped on no resources), define threshold (e.g. 0), define email address.|8.4.2.38v39|
|[Open ServiceNow Ticket](xwf/Open_ServiceNow_Ticket-8.4.2.38v3.xwf?raw=true)|This workflow creates ticket in ServiceNow through the API call based on the alarm.|Define variables for ServiceNow (Instance, credentials, queue, priority). Create an alarm to trigger this workflow.|8.4.2.38v3|
|[Aggregated Report Alarm History](xwf/Aggregated_Report_Alarm_History-8.4.3.24v28.xwf?raw=true)|This workflow creates an aggregated CSV report of alarm history. Columns in the CSV file are AlarmName, Source, Subcomponent, Occurrence.|The workflow can be executed or scheduled. You can define the aggregation time in seconds in the workflow Input. Define email recipients.|8.4.3.24v28|
|[Universal Alarm Email List](xwf/Universal_Alarm_Disbritution_List-8.4.4.26v1.xwf?raw=true)|This workflow sends an email to the recipient based on sysLocation. The translation from sysLocation to email address is defined in the CSV file. The first column in the CSV file is sysLocation. The second column is EmailAddress.|The workflow must be executed by an alarm. You can define the location of the CSV file.|8.4.4.26v1|
|[Report configuration changes by email](xwf/Report_Configuration_Changes-8.5.2.6v10.xwf?raw=true)|This workflow sends an email to the recipient with the configuration changes detected. It compares last two archived configurations.|The workflow can be executed by an [alarm](xwf/Report_Configuration_Changes.png). Define the email recipients.|8.4.4.26v1|
|[Extended Alarm Information to Email](xwf/Extended_Alarm_information_to_Email-8.5.3.66v6.xwf?raw=true)|The workflow contains the dictionary of CLI commands to be executed based on alarm name. The workflow determines the alarm name and based on the information in the dictionary the set of CLI commands are executed. The result is then send to email recipients.|The workflow must be executed by an alarm. Modify the dictionary in the workflow. Define the email recipients.|8.5.3.66v6|
|[Report Congestions](xwf/GetCongestion-8.5.5.30v67.xwf?raw=true)|The Workflow checks congestions on ports through SNMP and if congestion is detected then the email report is generated.|Define devices inside of the activity and threshold. Define the email recipients.|8.5.5.30v67|
|[XIQ-SE licensing calculation](xwf/XIQ-SE_Licensing_calculation-v98.xwf?raw=true)|The Workflow reports number of Pilot and Navigator licenses required by ExtremeCloud IQ - Site Engine.|Define the email recipients.|v98|

# XIQ Site Engine (XMC) Troubleshooting Workflows
| Workflow name | Description | Comment | Version |
| ------------- | ----------- | ------- | ------- |
|[Uptime and Tech Support](xwf/Uptime_and_Tech_Support-8.4.0.115v87.xwf?raw=true)|Checks the uptime of each device (families: Wireless Controller, VSP, Summit Series, Catalyst, Extreme Access Series, VDX). If the uptime is lower then configured value and the device is not in maintenance then the workflow gathers tech support information and send an email.|Add XMC to devices with proper CLI credentials. Configure variables and email destination.|8.4.0.115v87|
|[Gather Show Support](xwf/Gather_Show_Support-8.4.3.24v29.xwf?raw=true)|Workflow gathers show support information from devices (families: Wireless Controller, VSP, Summit Series, Catalyst, Extreme Access Series, VDX, SLX). The workflow should be executed by alarm or with right-click on the device. Workflow generates an email with tech support attached.|Configure the email destination. Create an Alarm to execute this workflow. Add XMC to the database with CLI credentials or define XMC credentials in variables.|8.4.3.24v29|

# XIQ Site Engine (XMC) Provisioning Workflows
| Workflow name | Description | Comment | Version |
| ------------- | ----------- | ------- | ------- |
|[Export Site Structure](xwf/Export_Sites-8.4.1.24v1.xwf?raw=true)|Exports Site structure to the file or email.|Inputs: FileName including full path, the email address is optional.|8.4.1.24v1|
|[Import Site Structure](xwf/Import_Sites-8.2.5.50v2.xwf?raw=true)|Automatically creates sites and subsites based on input file|Inputs: [File with site names](xwf/Import_Sites_Sites2Create.txt?raw=true). Parent site must exist.|8.2.5.50v2|
|[Import Devices](xwf/Import_Devices-8.4.4.26v6.xwf?raw=true)|Import devices to the database based on input file|Inputs: [File with devices](xwf/Import_Devices.txt?raw=true). The file contains IP (IPv4/IPv6), Nickname, Site, Profile. The workflow finishes quickly, added devices will start to appear in the XMC sequentially.|8.4.4.26v6|
|[Import VLANs](xwf/Import_VLANs_to_Site-8.3.0.106v3.xwf?raw=true)|Import VLANs to the Site based on input file|Inputs: [File with VLANs](xwf/Import_VLANs_to_Site.txt?raw=true). The file contains VlanID, VlanName. Chose method ADD (fails if the VLAN exists) or REPLACE (if does not exist then it creates the VLAN). Specify the Site.|8.3.0.106v3|
|[Import VLANs to Sites](xwf/Import_VLANs_to_Sites-8.5.3.66v52.xwf?raw=true)|Import VLANs to Sites based on input CSV text|Inputs: CSV formated text with SiteName, VlanID, VlanName. Chose action: Check only (generates report), Add non-existing (Adds only non-existing VLANs) or Modify & Add (Renames existing VLANs and Adds non-existing VLANs).|8.5.3.66v52|
|[Import VRFs and VLANs and Services from VSP](xwf/Import_VLANs_and_Services_from_VSP-8.4.0.107v37.xwf?raw=true)|Workflow reads VRFs, VLANs, L2VSN, L3VSN from VSP, and import it to Service Defintions.|Inputs: Service Application, VSP device, or XA. The Service Definition is determined automatically = VSP must be assigned to the site with Service Definition.|8.4.0.107v37|
|[Import End-Systems to XCA](xwf/Import_CSV_to_XCA_ES_group-8.3.0.111v4.xwf?raw=true)|This workflow reads the CSV file with MACs and descriptions. The workflow injects the content of the CSV file to the end-system group in Extreme Cloud Appliance through the API. The XCA must be in XMC and must have CLI credentials defined. The end-system group must exist. The maximum number of entries in one run is 100 for XCA version 04.36.02.0014 |Inputs: [File with End-systems](xwf/Import_CSV_to_XCA_ES_group.txt?raw=true). The file contains MAC, description.|8.3.0.111v4|
|[Import L2VSNs to XMC](xwf/Import_L2VSNs-8.3.1.9v7.xwf?raw=true)|Imports VLANs and L2VSNs from file to XMC Service Definitions and Service Applications. If Service Definition does not exist then it is created. If Service Application does not exist then it is created. If Vlan ID exists then it is updated. If NSI exists then it is updated. The goal is: You do not need to manually create each VLAN and ISID in XMC.|Inputs: [File with Services](xwf/Import_L2VSNs_Services2Create.txt?raw=true)|8.3.1.9v7|
|[Create Device Groups from Sites](xwf/Create_Device_Groups_from_Sites-8.4.0.115v25.xwf?raw=true)|Based on the Site structure user groups will be created. Workflow stops if there is a name conflict: if a group with the same name already exists. Backup of the XMC is strongly recommended before the workflow execution.|Name of each site must be unique. A restart of XMC is mandatory after the workflow execution.|8.4.0.115v25|
|[Change EXOS policy Rule model](xwf/Change_EXOS_policy_model-8.4.3.10v29.xwf?raw=true)|This workflow address incompatibility of EXOS 30.5 with Policy Manager in XMC 8.4 and older. [KB article](https://extremeportal.force.com/ExtrArticleDetail?an=000057615&q=xmc-Policy-enforce-is-failing-to-EXOS-switches-running-30-5-x-15-firmware-after-upgrading-to-v8-4-x). The workflow can be executed through ZTP+ process or manually.|CLI access must work, Policy domain must be assigned. [ZTP+ settings](xwf/Change_EXOS_policy_mode_ZTP_configuration.PNG)|8.4.3.10v29|
|[ZTP+ Remove Redundant IPs](xwf/Remove_redundant_IPs-8.4.2.38v1.xwf?raw=true)|During the ZTP+ process the switch can learn multip IPs from the DHCP server. This workflow can be executed after the EXOS device is onboarded and it does remove IPs from EXOS not registered in XMC.|Configure Site Actions to execute this workflow as part of ZTP+ process.|8.4.2.38v1|
|[ZTP+ Change the persona to VOSS](xwf/Change_persona_to_VOSS-8.5.4.23v17.xwf?raw=true)|Workflow changes persona to VOSS from EXOS. Removes the device from the XMC and allow ZTP+ to happen. Tested with 5520/5420 platform.|Configure the VOSS firmware file name for the right platform, TFTP directory with the firmware. Configure Site Actions to execute this workflow as part of ZTP+ process.|8.5.4.23v17|
|[ZTP+ Change the persona to EXOS](xwf/Change_persona_to_EXOS-21.4.10.80v35.xwf?raw=true)|Workflow changes persona from VOSS to EXOS. Removes the device from the XMC and allow ZTP+ to happen. Tested with 5520 platform.|Configure the EXOS firmware file name, TFTP directory with the firmware.|21.4.10.80v35|
|[Update PVI from CSV](xwf/Update_PVI_from_CSV_files-8.5.1.60v6.xwf?raw=true)|Workflow reads VLANs and NSIs from CSV files and updates the Policy Vlan Islands in the specified Policy Domain.|Inputs:[PVI_NSIs.csv](xwf/Update_PVI_from_CSV_files-NSI.csv?raw=true),[PVI_VLANs.csv](xwf/Update_PVI_from_CSV_files-VLAN.csv?raw=true), Policy domain, Force unlock.|8.5.1.60v6|
|[Update PVI](xwf/Update_PVI-8.5.1.60v8.xwf?raw=true)|Workflow updates th Policy VLAN Islands in the specified Policy Domain based on information provided in the input form.|Inputs:PVI NSIs, PVI VLANs, Policy domain, Force unlock.|8.5.1.60v8|
|[Delete VLANs from Policy Domain](xwf/Delete_VLANs_from_Policy_Domain-8.5.1.60v6.xwf?raw=true)|Workflow deletes VLANs from the policy domain without deleting those VLANs from switches. It is useful for migration to PVI.|Inputs:Policy domain, Comma separated list of VLANs, Confirmation.|8.5.1.60v6|
|[ZTP+ Adding Commands per Port Template](xwf/ZTP_adding_commands_per_Port_Template-8.5.1.60v4.xwf?raw=true)|Workflow executes commands to update the EXOS configuration. Define commands to execute per Port Template. The workflow replaces "{}" with the port.|Inputs:CLI Commands for each port template, CLI Commands for switch.|8.5.1.60v4|
|[Clear Nicknames](xwf/Clear_Nicknames-8.5.1.60v6.xwf?raw=true)|Workflow removes Nicknames from all devices in the database except those without sysName (e.g. ICMP monitored). If the Nickname is not present then XMC display actual sysName. |Inputs:Confirm the action.|8.5.1.60v6|
|[Onboard VSP](xwf/Onboard_VSP-21.9.10.90v81.xwf?raw=true)|This workflow allows for automated onboarding of VSP Edge and is designed to be assigned to a Site, under Action tab, as a Custom Configuration Task. The workflow inputs can be set on the workflow itself (if all VSPs will be onboarded to the same Site) or can be set to ${&lt;site-custom-variable&gt;} where the appropriate variable has been set under the Site Custom Variables tab as category "Site", site the site itself (not Global), and type "String". The workflow inputs will determine whether the onboarded VSP is NAC enabled (this will both configure the VSP switch and add the VSP switch to the correct XMC AccessControl Engine Group) and whether the VSP is made into a DVR Leaf node. Auto-sense configuration is also applied if provided and any additional CLI config commands can also be applied at the same time. Activation of DVR Leaf mode, will trigger a VSP switch reboot at the end of the workflow.|Inputs: DVR Leaf enable/disable, NAC enable/disable, NAC Engine Group name, RADIUS attributes template, RADIUS shared secret, Location Group, Auto-sense voice I-SID/VLAN, Auto-sense Data I-SID, Auto-sense ISIS Authentication key, Auto-sense FA Authentication key, Additional CLI commands|21.9.10.90v81|



# XIQ Site Engine (XMC) daily job Workflows
| Workflow name | Description | Comment | Version |
| ------------- | ----------- | ------- | ------- |
|[Send System Time by Email](xwf/Send_SystemTime_by_Email-8.2.1.56v22.xwf?raw=true)|Gather system time from a group of EXOS devices sequentially and the aggregated result is sent by email.|Configure the email recipients before executing.|8.2.1.56v22|
|[Update Device Notes - Group Membership](xwf/Update_Device_Notes-Group_Membership-8.2.4.24v13.xwf?raw=true)|The workflow does modify device property to reflect groups the device belongs to.|Modify the Inputs to define what property you want to modify and what prefix you want to use. Run the workflow and save it as task. Schedule the task for periodic execution.|8.2.4.24v13|
|[Assign Device to User Device Group based on SysObjectID](xwf/Assign_Device_to_UserGroup-8.2.5.50v4.xwf?raw=true)|Automatically assigns the device to the user device group based on SysObjectID. All devices of the same type will be in the same user device group.|Inputs:[File with mapping](xwf/Assign_Device_to_UserGroup_SysObjectID2Group.csv?raw=true), SOAP credentials. The user device group must exist. Workflow can be executed automatically by Alarm (new device added). Workflow can be executed manually or scheduled.|8.2.5.50v4|
|[Assign Device to User Device Group based on site](xwf/Assign_the_Device_to_User_Device_Group-8.4.0.115v3.xwf=true)|Automatically assigns the device to the user device group based on site.|Define SOAP credentials. User device group must exist (Use workflow "Create Device Groups from Sites" to create the user group structure.). Workflow can be executed manually or scheduled or part of the site actions. Multiple devices can be processed by one run.|8.4.0.115v3|
|[Synchronize Vlans on Catalyst](xwf/Synchronize_Vlans_on_Catalyst-8.4.3.24v19.xwf?raw=true)|This workflow creates VLANs on the Cisco Catalyst switch based on Site and Services VLAN configuration. The workflow deletes VLANs from the switch if the VLAN does not exist in the Site nor in the Services definition. The workflow renames VLAN name to match the Site or Services.|If a change has been made, the event is generated and configuration is saved.|8.4.3.24v19|
|[Synchronize Vlans on ERS](xwf/Synchronize_Vlans_on_ERS-8.4.1.23v20.xwf?raw=true)|This workflow creates VLANs on the ERS switch based on a combination of Site and Services VLAN configuration. The workflow deletes VLANs from the switch if the VLAN does not exist in the Site nor in the Services definition. The workflow renames VLAN name to match the Site or Services.|If a change has been made, the event is generated.|8.4.1.23v20|
|[Synchronize Vlans on HPE](xwf/Synchronize_Vlans_on_HP-8.4.3.24v2.xwf?raw=true)|This workflow creates VLANs on the HPE switch based on Site and Services VLAN configuration. The workflow deletes VLANs from the switch if the VLAN does not exist in the Site nor the Services definition. The workflow renames VLAN name to match the Site or Services.|If a change has been made, the event is generated and configuration is saved.|8.4.3.24v2|
|[Synchronize Vlans on ISW](xwf/Synchronize_Vlans_on_ISW-8.4.3.24v6.xwf?raw=true)|This workflow creates VLANs on the ISW switch based on a combination of Site and Services VLAN configuration. The workflow deletes VLANs from the switch if the VLAN does not exist in the Site nor in the Services definition. The workflow renames VLAN name to match the Site or Services.|If a change has been made, the event is generated.|8.4.3.24v6|
|[Disable unused ports](xwf/Disable_unused_ports-8.4.4.26v66.xwf?raw=true)|If the port is unused for more than X days then the port is set to Admin-Down state and ifAlias is configured. On EXOS and BOSS and FastPath and ISW devices, there is an option to save the configuration.|Variable PortDescription defines ifAlias prefix. Custom Inputs: Topology roles delimited by comma (XMC version 8.3 the roles are numbers starting from 0, XMC version 8.4 roles are "L2 Leaf,L2 Access,...", how many days should be the port down before workflow takes the action if you do want to save the changed configuration. What sites and subsites you want this workflow to execute. You can schedule the workflow execution in task scheduler.|8.4.4.26v66|
|[Refresh Neighbor Devices](xwf/Refresh_Neighbor_Devices-8.2.4.55v2.xwf?raw=true)|This workflow checks neighbor devices based on XMC link database and executes refresh of each neighbor. If the device goes down or up then the map is automatically updated.|Create Status Change Alarm and for both contact lost and contact established add action run task with this workflow. |8.2.4.55v2|
|[Execute CLI commands in Enable mode](xwf/CLI_Command_Execute_with_Enable-8.5.0.169v11.xwf?raw=true)|This workflow automatically enters the enable mode and passes the enable password. Then it executes user-defined commands. Both Single and Multi-device execution is supported.| The enable password must be configured in the CLI credentials. The Network OS must be one of the defined in the list.|8.5.0.169v11|
|[Import APs from XIQ](xwf/Process_New_XIQ_Devices-8.5.0.169v158.xwf?raw=true)|This workflow automatically adds APs from Extreme Cloud IQ to XMC and to ExtremeControl.|Update the Bearer Token, client secret, client-id, redirect-uri, and ownerid in the curl_cmd variable to match your developer credentials, bearer token from XIQ, and VIQ ID.|8.5.0.169v158|


# XIQ Site Engine (XMC) NAC-related Workflows
| Workflow name | Description | Comment | Version |
| ------------- | ----------- | ------- | ------- |
|[Delete end-system from ExtremeControl](xwf/GDPR-Delete_End-System-8.2.4.41v6.xwf?raw=true)|This workflow deletes End-System with specified MAC from the database. Can help with the implementation of GDPR "Right to be forgotten".|Various MAC address formats are accepted: lowercase, uppercase, dot delimited, colon-delimited, dash delimited, not delimited|8.2.4.41v6|
|[Delete from ExtremeControl](xwf/GDPR-Delete-8.2.4.41v4.xwf?raw=true)|This workflow deletes End-System with specified MAC or Username from the database. Can help with the implementation of GDPR "Right to be forgotten".|Various MAC address formats are accepted: lowercase, uppercase, dot delimited, colon-delimited, dash delimited, not delimited. The domain is not mandatory in the username.|8.2.4.41v4|
|[Investigate End-System History](xwf/Investigate_End-System_history-8.2.5.50v48.xwf?raw=true)|Workflow generates an email with table of end-system events based on defined criteria.|Input: MAC or Username, Date range. Define email recipients before use. The InstallDirectory is referring to the XMC installation path.|8.2.5.50v48|
|[Remove all End-Systems from group](xwf/Clear_End-Systems_in_the_group-8.3.1.9v12.xwf?raw=true)|This workflow removes all end-systems from the end-system group. It can be scheduled to execute periodically.|Define an end-system group in variable "EndSystemGroup" default end-system group: "Access Expired".|8.3.1.9v12|
|[Import credentials from MySQL to local repository](xwf/MySQL-2-LocalRepository-8.4.0.115v13.xwf?raw=true)|Workflow connects to an external MySQL server and read usernames and passwords. These are then injected to the local password repository. Can be executed once, can be scheduled.|Input: SQL server, SQL username, SQL password, SQL database, SQL table, Column with usernames, Column with passwords.|8.4.0.115v13|
|[RFC3580 for ISW through CLI](xwf/RFC3580_for_ISW_and_MACauth_through_CLI-8.4.2.38v11.xwf?raw=true)|This workflow delivers missing RFC3580 feature on the ISW for Macauth. If it is mac authentication then it configures on the switch VLAN based on authorization VLAN in the radius response. The configuration is done through ssh/telnet. When the end-system is disconnected it returns the port VLAN to default.|Define disconnected PVID. Create 2 notification rules. [State Change](xwf/RFC3580_for_ISW_and_MACauth-Rule1.PNG) and [New End-System Added](xwf/RFC3580_for_ISW_and_MACauth-Rule2.PNG).|8.4.2.38v11|
|[RFC3580 for ISW through SNMP](xwf/RFC3580_for_ISW_and_MACauth_through_SNMP-8.4.2.38v2.xwf?raw=true)|This workflow delivers missing RFC3580 feature on the ISW for Macauth. If it is mac authentication then it configures on the switch VLAN based on authorization VLAN in the radius response. The configuration is done through SNMP. When the end-system is disconnected it returns the port VLAN to default.|Define disconnected PVID. Create 2 notification rules. [State Change](xwf/RFC3580_for_ISW_and_MACauth-Rule1.PNG) and [New End-System Added](xwf/RFC3580_for_ISW_and_MACauth-Rule2.PNG).|8.4.2.38v2|
|[Limit number of End-Systems with the same Username](xwf/Limit_ES_with_same_Username-8.4.2.38v2.xwf?raw=true)|The workflow reads all end-systems and process only those in Accept state. If the number of end-systems with the same name is higher than the threshold then one of the following will happen: UserName can be added to the defined User Group and all end-systems are reauthenticated. All MACs for that username are added to the defined ES group and all those end-systems are reauthenticated. Only older MACs for that username are added to the defined ES group and are reauthenticated.|Define the number of allowed end-systems with the same username, action what will happen, group to add MACs/Username. Schedule the workflow execution.|8.4.2.38v2|
|[Add MAC to the Blaclist to inform user](xwf/Add_MAC_to_Blacklist_to_inform_user-8.5.0.169v6.xwf?raw=true)|This workflow adds MAC address to ES group and creates a event.|Description can be defined and end-system group can be defined.|8.5.0.169v6|
|[Report 802.1X Rejects](xwf/NAC_report_too_many_1X_Rejects-8.5.5.30v2.xwf?raw=true)|Workflow generates an email with table of User Names with too many rejects in last X hours.|Input: Number of Hours. Threshold. Email Address.|8.5.5.30v2|
|[Import FDB from ERS to NAC](xwf/Import_FDB_from_ERS_to_NAC-21.9.10.90v19.xwf?raw=true)|Workflow reads the MAC address table from ERS devices and imports those to End-System groups, creates NAC profiles and NAC rules. If duplicate MAC is seen on more VLANs then VoIP vlan makes precedence. If duplicate MAC is not seen on VoIP VLAN then the duplicate MAC is not imported.|Input: Site with VLAN names, NAC config name. VoIP VLAN ID, Name prefix|21.9.10.90v19|


# XIQ Site Engine (XMC) Workflow Combinations
| Name | Workflows | Description | How To | Version |
| ---- | --------- | ----------- | ------ | ------- |
|Add NSI to Vlan Egress = After Policy Enforcement|[Run Add NSI After Policy Enforcement](combo/AddNSIprefix/Run_Add_NSI_After_Policy_Enforcement-8.4.0.107v11.xwf?raw=true), [Add NSI prefix to vlan egress](combo/AddNSIprefix/Add_NSI_prefix_to_vlan_egress-8.3.1.9v35.xwf?raw=true)|There maybe tagged egress vlans in the policy profiles. This workflow ensures these egress vlans are mapped to proper NSI on EXOS switch. This check is executed on each reachable device in the policy domain, when the enforce is completed.|Import both workflows. The "Run Add NSI After Policy Enforcement" should be executable by [Alarm](combo/AddNSIprefix/Alarm.png). Configure the [path](combo/AddNSIprefix/WorkflowPath.png) to the "Add NSI prefix to vlan egress" workflow. [Create Alarm](combo/AddNSIprefix/AlarmDefinition.png) to execute the workflow if the policy domain is enforced. Create [topology](combo/AddNSIprefix/Topology.png) if you do not have any. Create [Service and Application](combo/AddNSIprefix/Applications.png). Assign [Topology](combo/AddNSIprefix/SiteTopology.png) to the Site. Assign [Service](combo/AddNSIprefix/SiteService.png) Definition to the Site.|8.4.0.107v11 8.3.1.9v35|
|User authenticated on domain computer|[Add MAC to Domain Computers](combo/UserAndComputer/Add_MAC_to_Domain_Computers-8.3.1.9v3.xwf?raw=true), [Clear old End-Systems in the group](combo/UserAndComputer/Clear_old_End-Systems_in_the_group-8.3.1.9v5.xwf?raw=true)|"Add MAC to Domain Computers" is executed when the computer authenticates. The MAC address is added to End-System and the timestamp is created (updated). Consequent User authentication can be combined with the condition of the End-System group. "Clear old End-Systems in the group" checks if the timestamp is older than X hours and old End-Systems are deleted from the group.|Create End-System group "Domain Computers". Create User Group [Username starts with host/](combo/UserAndComputer/UserGroup.PNG). Create notification [Domain authentication - after logoff](combo/UserAndComputer/Notification1.PNG). Create notification [Domain authentication - after boot](combo/UserAndComputer/Notification2.PNG). Configure inputs for workflows. Schedule the workflow execution to clean old end-systems from the End-Systems group. Create [NAC rule](combo/UserAndComputer/Rule.PNG)|8.3.1.9v3 8.3.1.9v5|
|IGE Governance Regime|[Governance Regime Export](combo/GovernanceEngine/Governance_Regime_Export-8.4.1.23v7.xwf?raw=true), [Governance Regime Import](combo/GovernanceEngine/Governance_Regime_Import-8.4.1.23v4.xwf?raw=true)|Governance Regime can be exported and then imported to other XMC instance. You can share your regime with the community. Professionals can share regimes with their customers.|You may need to modify the InstallDirectory variable. During Export, you need to specify the name of the regime. The regime is exported to the file system InstallDirectory/GovernanceEngine/audit-tests/ as tgz file. The export workflow can email the regime. Transfer the file to the new system. During the import select if imported tests will be marked read-only or editable.|8.4.1.23v7 8.4.1.23v4|

# XIQ Site Engine (XMC) Extreme Fabric Automation Workflows
| Workflow Name | Description | How To | Version |
| ------------- | ----------- | ------ | ------- |
|[Day 0 Create Fabric](xwf/EFA_1_Create_Fabric-8.4.4.26v3.xwf?raw=true)|Creates Fabric through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 1 Create Tenant](xwf/EFA_2_Create_Tenant-8.4.4.26v3.xwf?raw=true)|Creates Tenant through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 1 Create EPG](xwf/EFA_3_Create_EPG-8.4.4.26v18.xwf?raw=true)|Creates VRF, Port Channels, EndPointGroup through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress, PortChannelSpeed, PortChannelNegotiation, PoName to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 2 Add Ports to Tenant](xwf/EFA_Add_Tenant_Ports-8.4.4.26v2.xwf?raw=true)|Adds ports to existing Tenant through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 2 Add Ports to EPG](xwf/EFA_Add_EPG_Ports-8.4.4.26v5.xwf?raw=true)|Adds ports to existing EndPointGroup through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress, PortChannelSpeed, PortChannelNegotiation to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 2 Create PortChannel](xwf/EFA_Create_PO-8.4.4.26v3.xwf?raw=true)|Creates PortChannel through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress, PortChannelSpeed, PortChannelNegotiation to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 2 Create VRF](xwf/EFA_Create_VRF-8.4.4.26v4.xwf?raw=true)|Creates VRF through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 2 Delete Fabric](xwf/EFA_Delete_Fabric-8.4.4.26v3.xwf?raw=true)|Workflow deletes existing Fabrics through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 2 Delete Tenant](xwf/EFA_Delete_Tenant-8.4.4.26v5.xwf?raw=true)|Workflow deletes existing Tenants through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 2 Delete PortChannel](xwf/EFA_Delete_PO-8.4.4.26v2.xwf?raw=true)|Workflow deletes existing Port Channels through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 2 Delete VRF](xwf/EFA_Delete_VRFs-8.4.4.26v4.xwf?raw=true)|Workflow deletes existing VRFs through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[Day 2 Delete EPG](xwf/EFA_Delete_EPG-8.4.4.26v5.xwf?raw=true)|Workflow deletes existing EPGs through Extreme Fabric Automation.|EFA must be in the XMC with valid CLI credentials. Modify variable EFAaddress to reflect your environment.|EFA version 2.2.0, XMC version 8.4|
|[EFAv210 package](xwf/EFA.zip?raw=true)|All EFA workflows zipped to one package.|Unzip and import.| EFA version 2.1.0, XMC version 8.2|
|[Whole EFA package](xwf/EFA220.zip?raw=true)|All EFA workflows zipped to one package.|Unzip and import.| EFA version 2.2.0, XMC version 8.4|

# XIQ Site Engine Training workflows
| Workflow Name | Description |
| ------------- | ----------- |
|[EXOS Switch Audit System Disabled](xwf/EXOS_Switch_Audit_System_Disabled-Partial-21.6.20.4v5.xwf?raw=true)|This workflow is used as part of an educational training video. It does not work as standalone workflow.|
|[Store Active Clients in Cloud Database](xwf/Store_Active_Clients_in_Cloud_Database-21.4.10.80v71.xwf?raw=true)|This workflow is used as part of an educational training video. It does not work as standalone workflow.|

# Support
_The software is provided as-is and [Extreme Networks](http://www.extremenetworks.com/) has no obligation to provide maintenance, support, updates, enhancements, or modifications. Any support provided by [Extreme Networks](http://www.extremenetworks.com/) is at its sole discretion._

Issues and/or bug fixes may be reported on [The Hub](https://community.extremenetworks.com).
>Be Extreme