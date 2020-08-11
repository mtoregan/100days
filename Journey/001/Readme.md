<p align="center">
  <img src="/Assets/Images/banner.png">
</p>

# AZ 203 - Batch 

## Introduction

✍️ (Why) Explain in one or two sentences why you choose to do this project or cloud topic for your day's study.

## Create batch 

✍️ (What) Explain in one or two sentences the base knowledge a reader would need before describing the the details of the cloud service or topic.

```shell
az group create \
    --name my100DaysBatchResourceGroup \
    --location northeurope

az storage account create \
    --resource-group my100DaysBatchResourceGroup \
    --name my100daysstorageaccount \
    --location northeurope \
    --sku Standard_LRS


az batch account create \
    --name my100daysbatchaccount \
    --storage-account my100daysstorageaccount \
    --resource-group my100DaysBatchResourceGroup \
    --location northeurope
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
