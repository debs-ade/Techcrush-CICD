# Automated Website Deployment to AWS EC2 using GitHub Actions

## Overview

This project demonstrates a Continuous Integration and Continuous Deployment (CI/CD) pipeline that automatically deploys a static website to an AWS EC2 Ubuntu server using GitHub Actions.

Whenever changes are pushed to the `main` branch, GitHub Actions securely connects to the EC2 instance via SSH and updates the website by pulling the latest changes from the GitHub repository.

This project was completed as part of my Cloud & DevOps training at TechCrush Academy.

---

## Technologies Used

- AWS EC2
- Ubuntu Linux
- NGINX
- Git
- GitHub
- GitHub Actions
- SSH
- HTML
- CSS
- JavaScript

---

## Project Workflow

1. A developer pushes code to the `main` branch.
2. GitHub Actions automatically starts the deployment workflow.
3. The workflow checks out the latest version of the repository.
4. GitHub Actions securely connects to the EC2 instance using SSH credentials stored as GitHub Secrets.
5. The workflow navigates to the web server directory (`/var/www/html`).
6. The server pulls the latest changes using:

```bash
git pull origin main
```

7. The updated website is immediately served by NGINX.

---

## GitHub Actions Workflow

The deployment workflow includes:

- Checkout repository
- Secure SSH connection to EC2
- Automatic deployment on every push to `main`

```yaml
on:
  push:
    branches:
      - main
```

---

## GitHub Secrets Used

To keep credentials secure, the following GitHub Secrets were configured:

- `SERVER_IP`
- `SERVER_USER`
- `SSH_PRIVATE_KEY`

No sensitive credentials are stored in the repository.

---

## Skills Demonstrated

- CI/CD Pipeline Implementation
- GitHub Actions
- AWS EC2 Administration
- Linux Command Line
- SSH Authentication
- NGINX Configuration
- Git Version Control
- Deployment Automation

---

## Screenshots

### Successful GitHub Actions Workflow

<img width="1313" height="536" alt="hyggffn" src="https://github.com/user-attachments/assets/39e67d8b-c0ab-4033-ab0e-4159e1fc5b35" />

### Deployment Workflow

<img width="942" height="564" alt="jjjj" src="https://github.com/user-attachments/assets/49fe8028-6544-4883-8128-61bfc42e727a" />


---

## Challenges Encountered

The first deployment attempt failed due to workflow configuration issues. After troubleshooting and updating the deployment workflow, the pipeline executed successfully and automated deployments worked as expected.

This project strengthened my understanding of GitHub Actions, Linux administration, SSH authentication, and deployment automation.

---

## Future Improvements

- Add automated testing before deployment
- Dockerize the application
- Configure monitoring and logging
- Implement Infrastructure as Code using Terraform
