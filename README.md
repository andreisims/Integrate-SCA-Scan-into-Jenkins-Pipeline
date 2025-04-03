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

### Add the Token to Jenkins
iv. Proceed to the Jenkins dashboard
<li>Select Manage Jenkins</li>
<li>Then Credentials</li>
<li>Then System</li>
<li>and then select Global Credentials</li>

![Image](https://github.com/user-attachments/assets/6ef97fda-af5f-45ea-96d1-563215d9a6df)

#### add credentials
<li>in the Kind field select 'secret text'</li>
<li>paste the snyk key value into the Secret field.</li>
<li>in the ID and Description fields, enter the same name from the jenkinsfile "SNYK_TOKEN". should be in all caps, same as in the file</li>

![Image](https://github.com/user-attachments/assets/e5679a28-bc05-46bc-8f05-faeb6c63573c)

![Image](https://github.com/user-attachments/assets/a0f85c0e-cd8e-4627-8307-153de7745084)
<li>click create</li>

### Now update the Jenkins Pipeline
v. back to Jenkins dashboard. select the pipeline so we can update it.
<li>select Configure</li>
<li>we need to update the repo to your forked version of https://github.com/asecurityguru/devsecops-jenkins-k8s-tf-sast-sca-sonarcloud-snyk-repo in the Repository URL field</li>

![Image](https://github.com/user-attachments/assets/18a212ab-8df0-4569-9571-2da5667b04c0)
<li>click apply+save</li>

#### run the Build
vi. now that the build is updated, select Build Now on the dashboard.
<li>as you can see, I made a typo in the Jenkinsfile</li>

![Image](https://github.com/user-attachments/assets/1bd42a63-2038-4ec5-b7c8-8cbd3a838854)
<li>edit the file with the correct Maven version and run Build Now again</li>

![Image](https://github.com/user-attachments/assets/40ba1f1c-d93b-47bd-b8db-1e74b778d3e7)
<li>the build failed because of the errors in the dependencies</li>

![Image](https://github.com/user-attachments/assets/5c0304fd-a9fb-4d37-aa17-8585a7cbee55)
<li>but the Jenkins build was successful</li>

![Image](https://github.com/user-attachments/assets/825ffad7-621b-4840-8292-84aea67f8b30)
<li>the Snyk file also outlines steps for remediation, by upgrading</li>

![Image](https://github.com/user-attachments/assets/ebff9ef7-5f1b-4860-a289-a6b45d109169)

SUCCESS! You can now destroy the build and repeat as needed. Hope it was helpful.
