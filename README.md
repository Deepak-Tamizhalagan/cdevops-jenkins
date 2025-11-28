
## Assignment 4 – Jenkins CI/CD in Kubernetes

## Team Contribution Breakdown
Member	Responsibility

+ Deepak Tamizhalagan	Jenkins installation using Ansible (up.yml / down.yml), Helm configuration (values.yaml), folder structure setup, and README documentation for deployment.

+ Cibi Sharan	Created sample pipeline project using Jenkinsfile, prepared sample-app/README.md, worked on CI pipeline explanation and repository integration steps.

## Deepak Tamizhalagan – Contribution Details

As part of this assignment, I was responsible for deploying Jenkins into the Kubernetes environment using Ansible and Helm, and ensuring it aligns with the assignment requirements. 

Technical Responsibilities

+ Set up the jenkins/ folder structure in the project repository.

+ Developed up.yml and down.yml playbooks to automate:
+ + Creating the namespace
  + Installing Jenkins via Helm
  + Enabling persistent storage
  + Removing Jenkins resources during cleanup

+ Configured values.yaml with:
+ +  Default admin credentials (admin/admin123)
  +  PersistentVolume settings
  +  Service exposure via ClusterIP

+ Updated the README.md to include:
+ + Deployment and cleanup instructions
  + Jenkins access details
  + Notes on integration requirements

## Deployment Steps
```
pip install ansible kubernetes openshift
ansible-playbook jenkins/up.yml
kubectl port-forward svc/jenkins 8080:8080 -n jenkins
```

Then access Jenkins via:
```
http://localhost:8080
Username: admin
Password: admin123
```

To remove all resources from the cluster:
```
ansible-playbook jenkins/down.yml
```
# Sample CI Pipeline Project

This project is used to verify Jenkins pipeline functionality as per Assignment 4 requirements.

## Purpose
The Jenkinsfile demonstrates a simple CI workflow executed inside Jenkins once integrated with GitHub and Gitea.

## Pipeline Stages
- *Checkout* – Retrieves source code
- *Build* – Simulates application build
- *Test* – Runs basic test output

## Integration Instructions
1. Push this folder as a separate repository in GitHub.
```bash
https://github.com/Cibi619/test-jenkins.git
```
2. Also push to Gitea (http://gitea.placeholder.local) as required.
3. In Jenkins:
   - Create a new pipeline job.
   - Configure SCM connection (GitHub/Gitea link).
   - Ensure Jenkins triggers a build on push or run manually.

## Notes
- This sample app does not require any runtime environment.
- The Jenkinsfile is intentionally minimal and structured for demonstration.
- Ideal for testing pipeline setup, SCM integration, and Jenkins configuration.

---

### Contribution
Prepared by *Cibi Sharan*  
Responsible for:
- Creating the CI test project
- Writing the Jenkinsfile
- Documenting pipeline flow
- Assisting with integration configuration