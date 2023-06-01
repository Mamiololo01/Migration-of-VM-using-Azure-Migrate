# Migration-of-VM-using-Azure-Migrate
Step by step guides in migrating VM/Hyper V to Azure Cloud using Azure Migrate

Migration planning

Strategy - what success looks like including business ad technical goals


Planning - Map out what needs to be moved and the strategy will be achieved.

Preparation: prepare both the source and destination for the migration

Migration- replicating the servers from the source to the destination

Handover - handover the final solution to the ops team for ongoing maintenance

AZURE MIGRATE

Supports migration of data, web, application and servers

It has assessment tool which can work with 3rd party tools for accessing migrations

Migration tools- help to migrate source environment to cloud.

Database- Database migration service

Data Migrations- Physical Data box hardware

Web application- Azure App service

Click on Azure migrate and click on create project Under migration goals , we have servers, database, VDI, Web App and Data box

Click on server and then you will see the assessment tools

Azure Migrate: Server migration

We have discover, replicate, Migrate and overview

Under create a new project

A. Migrate project

Subscription

Resource group

PROJECT DETAILS

Migrate project

Geography

B SELECT ASSESSMENT

Pick Azure Migrate server assessment; out of many tools

C. SELECT MIGRATION TOOLS

Pick Azure Migrate server assessment; out of many tools

D. REVIEW + ADD

Click and it will set up the deployment.

Click on resource groups and pick the newly deployed resource group

SERVER ASSESSMENT.

Discover-deploy an appliance to uncover VM, Hyper-v and other metadata to be used on the project.. If there are cloud connection or another on-premise server

Cost and readiness-determine suitability of VM for the migration and the cost

Dependency analysis- determine the server dependencies including network, software, versions

SERVER MIGRATION
Discovery

Replication- configure a replication appliance responsible for replicating Hyper-V, VMs to the replication storage account.

MIGRATION: Perform the test and actual migration.

Steps
Install assessment appliance(web app) on-premise

Dependency analysis by installing log analytics workspace on all machines/VM on-premise

Steps

Azure Migrate>Servers>Discover and click on Hyper-V

Download and install the Azure migrate appliance on the Hyper V

Complete the prerequisite like connecting to internet, time sync, latest update and accepting terms and condition.

Then login and enter Azure portal and then register the appliance

Provide hyper V credentials and add the host and validate

Save and start discovery…15mins

As it is completed successfully, if you check on the Azure server portal, you will see an increase in the number of discovered server.

Configure OMS workspace and location

For dependencies for each server,

Download and install MMA (Microsoft monitoring agebt_

Download and install dependency agent

Configure MMA agent

Access the servers

Assessment details

Assessment type; Azure VM

Discovery source; Machines discovered from Azure migrate appliance

Assessment name- give a name

Other details, reserved instance 3years or more, storage type:automatic, location, VM size, pricing, percentile utilisation, VM series…

If dependency, then click on both servers and then group machine  then create a new assessment for the group

Architecture

Azure Migrate

Replication

Migration/Failover- Creates a VM in Azure using the replicated data

Migration tools

Azure Migrate: Server Migration

Discover>>Replicate>>Migrate

Discover, pick VM type and location(target region) and create resources

Download Azure site recovery provider  and vault credentials

Install the Azure site recovery provider setup, use the vault credentials to finalise registration

Click on Replicate or Overview

Step 1 ; Replicate. Click and pick Hyper-V. Import VM, no or Yes and then pick the actual VM to replicate or group respectively. Click on target settings and fill all parameters. Click on compute which shows VM size, availability, OS  type and OS Disk. Click on Disk and then review + replication

Step 2; Test migration

Click on Test migration and select virtual network(vnet1) and click om test migration. It shows healthy stats and no configuration issues if the test was successful. Afterwards, you can plan for the actual migration. You can connect to the test VM via SSH, RDP, bastion to check everything is fine as expected. Then clean up testing checks cum failover.

Step 3; Migrate

Click on migrate, pick the VM and shutdown the machine before migration to minimise data list, Yes and click on migrate.  Migration successful and the VM at on-premise is shut down. After monitoring period, Ops team will manage the infra
