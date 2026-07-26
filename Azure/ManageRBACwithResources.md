# Azure Storage: Switching from Storage Account Keys to Microsoft Entra ID RBAC

## Overview

This project demonstrates how I secured an Azure Storage Account by replacing traditional Shared Key authentication with **Microsoft Entra ID** and **Azure Role-Based Access Control (RBAC)**.

Instead of relying on storage account keys that grant broad access, I configured identity-based authorization using Azure RBAC. I assigned permissions at both the storage account and blob container levels and validated access using Microsoft Entra user accounts.

This lab demonstrates Azure identity and access management concepts that are commonly used by Azure Administrators, Cloud Engineers, Infrastructure Engineers, and Security Engineers.

---

# Objectives

The primary objectives of this project were to:

- Deploy an Azure Storage Account
- Configure storage security settings
- Understand Shared Key authentication
- Configure Microsoft Entra authentication
- Disable Shared Key authorization
- Assign Azure RBAC roles
- Configure container-level permissions
- Validate blob access using Microsoft Entra identities
- Demonstrate least privilege access

---

# Technologies Used

- Microsoft Azure
- Azure Storage Accounts
- Azure Blob Storage
- Microsoft Entra ID
- Azure Role-Based Access Control (RBAC)
- Access Control (IAM)
- Storage Blob Data Owner
- Storage Blob Data Reader
- Storage Blob Data Contributor
- Azure Resource Groups
- TLS 1.2
- Azure Portal

---

# Skills Demonstrated

- Azure Administration
- Azure Storage
- Identity and Access Management (IAM)
- Azure RBAC
- Microsoft Entra ID
- Cloud Security
- Blob Storage Administration
- Least Privilege Access
- Storage Security
- Resource Authorization
- Container-Level Permissions
- Access Reviews
- Azure Portal Administration

---

# Why Replace Storage Account Keys?

Azure Storage Accounts include two access keys.

These keys allow anyone possessing them to authenticate directly to the storage account.

Although simple, Shared Key authentication has several disadvantages.

## Shared Key Authentication

Advantages

- Simple to configure
- Works with older applications
- Supports scripts using connection strings

Disadvantages

- Full storage account access
- Keys are shared among users
- Difficult auditing
- Manual key rotation
- Keys may be accidentally exposed
- No identity-based authorization
- Cannot enforce least privilege

---

## Microsoft Entra ID + Azure RBAC

Using Microsoft Entra authentication provides significantly better security.

Advantages

- Identity-based authentication
- Individual user permissions
- Supports MFA
- Supports Conditional Access
- Easy role removal
- Detailed auditing
- Least privilege access
- Role inheritance

---

# Azure RBAC Architecture

```text
Microsoft Entra ID
        │
        │ Authentication
        ▼
Azure RBAC
        │
        ▼
Azure Storage Account
        │
        ├───────────────┐
        │               │
        ▼               ▼
Container 1        Container 2
        │               │
        ▼               ▼
Blob Files       Blob Files
```

---

# Management Plane vs Data Plane

Azure Storage uses two permission models.

## Management Plane

Management plane permissions control the Azure resource itself.

Examples include:

- Owner
- Contributor
- Reader

These roles allow administrators to:

- Create storage accounts
- Delete storage accounts
- Configure networking
- Configure encryption
- Configure access policies

Management plane roles DO NOT automatically grant access to blob data.

---

## Data Plane

Data plane permissions control the actual files stored inside Azure Storage.

Examples include:

- Storage Blob Data Owner
- Storage Blob Data Contributor
- Storage Blob Data Reader

These roles determine whether a user can:

- Read blobs
- Upload blobs
- Delete blobs
- Modify blob metadata

This separation is one of Azure Storage's most important security concepts.

---

# Azure RBAC Scope

Azure RBAC permissions can be assigned at different scopes.

```text
Management Group

        │

Subscription

        │

Resource Group

        │

Storage Account

        │

Blob Container

        │

Blob
```

Permissions assigned higher in the hierarchy are inherited by lower resources unless explicitly overridden.

---

# Project Walkthrough

## Step 1 — Create an Azure Storage Account

The first step was creating a new Azure Storage Account.

Configuration included:

- Standard Performance
- StorageV2
- East US Region
- Locally Redundant Storage (LRS)

This storage account serves as the parent resource for all blob containers.

![Step 1](images/rbac-01.png)

---

## Step 2 — Configure Advanced Storage Settings

During deployment I reviewed several advanced storage options including:

- Hierarchical Namespace
- Secure File Transfer Protocol (SFTP)
- NFS v3
- Cross-Tenant Replication
- Blob Access Tier

For this lab I left Hierarchical Namespace disabled because the project focused on Azure Blob Storage rather than Azure Data Lake Storage Gen2.

![Step 2](images/rbac-02.png)

---

## Step 3 — Deploy the Storage Account

After validating the configuration Azure deployed the storage account into the selected resource group.

Deployment included:

- Azure Subscription
- Resource Group
- Storage Account
- Default Storage Configuration

![Step 3](images/rbac-03.png)

---

## Step 4 — Verify Deployment

Once deployment completed successfully I reviewed the storage account properties.

Important configuration included:

- Secure Transfer Enabled
- TLS 1.2
- StorageV2
- Standard Performance
- LRS Replication
- Blob Anonymous Access Disabled

These settings provide a secure baseline for Azure Storage.

![Step 4](images/rbac-04.png)

---

## Step 5 — Review Storage Account Keys

Azure automatically creates two Storage Account Keys.

These keys can authenticate directly against the storage account without requiring Microsoft Entra authentication.

This authentication method is called **Shared Key Authentication**.

Although functional, Microsoft recommends migrating away from Shared Keys whenever possible.

Reasons include:

- Shared secrets
- Difficult auditing
- No identity association
- Broad permissions

The storage account keys remained hidden throughout this project to protect credentials.

![Step 5](images/rbac-05.png)

---

## Step 6 — Configure Storage Account Security

Next I reviewed the Storage Account Configuration page.

Security settings included:

- Secure Transfer Required
- Blob Anonymous Access Disabled
- Microsoft Entra Authorization Enabled
- Minimum TLS Version 1.2
- Hot Blob Access Tier

Enabling Microsoft Entra Authorization causes Azure Portal authentication to rely on Microsoft Entra identities rather than Storage Account Keys.

![Step 6](images/rbac-06.png)

---
