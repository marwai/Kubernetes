users access K8 API using kubectl have to be authenticated, authorised to use specific actions and sometimes have admission 
control to approve or reject request

### Types of User
Normal users: Humansinteracting with the system
Service accounts: Accounts managed by the k8s API
	- Username - string to identify the end user
	- UID - identifier - more consistent or unique than username
	- Group - a string that associate users with a set of commonly grouped users 
	- Extra fields: a map of strings that hold additional information that might be used by the authorisation system 
	
### Authentication 
- Does user have access to the system?

### Authorisation 
- Can the user peroform an action in the system?


### 4 popular modules to authenticate
- Client certs
- Static token files (static password file)
- Openid Connects
- Webhook mode

### Client Certs
- Client certificate authentication enabled by passing the --clinet-ca-file=FILENAME option to the API server
- Referenced file must contain one or more certificate authorities to validate client certificates 
- The common name of a client certificate is used as the user name for the request

### Static token files
- Use --token-auth-file=FILE_WITH_TOKENS optinos on the command line 
- Token file is a CSV file with four columns: token, user name, user, UID
	- Example: token, user,uid, "group1, group2, group3"

### OpenID Connects

### Webhook Mode
