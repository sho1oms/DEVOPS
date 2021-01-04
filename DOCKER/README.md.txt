
# Building and running Dockerfile

```
From URL:
docker build github.com/creack/docker-firefox

Build with PATH without TAG:

$ docker build .

Sending build context to Docker daemon  3.072kB
Step 1/2 : FROM alpine
latest: Pulling from library/alpine
801bfaa63ef2: Pull complete
Digest: sha256:3c7497bf0c7af93428242d6176e8f7905f2201d8fc5861f45be7a346b5f23436
Status: Downloaded newer image for alpine:latest
 ---> 389fef711851
Step 2/2 : CMD echo "Hello World"
 ---> Running in 2ae6e8b4c6fe
Removing intermediate container 2ae6e8b4c6fe
 ---> d7aa8811b487
Successfully built d7aa8811b487
SECURITY WARNING: You are building a Docker image from Windows against a non-Windows Docker host. All 
files and directories added to build context will have '-rwxr-xr-x' permissions. It is recommended to 
double check and reset permissions for sensitive files and directories.

Build with PATH with TAG:

docker build -t demo:latest .

```

# Environment variables and secrets

Variables have added security requirenments:
- passwords
- SSL cert
- DB connection cred

```
FROM alpine
ENV STAGE="dev"
CMD: echo $(STAGE)
```


docker run -e "STAGE=prod" demo

#Data Volumes


#Azure Container Reqistry ( ACR )

Store distribute and manage container images
Version control:
- push 
- pull
- tags

Fundamental block of distributing

Secured:
ACR - security and high avalibility
- access is by Active direcrtory or firewall - identity and network
- Cross region replication

Azure container registry can be used as building tasks in the cloud and publish in registry.

#Create ACR from CLI
acr create --name kin1234 --resource-group --location westus --sku Premium

Name globally unique!! 

ACR pricing tiers:
-basic
-standard
-premium

Prod env should be used (MICROSOFT RECOMMENED) - STANDARD

Security controles:
- onitoring
- Bring your own key
- Firewall
- AUthentication and autorization


# Publish your application in ACR

az acr login --name kin1234

ACR authentication and Autorizastion
- Azure Active Directory user
- Managed identity
- Azure AD service principal 
- Admin User - no recomemded - disabled by default 

dicjer push <name of regiustry>/demo:latest




