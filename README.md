# Drupal Package

Drupal is one of the most versatile open source content management systems in the world. It is pre-configured with the Ctools and Views modules, Drush and Let's Encrypt auto-configuration support.

## Configuration Reference

You can configure the following:

### Drupal parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|image.pullPolicy|Drupal image pull policy|string|IfNotPresent
|drupalProfile|Drupal installation profile|string|standard"
|drupalUsername|User of the application|string|user|
|drupalPassword|Application password|string|""|
|drupalEmail|Admin email|string|user@example.com|
|replicaCount|Number of Drupal Pods to run (requires ReadWriteMany PVC support)|integer|1|
|prometheus.io/port|drupal prometheus.io/port|integer|9117|
|prometheus.io/scrape|drupal prometheus.io/scrape|string|TRUE|
|containerPorts.http|drupal HTTP container port|integer|8080|
|containerPorts.https|drupal HTTPS container port|integer|8443|
|updateStrategy.type|update strategy - only really applicable for deployments with RWO PVs attached|string|RollingUpdate|
|priorityClassName|Drupal pods' priorityClassName|string|""|
|sessionAffinity|Control where client requests go, to the same pod or round-robin. Values: ClientIP or None|string|None|
|resources.limits|The resources limits for the init container	string|{}|
|resources.requests|The requested resources for the init container|string|{}|
|resources.cpu|Cpu for the drupal container|integer|300m|
|resources.memory|memory for the drupal container|integer|512Mi|
|podSecurityContext.fsGroup|Drupal pods' group ID|integer|1001|
|containerSecurityContext.runAsNonRoot|Set Controller container's Security Context runAsNonRoot|string|true|
|containerSecurityContext.runAsUser|Drupal containers' Security Context|integer|1001|
|initialDelaySeconds|Initial delay seconds for livenessProbe|integer|600|
|livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|10|
|livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|5|
|livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|5|
|livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|readinessProbe.initialDelaySeconds|readinessProbe.initialDelaySeconds|integer|30|
|readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|5|
|readinessProbe.timeoutSeconds|Timeout seconds for readinessProb|integer|1|
|readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|5|
|readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|startupProbe.enabled|		
|startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|integer|600|
|startupProbe.periodSeconds|Period seconds for startupProbe|integer|10|
|startupProbe.timeoutSeconds|Timeout seconds for startupProbe|integer|5|
|startupProbe.successThreshold|Success threshold for startupProbe|integer|1|
|startupProbe.failureThreshol|Failure threshold for startupProbe|integer|5|
|drupalPassword|Application password|string|myadmin|
|mariadbrootPassword|mariadb rootPassword|string|mypassword|
|mariadbPassword|mariadb Password|string|dbpassword|
|persistence.size|PVC Storage Request for Drupal volume|integer|8GI|

### Traffic Exposure Parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|service.ports.http|Drupal service HTTP port|integer|80|
|service.ports.https|Drupal service HTTPS port|integer|443|
|ingress.enabled|Enable ingress record generation for Drupal|string|false| 
|ingress.pathType|Enable ingress record generation for Drupal|string|ImplementationSpecific|

### Metrics parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|metrics.enabled|string|FALSE|
|metrics.livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|15|
|metrics.livenessProbe.timeoutSeconds|Initial delay seconds for readinessProbe|integer|5|
|metrics.readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|5|
|metrics.readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|1|
|metrics.containerPorts|Container ports|integer|9117|

### Database parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|mariadb.auth.rootPassword|Password for the MariaDB root user|string|""|
|mariadb.auth.username|Database user to create|string|bn_drupal
|mariadb.auth.password|Password for the database|string|""|
|mariadb.portnumber|mariadb port number|integer|3306|


