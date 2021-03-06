# cc-server
Cloud custodian in a container and accessed  through a rest api.

# Why
Cloud custodian is a command line tool. To automate and operationalize cloud custodian, one would need
- to choose an appropriate cost effective run environment such as Jenking, codebuild or docker. 
- bash scripts in pipelines
- a way to manage the state of what has been deployed.
Depending on the scale and requirements of the org, it could be challenging to clean up garbage and manage logs. Also, additional infrastructure (such as s3 buckets for logs, sqs ques for notifications, sns topics for ) needs to be managed.

Fronting cc with a rest api allows us to:
- package cc as a web app, simplifying deployment
- different systems can integrate against it
- easy to pass roles/account numbers for multi account deployments.
- plan to create a terraform provider.

# Tools

##  Fastapi
- it is fast(er than Django) (supports async workflows)
- built in rest api support (no need for django plus drf)
- hopefully easier to write

## Docker/Kubernetes
- Webapp packaged in docker image for easy distribution and deployment
- helm chart for installing on kubernetes

## cloud custodian
- c7n
- c7n mailer

## Terraform
- terraform provider for interacting with api
- terraform module for deploying aws infrastructure 
