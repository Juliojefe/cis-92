# My CIS-92 Project 

This repository has the starter code for CIS-92. 

Author: Julio Fernandez


| Variable Name | Default Value | Description |
| --- | --- | --- | 
| PORT | 8000 | Easy to work with port | 
| STUDENT_NAME | Julio Fernandez | My Name |
| SITE_NAME | * | Unamed Site | 
| DATA_DIR | /data | location where data is stored |
| DEBUG | 1 | Debug Option | 
| SECRET_KEY | this-is-a-bad-key | change this (IMPORTANT) | 

To deploy run the following commands  
1) kubectl apply -f deployment/
2) kubectl get all - (copy external ip into browser of choice)
3) application has been deployed

To delete run
1) kubectl get all 
2) kubectl delete <pod and service name>
3) application has been deleted