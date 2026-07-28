# Jenkins vs Husky

Jenkins is an *open-source automation server* allowing developers to implement *Continuous Integration and Continuous Delivery (CI/CD) workflows*

It is written in Java and automates repetitive tasks such as compiling code, running tests, analyzing code quality, and deploying completed software to servers.
It increases roll-out times and decreases human error for production-ready code 

**Jenkins activates when code gets pushed on a central repository on GitHub** whilst Husky is an *automation tool* that only runs tests **before you commit locally**

Jenkins integrates with Docker, Kubernetes etc.

Jenkings pushes code directly to production making sure none of the features are compromised for increased stability.

Feature | Jenkins | Husky
-------- |--------- | --------
**Where it runs** | Central server/cloud | Local machine (developer's computer)
**When it runs** | *After* code is pushed to Git | *Before* code is committed or pushed
**Primary purpose** | Compiling, testing, and deploying apps | Enforcing code style and linting rules locally
**Scope** | Whole team and production environments | Individual developer workflow

This means that the two are not opposing systems but *they complement each other* to improve CI/CD workflows
