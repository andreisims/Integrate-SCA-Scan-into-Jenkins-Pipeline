## Integrating Snyk Scans into a Jenkins Pipeline

This tutorial will guide you through adding Snyk Software Composition Analysis (SCA) scan to a Jenkins pipeline to automatically detect vulnerabilities in dependencies. This is a continuation of the previous guide on how we integrated SonarCloud SAST (Static Application Security Testing) Scan.


Steps Covered
1. Generate a Snyk API Token – Create an authentication token in the Snyk dashboard.

2. Update pom.xml – Configure Maven dependencies for Snyk analysis.

3. Modify Jenkinsfile – Add Snyk scan stages using the Snyk Security Plugin or CLI.

4. Run & Review Results – Execute the pipeline and analyze Snyk’s vulnerability report.

### Create an account on Snyk (https://snyk.io/)

i. Sign up with Github

![Image](https://github.com/user-attachments/assets/79df046f-8fa8-4022-bc59-f0178b78b920)

<li> Fork the snyk repo into your own repository (https://github.com/asecurityguru/devsecops-jenkins-k8s-tf-sast-sca-sonarcloud-snyk-repo.git) and update the pom.xml file.
<li>Scroll down to the 'Changes for Software Composition Analysis Scan using Snyk' section to update the org name (use same org name from the last guide)</li>

![Image](https://github.com/user-attachments/assets/7b3e0ff4-f30f-43b8-826d-4d9fa40d9bcb)
### Update the Jenkinsfile
ii. Go to the jenkinsfile in the repo.
<li>update the projectkey</li>
<li>update the organization</li>
<li>update the token (all things that we have done before)</li>

![Image](https://github.com/user-attachments/assets/d93c4699-d36e-49b7-afab-cbc98de53daa)
### Create a Token on Snyk
iii. Go back to the Snyk dashboard
<li>Go to Settings</li>
<li>then select 'General'</li>
<li>in the Key field, select 'click to show'</li>

![Image](https://github.com/user-attachments/assets/9631d9f2-9865-4cf3-80ec-4ea3c0ec9d50)
<li>copy the key to your notepad</li>





