## Integrating Snyk Scans into a Jenkins Pipeline

This tutorial will guide you through adding Snyk Software Composition Analysis (SCA) scan to a Jenkins pipeline to automatically detect vulnerabilities in dependencies. This is a continuation of the previous guide on how we integrated SonarCloud SAST (Static Application Security Testing) Scan.


Steps Covered
1. Generate a Snyk API Token – Create an authentication token in the Snyk dashboard.

2. Update pom.xml – Configure Maven dependencies for Snyk analysis.

3. Modify Jenkinsfile – Add Snyk scan stages using the Snyk Security Plugin or CLI.

4. Run & Review Results – Execute the pipeline and analyze Snyk’s vulnerability report.
