# Experiment Report: Install Gitea Locally via Docker

## Experiment Overview

This experiment aims to install and configure the Gitea DevOps platform on a local machine using Docker. Key objectives include verifying Gitea's LFS (Large File Storage) support, uploading a large file (≥1GB) to a repository, and documenting the entire process.

## Prerequisites

- Docker Desktop installed and running
- Basic understanding of Docker command operations
- Stable network connection

## Installation Steps

### 1. Create Data Storage Directories

To ensure Gitea data persistence, create local directories for data and configuration:

```bash
mkdir -p $env:USERPROFILE\gitea\data $env:USERPROFILE\gitea\config
```

### 2. Start Gitea Container

Run the following command to launch the Gitea container:

```bash
docker run -d `
  --name=gitea `
  -p 3000:3000 `
  -p 222:22 `
  -v ${env:USERPROFILE}\gitea\data:/data `
  -v ${env:USERPROFILE}\gitea\config:/etc/gitea `
  --restart always `
  gitea/gitea:latest
```

![image-20251016103926083](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251016103926083.png)

### 3. Initialize Gitea Configuration

1. Open a web browser and visit `http://localhost:3000`
2. On the initial configuration page, set the following key parameters:
   - Database Type: SQLite3 (default, no additional configuration required)
   - Site Title: Custom name (e.g., "ZTM's Gitea")
   - Repository Root Path: `/data/git/repositories` (default)
   - LFS Root Path: `/data/git/lfs` (enable LFS storage)
   - Run As Username: `git` (default)
   - Server Domain: `localhost`
   - HTTP Port: `3000`
   - Base URL: `http://localhost:3000/`
   - Administrator Account: Create admin credentials (username, email, password)
3. Keep other settings as default and click "Install Gitea" to complete configuration.

![image-20251016104014994](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251016104014994.png)

![image-20251016104023746](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251016104023746.png)

## a. Verify Gitea LFS Support

### Step 1: Check LFS Function Switch

1. Log in to Gitea with the administrator account
2. Click the username in the upper right corner → Select "Site Administration"
3. Navigate to "Settings" → "LFS" tab
4. Confirm that "Enable Git LFS Support" is checked (enabled by default)

![image-20251016104039565](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251016104039565.png)

### Step 2: Function Verification

1. Install Git LFS client (run in terminal):

   ```bash
   git lfs install
   ```

   

2. Create and clone a test repository:

   ```bash
   # Clone the repository (after creating it in Gitea web interface first)
   git clone http://localhost:3000/[Your Username]/test-lfs.git
   cd test-lfs
   
   # Configure LFS to track specific file types
   git lfs track "*.bin"
   git add .gitattributes
   git commit -m "Enable LFS for bin files"
   git push
   ```

## b. Create Repository with Large File (≥1GB)

### Step 1: Prepare Large File

Create a 1GB test file using terminal commands:

```bash
fsutil file createnew large_file.bin 1073741824
```

### Step 2: Upload Large File

```bash
# Track the large file with LFS (if not already configured)
git lfs track "large_file.bin"

# Add files to staging area
git add large_file.bin .gitattributes

# Commit to local repository
git commit -m "Add 1GB test file"

# Push to remote repository
git push
```

![image-20251016104250724](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251016104250724.png)

### Step 3: Verify Upload Result

1. Visit the `test-lfs` repository in Gitea web interface
2. Confirm that `large_file.bin` is displayed in the file list
3. Check that the file is marked as an LFS object

![image-20251016104258494](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251016104258494.png)

## Experiment Results

- Successfully installed Gitea via Docker and completed initial configuration
- Verified Gitea's native support for Git LFS functionality
- Successfully created a repository and uploaded a 1GB+ large file using LFS
- Achieved persistent storage of Gitea data through Docker volume mapping

