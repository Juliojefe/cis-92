# My CIS-92 Project 

This repository has the starter code for CIS-92. 

Author: Julio Fernandez

<br /><br />
### config.yaml
| Variable Name | Default Value | Description |
|---|---|---|
| STUDENT_NAME | Julio Fernandez | My Name |
| SITE_NAME | * | Unamed Site | 
| DEBUG | 1 | Debug Option | 
| POSTGRES_DB| mysite | database |
| POSTGRES_HOSTNAME | postgres-postgresql | name of postgres host|
<br />

### secret.yaml
| Variable Name | Default Value | Description |
|---|---|---|
| SECRET_KEY | this-is-a-bad-keyurtiuitirut | change this (IMPORTANT) | 
| POSTGRES_PASSWORD | another-bad-password | database password (PostgresSQL) |
| POSTGRES_USER | mysiteuser | database username (PostgresSQL)|
<br />

Important: The values for POSTGRES_USER and POSTGRES_PASSWORD in secret.yaml need to match the values of username and postgresPassword in values-postgres.yaml for proper functionality.
<br />

### values-postgres.yaml
| Variable Name | Default Value | Description |
|---|---|---|
| username | mysiteuser | PostgresSQL database username |
| password | this-is-a-bad-password | Postgres password |
| database | mysite | name given to PostgresSQL database |
| postgresPassword | another-bad-password | PostgresSQL database password | 
<br />

### primary resources requests
| Variable Name | Default Value | Description |
|---|---|---|
| memory | 512Mi | minimum memory required |
| cpu | 500m | minimum cpu required |
| ephemeral-storage	 | 100Mi | minimum storage required |
<br />

### pirimary resources limits
| Variable Name | Default Value | Description |
|---|---|---|
| memory | 512Mi | maximum memory needed |
| cpu | 500m | maximum cpu needed |
| ephemeral-storage	 | 100Mi | maximum storage needed |
<br />

### To deploy application and initialize database run the following commands  
1) helm install postgres oci://registry-1.docker.io/bitnamicharts/postgresql --values values-postgres.yaml
2) kubectl apply -f deployment/
3) kubectl exec --stdin --tty pod/mysite-pod -- /bin/bash
4) python manage.py migrate
5) python manage.py createsuperuser
<br /> <br />

### To delete run
1) kubectl get all 
2) kubectl delete pod/postgres-postgresql-0 pod/mysite-pod service/mysite-svc service/postgres-postgresql service/postgres-postgresql-hl
3) helm uninstall postgres