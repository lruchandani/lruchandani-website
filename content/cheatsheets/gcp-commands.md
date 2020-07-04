---
title: "GCP Commands CheatSheet"
date: 2020-06-22T10:40:36-04:00
summary: "Handy list of some GCP commands"
draft: true
---
## Authentication
1. Authentication with browser
```
gcloud auth login
```
2. Authentication without browser
```
gcloud uth login --no-launch-browser
```
3. List current authentication accounts
```
gcloud auth list
```
4. Application default
    * *Login*  
    This is useful  in the development mode where you want that authentication is extended not only to the shell but also 
    to all the google libraries  used in the programs running from that machine. No,  need to setup GOOGLE_APPLICATION_CREDENTIALS.
    This steps stores the file at following location `$USER_HOME/.config/gcloud/application_default_credentials.json`
    ```
    gcloud auth application-default  login --no-launch-browser
    ```
    * *Logout*  
    ```
    gcloud auth application-default revoke
    ```

5. Print Access token 
```
gcloud auth print-access-token
```
6. Revoke / Log out
```
 gcloud auth revoke
 ```
## Compute
* Get List of instances
```
gcloud compute instances list
```
* Running instances
```
gcloud compute instances list --filter status=RUNNING
```
* Stopped Instances
```
WKMCA0719466:lruchandani lalrucha$ gcloud compute instances list --filter status=TERMINATED
NAME         ZONE        MACHINE_TYPE   PREEMPTIBLE  INTERNAL_IP   EXTERNAL_IP  STATUS
perf-test-1  us-east1-b  n1-standard-4               10.142.0.50                TERMINATED
```

2. Create Network
3. Create Subnet
4. Create instance 
6. Setup firewall
5. Set up VPC peering

 

