# Introduction
Batch has been rescently added to the AZ 203 exam and here is a summary of what might be expected to appear on the exam. 

## Batch
Use Azure Batch to run large-scale parallel and high-performance computing (HPC) batch jobs efficiently in Azure. Azure Batch creates and manages a pool of compute nodes (virtual machines), installs the applications you want to run, and schedules jobs to run on the nodes. There's no cluster or job scheduler software to install, manage, or scale. Instead, you use Batch APIs and tools, command-line scripts, or the Azure portal to configure, manage, and monitor your jobs.

## Steps 
These are the steps that are required to be taken to setup a batch job and allocate tasks to be processed. For the creation of these batch servcie I will be using Azure CLI.  

Part 1: Create Resource groups and Accounts  
- Create a Resource Goup  
- Create a Storage account  
- Create a batch account 
- Give batch account login rights 

Part 2: Create Pool, Job and tasks  
- Create a batch Pool 
- Create a Job 
- Create Tasks 
- Review output 

### Resource groups and Accounts 

Create a resource group for the batch resources.
```shell
az group create \
    --name my100DaysBatchResourceGroup \
    --location northeurope
```
Create a storage account in the resource group 
```shell
az storage account create \
    --resource-group my100DaysBatchResourceGroup \
    --name my100daysstorageaccount \
    --location northeurope \
    --sku Standard_LRS
```
Create a batch storage account for the previously created storage. 

```shell
az batch account create \
    --name my100daysbatchaccount \
    --storage-account my100daysstorageaccount \
    --resource-group my100DaysBatchResourceGroup \
    --location northeurope
```
```shell
az batch account login \
    --name my100daysbatchaccount \
    --resource-group my100DaysBatchResourceGroup \
    --shared-key-auth
```

### Pool, Job and Tasks 
```shell
#create pool 
az batch pool create \
    --id mypool --vm-size Standard_A1_v2 \
    --target-dedicated-nodes 2 \
    --image canonical:ubuntuserver:16.04-LTS \
    --node-agent-sku-id "batch.node.ubuntu 16.04" 

#view ceation

az batch pool show --pool-id mypool \
    --query "allocationState"

  #job 

  az batch job create \
    --id myjob \
    --pool-id mypool

  #tasks 

  for i in {1..4}
do
   az batch task create \
    --task-id mytask$i \
    --job-id myjob \
    --command-line "/bin/bash -c 'printenv | grep AZ_BATCH; sleep 90s'"
done

#cl;ean up 

az batch pool delete --pool-id mypool
az group delete --name myResourceGroup


https://docs.microsoft.com/en-us/azure/batch/quick-create-cli

```

## Run batch 

- 🖼️ (Show-Me) Create an graphic or diagram that illustrate the use-case of how this knowledge could be applied to real-world project
- ✍️ (Show-Me) Explain in one or two sentences the use case

## View Results 

## Cloud Research

- ✍️ Document your trial and errors. Share what you tried to learn and understand about the cloud topic or while completing micro-project.
- 🖼️ Show as many screenshot as possible so others can experience in your cloud research.

### Step 1 — Summary of Step

![Screenshot](https://via.placeholder.com/500x300)

### Step 1 — Summary of Step

![Screenshot](https://via.placeholder.com/500x300)

### Step 3 — Summary of Step

![Screenshot](https://via.placeholder.com/500x300)

## ☁️ Cloud Outcome

✍️ (Result) Describe your personal outcome, and lessons learned.

## Next Steps

✍️ Describe what you think you think you want to do next.

## Social Proof

✍️ Show that you shared your process on Twitter or LinkedIn

[link](link)
