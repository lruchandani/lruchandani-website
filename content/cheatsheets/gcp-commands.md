---
title: "GCP Commands CheatSheet"
date: 2020-06-22T10:40:36-04:00
summary: "Handy list of some GCP commands"
draft: true
---
## Authentication
1. Authentication with browser
```bash
gcloud auth login
```
2. Authentication without browser
```bash
gcloud uth login --no-launch-browser
```
3. List current authentication accounts
```bash
gcloud auth list
```
4. Application default
    * *Login*  
    This is useful  in the development mode where you want that authentication is extended not only to the shell but also 
    to all the google libraries  used in the programs running from that machine. No,  need to setup GOOGLE_APPLICATION_CREDENTIALS.
    This steps stores the file at following location `$USER_HOME/.config/gcloud/application_default_credentials.json`
    ```bash
    gcloud auth application-default  login --no-launch-browser
    ```
    * *Logout*  
    ```bash
    gcloud auth application-default revoke
    ```

5. Print Access token 
```bash
gcloud auth print-access-token
```
6. Revoke / Log out
```bash
 gcloud auth revoke
 ```
## Compute
1. Get List of instances
```bash
gcloud compute instances list
```
2. Create Network
3. Create Subnet
4. Create instance 
6. Setup firewall
5. Set up VPC peering

 

