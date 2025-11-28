
Assignment 4 – Jenkins CI/CD in Kubernetes
👥 Team Contribution Breakdown
Member	Responsibility
Deepak Tamizhalagan	Jenkins installation using Ansible (up.yml / down.yml), Helm configuration (values.yaml), folder structure setup, and README documentation for deployment.
Cibi Sharan	Created sample pipeline project using Jenkinsfile, prepared sample-app/README.md, worked on CI pipeline explanation and repository integration steps.

Deepak Tamizhalagan – Contribution Details

As part of this assignment, I was responsible for deploying Jenkins into the Kubernetes environment using Ansible and Helm, and ensuring it aligns with the assignment requirements. 

Technical Responsibilities

Set up the jenkins/ folder structure in the project repository.

Developed up.yml and down.yml playbooks to automate:

Creating the namespace

Installing Jenkins via Helm

Enabling persistent storage

Removing Jenkins resources during cleanup

Configured values.yaml with:

Default admin credentials (admin/admin123)

PersistentVolume settings

Service exposure via ClusterIP

Updated the README.md to include:

Deployment and cleanup instructions

Jenkins access details

Notes on integration requirements

Deployment Steps (Configured by Me)
pip install ansible kubernetes openshift
ansible-playbook jenkins/up.yml
kubectl port-forward svc/jenkins 8080:8080 -n jenkins


Then access Jenkins via:

http://localhost:8080
Username: admin
Password: admin123


To remove all resources from the cluster:

ansible-playbook jenkins/down.yml