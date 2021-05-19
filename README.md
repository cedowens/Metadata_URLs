# Metadata_URLs
List of some interesting cloud metadata URLs 

## AWS IDMSv1:
- curl http://169.254.169.254/latest/user-data (host info and may contain creds)
- curl http://169.254.169.254/latest/meta-data/iam/security-credentials (returns a list of roles available
- curl http://169.254.169.254/latest/meta-data/iam/security-credentials/[role-name] (returns aws creds for the specified role)
- curl http://169.254.169.254/latest/meta-data/local-hostname (return local hostname info)
- curl http://169.254.169.254/latest/meta-data/public-hostname (return public hostname info)
- curl http://169.254.169.254/latest/meta-data/public-keys/0/openssh-key (return public key info)

## AWS IDMSv2:
- Get Host Info (may contain creds): curl -H "X-aws-ec2-metadata-token: $TOKEN" -v http://169.254.169.254/latest/user-data 
- Get List of Roles Available: curl -H "X-aws-ec2-metadata-token: $TOKEN" -v http://169.254.169.254/latest/meta-data/iam/security-credentials 
- Get AWS Creds for Specified Role: curl -H "X-aws-ec2-metadata-token: $TOKEN" -v http://169.254.169.254/latest/meta-data/iam/security-credentials/[role-name] 
- Get Local Hostname: curl -H "X-aws-ec2-metadata-token: $TOKEN" -v http://169.254.169.254/latest/meta-data/local-hostname
- Get Public Hostname: curl -H "X-aws-ec2-metadata-token: $TOKEN" -v http://169.254.169.254/latest/meta-data/public-hostname
- Get Public Keys: curl -H "X-aws-ec2-metadata-token: $TOKEN" -v http://169.254.169.254/latest/meta-data/public-keys/

## GCP:
- curl http://169.254.169.254/computeMetadata/v1/instance/service-accounts/default/ -H "Metadata-Flavor: Google" (list of default service accounts for the project)
- curl http://169.254.169.254/computeMetadata/v1/?recursive=true&alt=text -H "Metadata-Flavor: Google" (return info specific to the compute host you are on)
- curl http://169.254.169.254/computeMetadata/v1/instance/service-accounts/default/token -H "Metadata-Flavor: Google" (return auth token info)
- curl http://169.254.169.254/computeMetadata/v1/instance/service-accounts/default/scopes -H "Metadata-Flavor: Google" (returns scopes for default service accounts)
- curl "http://169.254.169.254/computeMetadata/v1/?recursive=true&alt=text" -H "Metadata-Flavor: Google"
