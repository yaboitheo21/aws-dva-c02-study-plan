---
title: "Prepare Application Artifacts"
date: 2025-02-11
weight: 1
pre: "<b>3.1 </b>"
---

### Task 3.1: Prepare application artifacts to be deployed to AWS

## Artifact Repositories

Artifact repositories store và share versioned software/deployment packages:

**Lợi ích**:
- ✅ Tăng code reuse
- ✅ Giảm delivery time
- ✅ Tighter artifact governance
- ✅ Cải thiện security visibility

### AWS Services cho Artifact Storage

| Service | Use Case |
|---------|----------|
| **AWS CodeArtifact** | Secure, highly scalable, managed artifact repository |
| **Amazon S3** | Store application artifacts, deployment packages |

**CodeArtifact** eliminates need to:
- Manage your own artifact storage system
- Worry about scaling infrastructure

## Key Skills

### 3.1.1 - Manage Dependencies
- Manage dependencies của code module trong package
- Use Lambda layers cho libraries và dependencies
- Package management tools (pip, npm, yarn)

### 3.1.2 - Directory Structure
- Organize files và directory structure cho deployment
- Version control của artifacts
- Track revision history

### 3.1.3 - Code Repositories
- Use code repositories trong deployment environments
- Store code, track revisions, merge changes
- Revert to earlier versions khi cần

### 3.1.4 - Resource Requirements
- Apply application requirements cho resources
- CloudFormation helper scripts
- Systems Manager Application Manager
- AWS AppConfig

### 3.1.5 - Configuration Data
- Access application configuration data
- Parameter Store
- Secrets Manager
- AppConfig

{{% children %}}
