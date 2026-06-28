# 🚀 End-to-End DevOps CI/CD Pipeline on AWS EKS

## 📌 Project Overview

This project demonstrates a complete DevOps implementation for deploying a containerized web application on AWS EKS using modern DevOps tools and practices.

The solution automates infrastructure provisioning, configuration management, continuous integration, continuous deployment, security scanning, and monitoring.

---

## 🏗️ Architecture

```text
Developer
    │
    ▼
 GitHub Repository
    │
    ▼
 Jenkins CI/CD Pipeline
    │
 ┌──┴───────────────┐
 │                  │
 ▼                  ▼
SonarQube      OWASP Dependency Check
Code Analysis  Vulnerability Scan
 │
 ▼
Trivy Security Scan
 │
 ▼
Docker Build
 │
 ▼
Docker Hub / AWS ECR
 │
 ▼
AWS EKS Cluster
 │
 ▼
Kubernetes Deployment
 │
 ▼
Prometheus + Grafana Monitoring
```

---

# 🛠️ Tools & Technologies

| Category                 | Tools                  |
| ------------------------ | ---------------------- |
| Cloud Provider           | AWS                    |
| Infrastructure as Code   | Terraform              |
| Configuration Management | Ansible                |
| CI/CD                    | Jenkins                |
| Containerization         | Docker                 |
| Container Registry       | Docker Hub / AWS ECR   |
| Orchestration            | Kubernetes (EKS)       |
| Code Quality             | SonarQube              |
| Security Scan            | Trivy                  |
| Dependency Scan          | OWASP Dependency Check |
| Monitoring               | Prometheus             |
| Visualization            | Grafana                |
| Version Control          | Git & GitHub           |

---

# 📂 Project Structure

```text
project-root/
│
├── terraform/
│   ├── ec2.tf
│   ├── variables.tf
│   ├── outputs.tf
│   └── terraform.tf
│
├── ansible/
│   ├── hosts.ini
│   └── basic_setup.yml
│
├── kubernetes/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── ingress.yaml
│
├── Jenkinsfile
│
├── Dockerfile
│
└── README.md
```

---

# 🎯 Project Objectives

✅ Automate AWS infrastructure provisioning using Terraform

✅ Configure servers automatically using Ansible

✅ Implement CI/CD pipeline using Jenkins

✅ Deploy application to AWS EKS

✅ Perform Security & Vulnerability Scanning

✅ Monitor application and infrastructure health

✅ Achieve Infrastructure as Code (IaC)

---

# ☁️ AWS Infrastructure

The following AWS resources are provisioned:

* VPC
* Subnets
* Security Groups
* EC2 Instance (Jenkins Master)
* EKS Cluster
* S3 Bucket (Terraform State)
* IAM Roles & Policies

---

# 🐳 Dockerization

Build Docker Image:

```bash
docker build -t my-app .
```

Run Container:

```bash
docker run -d -p 3000:3000 my-app
```

---

# ⚙️ Terraform Deployment

Initialize Terraform:

```bash
terraform init
```

Validate Configuration:

```bash
terraform validate
```

Review Changes:

```bash
terraform plan
```

Create Infrastructure:

```bash
terraform apply -auto-approve
```

Destroy Infrastructure:

```bash
terraform destroy -auto-approve
```

---

# 🤖 Ansible Configuration

Verify Connectivity:

```bash
ansible ubuntu_servers -i hosts.ini -m ping
```

Run Playbook:

```bash
ansible-playbook -i hosts.ini basic_setup.yml
```

The playbook installs:

* Docker
* Docker Compose
* Jenkins
* AWS CLI
* kubectl
* eksctl
* Trivy

---

# 🔧 Jenkins Setup

Access Jenkins:

```text
http://<EC2-PUBLIC-IP>:8080
```

Install Plugins:

* Docker
* Pipeline Stage View
* SonarQube Scanner
* OWASP Dependency Check
* GitHub Integration

---

# 🔍 SonarQube Integration

Run SonarQube:

```bash
docker run -d \
--name sonarqube \
-p 9000:9000 \
sonarqube:lts-community
```

Access:

```text
http://<EC2-PUBLIC-IP>:9000
```

Features:

* Static Code Analysis
* Code Smells Detection
* Bug Detection
* Quality Gates

---

# 🛡️ Security Scanning

## OWASP Dependency Check

Detect vulnerable dependencies before deployment.

## Trivy Scan

Filesystem Scan:

```bash
trivy fs .
```

Docker Image Scan:

```bash
trivy image my-image:latest
```

---

# ☸️ Kubernetes Deployment

Deploy Application:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

Check Pods:

```bash
kubectl get pods
```

Check Services:

```bash
kubectl get svc
```

---

# 📊 Monitoring

## Prometheus

Collects:

* Node Metrics
* Container Metrics
* Kubernetes Metrics

## Grafana

Provides dashboards for:

* CPU Usage
* Memory Usage
* Pod Health
* Cluster Performance

---

# 🚀 CI/CD Pipeline Stages

### Stage 1: Source Code Checkout

```text
GitHub → Jenkins
```

### Stage 2: Code Quality Analysis

```text
SonarQube Scan
```

### Stage 3: Dependency Vulnerability Scan

```text
OWASP Dependency Check
```

### Stage 4: Security Scan

```text
Trivy Scan
```

### Stage 5: Build Docker Image

```text
Docker Build
```

### Stage 6: Push Image

```text
Docker Hub / AWS ECR
```

### Stage 7: Deploy to EKS

```text
Kubernetes Deployment
```

### Stage 8: Monitoring

```text
Prometheus + Grafana
```

---


# 📈 Key Features

* Fully Automated CI/CD Pipeline
* Infrastructure as Code
* Security Scanning
* Code Quality Analysis
* Kubernetes Deployment
* AWS EKS Integration
* Monitoring & Alerting
* Production Ready Architecture

---

# 🏆 Learning Outcomes

Through this project I gained hands-on experience with:

* Terraform
* Ansible
* Jenkins
* Docker
* Kubernetes
* AWS EKS
* SonarQube
* Trivy
* Prometheus
* Grafana
* CI/CD Best Practices

---

# 👨‍💻 Author

**Bharath RM**

DevOps Engineer | Cloud Enthusiast | Kubernetes Practitioner

GitHub: https://github.com/bharathrm555

This repository contains the Capstone Project completed collaboratively by *Group 1 (Batch 14)* as part of the HeroVired Multi-Cloud Architecture & DevOps Program.

Our team worked together throughout the project by following the official capstone guidelines, performing all required hands-on practical implementations, and applying DevOps best practices to build a complete end-to-end CI/CD pipeline for a containerized web application on AWS EKS.

The project covers Infrastructure as Code, configuration management, continuous integration and deployment, containerization, Kubernetes orchestration, security scanning, and monitoring using industry-standard DevOps tools.

*Group Members:*

* Bharath RM



---



# steps followed

Step-1 Create new Iam user

Go to aws console->IAM-> create user

![alt text](Image_assets/image.png)

![alt text](Image_assets/image-1.png)

![alt text](Image_assets/image-2.png)

![alt text](Image_assets/image-3.png)

![alt text](Image_assets/image-4.png)

configuring aws in local computer

aws configure

![alt text](Image_assets/image-5.png)

Enter your credentials for the newly create IAM user as above

Step-2 creating an jenkinsmaster ec2 instance using terraform

Ec2.tf

Step-2 creating an jenkinsmaster ec2 instance using terraform
Ec2.tf
provider "tls" {}

resource "tls_private_key" "generated" {
  algorithm = "RSA"
  rsa_bits  = 4096
}

resource "aws_key_pair" "deployer" {
  key_name   = "capstone-user-key"
  public_key = tls_private_key.generated.public_key_openssh
}

resource "local_file" "private_key" {
  content         = tls_private_key.generated.private_key_pem
  filename        = "${path.module}/capstone-user-key.pem"
  file_permission = "0400"
}

resource "aws_default_vpc" "default" {

}

resource "aws_security_group" "allow_user_to_connect" {
  name        = "allow TLS"
  description = "Allow user to connect"
  vpc_id      = aws_default_vpc.default.id
  ingress {
    description = "port 22 allow"
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    description = " allow all outgoing traffic "
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }

  ingress {
    description = "port 80 allow"
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

   ingress {
    description = "port 8080 jenkins allow"
    from_port   = 8080
    to_port     = 8080
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  ingress {
    description = "port 443 allow"
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  tags = {
    Name = "mysecurity"
  }
}

resource "aws_instance" "jenkinsmaster" {
  ami             = var.ami_id
  instance_type   = var.instance_type
  key_name        = aws_key_pair.deployer.key_name
  security_groups = [aws_security_group.allow_user_to_connect.name]
  tags = {
    Name = "jenkinsmaster"
  }
  root_block_device {
    volume_size = 30 
    volume_type = "gp3"
  }
}

Terraform.tf
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "5.65.0"
    }
  }
}

provider "aws" {
  region = var.aws_region
}


Outputs.tf
output "ec2_public_ip" {
  description = "Public IP of the EC2 instance"
  value       = aws_instance.jenkinsmaster.public_ip
}


Variables.tf
variable "aws_region" {
  description = "AWS region where resources will be provisioned"
  default     = "ap-south-1"
}

variable "ami_id" {
  description = "AMI ID for the EC2 instance"
  default     = "ami-07a00cf47dbbc844c"
}

variable "instance_type" {
  description = "Instance type for the EC2 instance"
  default     = "t2.large"
}


Commands to execute above files

a.	Terraform init

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/39df7416-48e9-4d71-8a43-359b85fa71d7" />

b.	Terraform plan

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/49d0f847-a58f-4d89-8a6c-3f859be684b4" />


c.	Terraform apply

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/3e5dc33c-e70a-431d-bfcf-d100f4006c4f" />

Output:

![alt text](Image_assets/image-6.png)

Step-3 : configuring following on Jenkins master using Ansible configuration management Tool

IMP: After creation of  ec2-instance as in previous step update public ip in hosts.ini in ansible folder

•	docker
•	docker-compose-v2
•	jenkins
•	awscli
•	kubectl
•	eksctl
•	trivy

Hosts.ini

[ubuntu_servers]
jenkinsmaster ansible_host=65.2.122.131
[ubuntu_servers:vars]
ansible_user=ubuntu
ansible_ssh_private_key_file=~/capstone-user-key.pem
ansible_ssh_common_args='-o StrictHostKeyChecking=no'

basic_setup.yml
---
- name: Setup Docker, Docker Compose v2 and Jenkins on Ubuntu 24
  hosts: all
  become: yes

  vars:
    jenkins_keyring: /etc/apt/keyrings/jenkins-keyring.asc
    docker_keyring: /etc/apt/keyrings/docker.gpg

  tasks:

    # -----------------------------
    # SYSTEM UPDATE
    # -----------------------------
    - name: Update apt cache
      apt:
        update_cache: yes

    - name: Install required packages
      apt:
        name:
          - ca-certificates
          - curl
          - gnupg
          - lsb-release
        state: present

    # -----------------------------
    # DOCKER INSTALLATION
    # -----------------------------
    - name: Ensure keyrings directory exists
      file:
        path: /etc/apt/keyrings
        state: directory
        mode: '0755'

    - name: Download Docker GPG key
      get_url:
        url: https://download.docker.com/linux/ubuntu/gpg
        dest: /tmp/docker.asc

    - name: Convert Docker GPG key
      command: gpg --dearmor -o {{ docker_keyring }} /tmp/docker.asc
      args:
        creates: "{{ docker_keyring }}"

    - name: Add Docker repository
      apt_repository:
        repo: "deb [arch=amd64 signed-by={{ docker_keyring }}] https://download.docker.com/linux/ubuntu {{ ansible_distribution_release }} stable"
        state: present
        filename: docker

    - name: Update apt cache after Docker repo
      apt:
        update_cache: yes

    - name: Install Docker Engine & plugins
      apt:
        name:
          - docker-ce
          - docker-ce-cli
          - containerd.io
          - docker-buildx-plugin
          - docker-compose-plugin
        state: latest

    - name: Start and enable Docker
      systemd:
        name: docker
        state: started
        enabled: yes

    - name: Add ubuntu user to docker group
      user:
        name: ubuntu
        groups: docker
        append: yes

    # -----------------------------
    # JAVA INSTALLATION
    # -----------------------------
    - name: Install Java and fontconfig
      apt:
        name:
          - fontconfig
          - openjdk-21-jre
        state: present

    # -----------------------------
    # JENKINS INSTALLATION
    # -----------------------------
    - name: Download Jenkins GPG key
      get_url:
        url: https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
        dest: "{{ jenkins_keyring }}"
        mode: '0644'

    - name: Add Jenkins repository
      apt_repository:
        repo: "deb [signed-by={{ jenkins_keyring }}] https://pkg.jenkins.io/debian-stable binary/"
        state: present
        filename: jenkins

    - name: Update apt cache after Jenkins repo
      apt:
        update_cache: yes

    - name: Install Jenkins
      apt:
        name: jenkins
        state: present

    - name: Enable and start Jenkins
      systemd:
        name: jenkins
        state: started
        enabled: yes

    # -----------------------------
    # PERMISSIONS & RESTARTS
    # -----------------------------
    - name: Add jenkins user to docker group
      user:
        name: jenkins
        groups: docker
        append: yes

    - name: Restart Docker
      systemd:
        name: docker
        state: restarted

    - name: Restart Jenkins
      systemd:
        name: jenkins
        state: restarted

    # -----------------------------
    # CLEANUP
    # -----------------------------
    - name: Remove temporary files
      file:
        path: "{{ item }}"
        state: absent
      loop:
        - /tmp/docker.asc

# -----------------------------
# AWS CLI INSTALLATION (your steps converted)
# -----------------------------

    - name: Install unzip dependency
      apt:
        name: unzip
        state: present
        update_cache: yes

    - name: Download AWS CLI v2 zip
      get_url:
        url: https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip
        dest: /tmp/awscliv2.zip

    - name: Extract AWS CLI zip
      unarchive:
        src: /tmp/awscliv2.zip
        dest: /tmp/
        remote_src: yes

    - name: Install AWS CLI v2
      command: >
        /tmp/aws/install -i /usr/local/aws-cli -b /usr/local/bin --update
      args:
        creates: /usr/local/bin/aws

    - name: Verify AWS CLI installation
      command: aws --version
      register: aws_output
      changed_when: false

    - debug:
        var: aws_output.stdout


    

    # -----------------------------
    # CLEANUP
    # -----------------------------
    - name: Remove AWS CLI temp files
      file:
        path: "{{ item }}"
        state: absent
      loop:
        - /tmp/aws
        - /tmp/awscliv2.zip

# -----------------------------
# KUBECTL INSTALLATION
# -----------------------------

    - name: Download kubectl binary
      get_url:
        url: https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl
        dest: /tmp/kubectl
        mode: '0755'

    - name: Move kubectl to /usr/local/bin
      command: mv /tmp/kubectl /usr/local/bin/kubectl
      args:
        creates: /usr/local/bin/kubectl

    - name: Verify kubectl installation
      command: kubectl version --client --short
      register: kubectl_output
      changed_when: false

    - debug:
        var: kubectl_output.stdout

# -----------------------------
# EKSCTL INSTALLATION
# -----------------------------

    - name: Download eksctl tar.gz
      get_url:
        url: https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_Linux_amd64.tar.gz
        dest: /tmp/eksctl.tar.gz

    - name: Extract eksctl binary
      unarchive:
        src: /tmp/eksctl.tar.gz
        dest: /tmp/
        remote_src: yes

    - name: Move eksctl to /usr/local/bin
      command: mv /tmp/eksctl /usr/local/bin/eksctl
      args:
        creates: /usr/local/bin/eksctl

    - name: Verify eksctl installation
      command: eksctl version
      register: eksctl_output
      changed_when: false

    - debug:
        var: eksctl_output.stdout

    # -----------------------------
    # CLEANUP
    # -----------------------------
    - name: Remove eksctl temp files
      file:
        path: "{{ item }}"
        state: absent
      loop:
        - /tmp/eksctl
        - /tmp/eksctl.tar.gz

    # -----------------------------
    # TRIVY INSTALLATION
    # -----------------------------

    - name: Remove old Trivy repo (if exists)
      file:
        path: /etc/apt/sources.list.d/trivy.list
        state: absent

    - name: Remove old Trivy keyring
      file:
        path: /usr/share/keyrings/trivy.gpg
        state: absent

    - name: Download Trivy GPG key (ASCII)
      get_url:
        url: https://aquasecurity.github.io/trivy-repo/deb/public.key
        dest: /tmp/trivy.asc

    - name: Convert Trivy key to GPG (IMPORTANT)
      command: >
        gpg --dearmor -o /usr/share/keyrings/trivy.gpg /tmp/trivy.asc
      args:
        creates: /usr/share/keyrings/trivy.gpg

    - name: Add Trivy repository
      apt_repository:
        repo: "deb [signed-by=/usr/share/keyrings/trivy.gpg] https://aquasecurity.github.io/trivy-repo/deb {{ ansible_distribution_release }} main"
        state: present
        filename: trivy

    - name: Update apt cache
      apt:
        update_cache: yes

    - name: Install Trivy
      apt:
        name: trivy
        state: present



Connecting ec2 instance from local ubuntu terminal
If using windows pc than install Ubuntu terminal from internet


<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/425d7f9c-b039-493c-96dd-7870e2632bc2" />

Open ubuntu terminal  
Go to terraform folder
cd /mnt/c/Users/Admin/Desktop/herovired/Hero-capstone-project/terraform

copy capstone-user-key.pem to ~/ location (home location)
cp capstone-user-key.pem ~/

change the permission
chmod 400 ~/capstone-user-key.pem

go to ansible folder
cd /mnt/c/Users/Admin/Desktop/herovired/Hero-capstone-project/ansible

check for the connectivity
ansible ubuntu_servers -i hosts.ini -m ping

run basic-setup.yml file using below command in ubuntu terminal
ansible-playbook -i hosts.ini basic-setup.yml



output:
bharath@DEN-01:/mnt/c/Users/Admin/Desktop/herovired/Hero-capstone-project/ansible$ ansible ubuntu_servers -i hosts.ini -m ping
jenkinsmaster | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
bharath@DEN-01:/mnt/c/Users/Admin/Desktop/herovired/Hero-capstone-project/ansible$ ansible-playbook -i hosts.ini basic-setup.yml

PLAY [Setup Docker, Docker Compose v2 and Jenkins on Ubuntu 24] ********************************************************************************************************
TASK [Gathering Facts] *************************************************************************************************************************************************ok: [jenkinsmaster]

TASK [Update apt cache] ************************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Install required packages] ***************************************************************************************************************************************ok: [jenkinsmaster]

TASK [Ensure keyrings directory exists] ********************************************************************************************************************************ok: [jenkinsmaster]

TASK [Download Docker GPG key] *****************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Convert Docker GPG key] ******************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Add Docker repository] *******************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Update apt cache after Docker repo] ******************************************************************************************************************************changed: [jenkinsmaster]

TASK [Install Docker Engine & plugins] *********************************************************************************************************************************changed: [jenkinsmaster]

TASK [Start and enable Docker] *****************************************************************************************************************************************ok: [jenkinsmaster]

TASK [Add ubuntu user to docker group] *********************************************************************************************************************************changed: [jenkinsmaster]

TASK [Install Java and fontconfig] *************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Download Jenkins GPG key] ****************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Add Jenkins repository] ******************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Update apt cache after Jenkins repo] *****************************************************************************************************************************changed: [jenkinsmaster]

TASK [Install Jenkins] *************************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Enable and start Jenkins] ****************************************************************************************************************************************ok: [jenkinsmaster]

TASK [Add jenkins user to docker group] ********************************************************************************************************************************changed: [jenkinsmaster]

TASK [Restart Docker] **************************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Restart Jenkins] *************************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Remove temporary files] ******************************************************************************************************************************************changed: [jenkinsmaster] => (item=/tmp/docker.asc)

TASK [Install unzip dependency] ****************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Download AWS CLI v2 zip] *****************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Extract AWS CLI zip] *********************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Install AWS CLI v2] **********************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Verify AWS CLI installation] *************************************************************************************************************************************ok: [jenkinsmaster]

TASK [debug] ***********************************************************************************************************************************************************ok: [jenkinsmaster] => {
    "aws_output.stdout": "aws-cli/2.34.63 Python/3.14.5 Linux/7.0.0-1004-aws exe/x86_64.ubuntu.26"
}

TASK [Remove AWS CLI temp files] ***************************************************************************************************************************************changed: [jenkinsmaster] => (item=/tmp/aws)
changed: [jenkinsmaster] => (item=/tmp/awscliv2.zip)

TASK [Download kubectl binary] *****************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Move kubectl to /usr/local/bin] **********************************************************************************************************************************changed: [jenkinsmaster]

TASK [Verify kubectl installation] *************************************************************************************************************************************ok: [jenkinsmaster]

TASK [debug] ***********************************************************************************************************************************************************ok: [jenkinsmaster] => {
    "kubectl_output.stdout": "Client Version: v1.19.6-eks-49a6c0"
}

TASK [Download eksctl tar.gz] ******************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Extract eksctl binary] *******************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Move eksctl to /usr/local/bin] ***********************************************************************************************************************************changed: [jenkinsmaster]

TASK [Verify eksctl installation] **************************************************************************************************************************************ok: [jenkinsmaster]

TASK [debug] ***********************************************************************************************************************************************************ok: [jenkinsmaster] => {
    "eksctl_output.stdout": "0.227.0"
}

TASK [Remove eksctl temp files] ****************************************************************************************************************************************ok: [jenkinsmaster] => (item=/tmp/eksctl)
changed: [jenkinsmaster] => (item=/tmp/eksctl.tar.gz)

TASK [Remove old Trivy repo (if exists)] *******************************************************************************************************************************ok: [jenkinsmaster]

TASK [Remove old Trivy keyring] ****************************************************************************************************************************************ok: [jenkinsmaster]

TASK [Download Trivy GPG key (ASCII)] **********************************************************************************************************************************changed: [jenkinsmaster]

TASK [Convert Trivy key to GPG (IMPORTANT)] ****************************************************************************************************************************changed: [jenkinsmaster]

TASK [Add Trivy repository] ********************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Update apt cache] ************************************************************************************************************************************************changed: [jenkinsmaster]

TASK [Install Trivy] ***************************************************************************************************************************************************changed: [jenkinsmaster]

PLAY RECAP *************************************************************************************************************************************************************jenkinsmaster              : ok=45   changed=32   unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

bharath@DEN-01:/mnt/c/Users/Admin/Desktop/herovired/Hero-capstone-project/ansible$


![alt text](Image_assets/image-7.png)

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/eac68a9e-82a3-4245-93f5-dd52d2698b8d" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/b925bb1c-1784-45dc-a26c-928503da45f2" />

![alt text](Image_assets/image-8.png)

Verification
-> docker,docker-compose-v2
    docker --version
-> jenkins
   jenkins --version
-> awscli
     aws --version
-> kubectl
   kubectl version --client
-> eksctl
    eksctl version
-> trivy
    trivy –version
    
![alt text](Image_assets/image-9.png)

Step-4. jenkins setup
ports : 22,80,30000-32767,465,25,3000-10000,

![alt text](Image_assets/image-10.png)

Open in browser
http://public_ip:8080

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/487bf3ab-15cc-451c-8f24-054bc2618e7f" />

Generate password: username is admin by default

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/559557e9-5b9b-4329-9f24-1cce55cdd30e" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/710262fe-b053-4c1b-aaf8-9603f2b4ae54" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/3eead453-2693-46ed-9e77-31e21649684f" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/1d42f9c7-d934-427e-b2de-30cde601762c" />

Step 5 Pluggin installation
 Go to Jenkins Master 
Manage Jenkins --> Plugins --> Available plugins 
install the below plugins:
   Docker
   Pipeline: Stage View
   OWASP dependency check
   SonarQube Scanner


<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/2ee15fa3-dca7-4275-b8d2-5b693893d38e" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/6873a985-d204-4494-83e6-247b142ebe6a" />

Step 6. OWASP setup
install OWASP plugin (already installed in step 5)

jenkins tools- OWASP dependency check

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/2f106c04-88d2-4a1d-837a-ae44b570d2bc" />

Step 7: Jenkins-Github integration
•	Go to Github.com
•	Profile->Settings->developer settings
•	Create new token

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/7437fb20-1764-41f0-8d2e-cdcd4f9973ba" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/81e8d05b-4f41-4bd1-9968-444bfd362322" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/ac8bdb11-1590-487c-b197-03ada2fb27d2" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/4bdfb523-8afa-4696-bdd2-e0e4bfe82213" />

Go to
Manage Jenkins->credentials

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/6afc5f3d-c639-48cf-bc9d-f3aa8c641c94" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/ba4ea217-e2be-4123-b5e6-6935ceeac627" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f1681bd7-534f-427a-a84d-9c7e4ae479dd" />

Step-8 Jenkins-DockerHub integration
Go to dockerhub.com and login
Click on Account settings 

![alt text](Image_assets/image-11.png)

Click personal access tokens on left

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/5d909d82-a41a-4554-99db-53ca740351de" />

Click on Generate New token

![alt text](Image_assets/image-12.png)

Give some name
And click Generate
Copy new token

![alt text](Image_assets/image-13.png)

Go to Jenkins-> manage Jenkins->credentials
Click on credentials
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/ab8cd4f8-efd7-486e-8e21-be2d9b957baa" />

Click on Add credentials

![alt text](Image_assets/image-14.png)

![alt text](Image_assets/image-15.png)

Step 9: Sonarqube setup

install SonarQube Scanner

 sudo docker run -itd --name SonarQube-Server -p 9000:9000 sonarqube:lts-community
 
open in browser

   http://public_ip:9000

generate sonar-token in sonarcube portal

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/9f4d12f0-90d4-4d23-8255-0d19d4015d16" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/752e69ee-5bb5-4935-8cc1-ac790b731c71" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f43b53fc-210e-4b93-bed4-86dbfc207630" />

Jenkins->manage Jenkins->tools

Look for Sonarqube scanner and fill detail as below and save

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/fcd52687-e106-4ee6-a5d4-882648119867" />

Go to sonarqube server->administration->security->users

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/0d71e473-238d-4da3-be8f-c60e83732fc0" />

Click on update tokens

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/65122b23-2476-4db8-8280-95fbd0583d73" />

Give name and then generate token and then copy it

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/260f09ed-ec36-424c-b30c-f45691a10dfb" />

Now Go to

Manage jenkins->credentials

Click on Credentials

![alt text](Image_assets/image-16.png)

![alt text](Image_assets/image-17.png)

Manage jenkins->system

Look for sonarqube installations fill as below and then save

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f6f53c9d-6d43-4375-906c-8a76e007a548" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/e3888e9f-b4a4-4a9c-be04-1a83114458bb" />

Now go sonarqube server

Administration->configuration->webhooks

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/69818266-7c45-44c2-909d-43c1743aa96d" />

Click on create

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/53762153-b9fc-40cc-9ca2-7d564f86d875" />

Fill as shown

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/e42a0d85-913a-4ff3-aa0e-b1c136836241" />

Click create

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/4ce6b61a-b012-472e-a7db-697e20b3483b" />


Step:10 Email-setup
Go to gmail.com
Profile-> manage account

![alt text](Image_assets/image-18.png)

Click security and signin in left

![alt text](Image_assets/image-19.png)

Search app password in searchbox and click

![alt text](Image_assets/image-20.png)

Give some name and create

![alt text](Image_assets/image-21.png)

Go to Manage jenkins->credentials

Click credentials

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/a51f4a62-e1ea-448f-8edb-70b646c0e971" />

Manage-jenkins->system click system


<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/e33fd79b-cfba-477d-9aff-7030b99cc9a6" />

Fill as below

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/dde24740-f7b0-4889-8af2-8b0a4f188506" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/d96494aa-8c18-45d4-8cc9-5878c9aff87f" />

Check for test email in gmail inbox


<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/b57fea70-b418-4804-a026-beedd305582a" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/2fd99b9c-2a9b-42b3-8156-91a22ceac338" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/737de889-8916-4025-bf55-dae4168fe9f6" />

Step-11 eks cluster setup (manual)
Create EKS Cluster (Master machine)

-->create iam role

12.  Go to:
👉 AWS Console → IAM → Roles → Create Role

Trusted entity: EC2
Attach policies:
AmazonEKSClusterPolicy
AmazonEKSWorkerNodePolicy
AmazonEC2ContainerRegistryReadOnly
AmazonEKS_CNI_Policy
administratoraccess

Name:
eksctl-ec2-role

Step 2: Attach Role to EC2
Go to EC2 → Instances
Select your instance (jenkinsmaster)

Click:
Actions → Security → Modify IAM role
Attach:
eksctl-ec2-role
Step 3: Verify Role

![alt text](Image_assets/image-22.png)

![alt text](Image_assets/image-23.png)

![alt text](Image_assets/image-24.png)

-->create cluster
eksctl create cluster --name=shopnow-cluster --region=ap-south-1 --version=1.30 --without-nodegroup

![alt text](Image_assets/image-25.png)

aws eks list-clusters --region ap-south-1

![alt text](Image_assets/image-26.png)


-->make eks-nodegroup-key keypair

![alt text](Image_assets/image-27.png)

-->Associate IAM OIDC Provider (Master machine)
eksctl utils associate-iam-oidc-provider \
  --region ap-south-1 \
  --cluster shopnow-cluster \
  --approve

![alt text](Image_assets/image-28.png)

-->Create Nodegroup (Master machine)
eksctl create nodegroup --cluster=shopnow-cluster \
                     --region=ap-south-1 \
                     --name=shopnow \
                     --node-type=t2.large \
                     --nodes=2 \
                     --nodes-min=2 \
                     --nodes-max=2 \
                     --node-volume-size=29 \
                     --ssh-access \
                     --ssh-public-key=eks-nodegroup-key

![alt text](Image_assets/image-29.png)

kubectl get nodes

![alt text](Image_assets/image-30.png)


Step 12 Argocd setup

kubectl create namespace argocd

![alt text](Image_assets/image-31.png)

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

![alt text](Image_assets/image-32.png)

kubectl get pods -n argocd

![alt text](Image_assets/image-33.png)

sudo curl --silent --location -o /usr/local/bin/argocd https://github.com/argoproj/argo-cd/releases/download/v2.4.7/argocd-linux-amd64

![alt text](Image_assets/image-34.png)


sudo chmod +x /usr/local/bin/argocd

![alt text](Image_assets/image-35.png)

kubectl get svc -n argocd

![alt text](Image_assets/image-36.png)


kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "NodePort"}}'

![alt text](Image_assets/image-37.png)

kubectl get svc -n argocd

allow port in security group of node 

![alt text](Image_assets/image-38.png)

Access it on browser, click on advance and proceed with
<public-ip-worker>:<port>
![alt text](Image_assets/image-39.png)

Fetch the initial password of argocd server

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/3e902f4a-6581-4a82-8420-3ebff6f0a53c" />

![alt text](Image_assets/image-40.png)

Username: admin
Now, go to User Info and update your argocd password

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/4de78d90-c9aa-4c20-987c-c5dc723548d2" />

add github repo in settings repositories

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/1100eb27-9eea-4364-88dc-84abf499e90d" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/1c5f4b3a-366d-4b2f-8762-d436f2ec1f18" />

adding clusters in argocd
argocd login 52.66.204.159:30424 --username admin

![alt text](Image_assets/image-41.png)

argocd cluster list
![alt text](Image_assets/image-42.png)

kubectl config get-contexts
![alt text](Image_assets/image-43.png)

argocd cluster add i-0560ef021d79e121d@shopnow-cluster.ap-south-1.eksctl.io --name shopnow-eks-cluster

![alt text](Image_assets/image-44.png)
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/9f6876d2-6fa8-469d-aafe-48de3693761b" />

Step 13 installation of nginx controller
Install ingress-nginx controller (for external access)
# For EKS, other cloud provider will have different file
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.12.0-beta.0/deploy/static/provider/aws/deploy.yaml

# For local development (minikube/kind/Docker Desktop)
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.1/deploy/static/provider/kind/deploy.yaml

![alt text](Image_assets/image-45.png)

•	kubectl get pods -n kube-system

![alt text](Image_assets/image-46.png)

•	kubectl get pods -n ingress-nginx

![alt text](Image_assets/image-47.png)

•	kubectl top nodes  # Should work after metrics server is running

![alt text](Image_assets/image-48.png)

•	kubectl top pods  # Should work after metrics server is running

![alt text](Image_assets/image-49.png)

kubectl create namespace shopnow-demo

![alt text](Image_assets/image-50.png)

ArgoCD GitOps
Git clone https://github.com/bharathrm555/Capestone_project_HVRD.git

![alt text](Image_assets/image-51.png)

Go to Hero-capstone-project/kubrnetes/argocd
# Deploy applications
kubectl apply -f kubernetes/argocd/umbrella-application.yaml

kubectl get applications -n argocd

![alt text](Image_assets/image-52.png)
 
kubectl get pods -n shopnow-demo
![alt text](Image_assets/image-53.png)


User creation in mongodb
•	# Run below commands
•	use admin;
•	db.createUser({
•	  user: 'shopuser',
•	  pwd: 'ShopNowPass123',
•	  roles: [
•	    { role: 'readWrite', db: 'shopnow' },
•	    { role: 'dbAdmin', db: 'shopnow' }
•	  ]
•	});
•	exit


![alt text](Image_assets/image-54.png)

![alt text](Image_assets/image-55.png)

# Restart backend deployment
kubectl rollout restart deploy backend -n shopnow-demo

![alt text](Image_assets/image-56.png)

kubectl get pods -n shopnow-demo

![alt text](Image_assets/image-57.png)


kubectl get deploy -n shopnow-demo
![alt text](Image_assets/image-58.png)

kubectl get svc -n shopnow-demo

![alt text](Image_assets/image-59.png)
 
kubectl get statefulsets -n shopnow-demo
![alt text](Image_assets/image-60.png)

kubectl get hpa -n shopnow-demo

![alt text](Image_assets/image-61.png)

kubectl get cm -n shopnow-demo

![alt text](Image_assets/image-62.png)

kubectl get secrets -n shopnow-demo

![alt text](Image_assets/image-63.png)

kubectl get ing -n shopnow-demo

![alt text](Image_assets/image-64.png)

Step 14: Monitoring using Prometheus and graffana
Install Helm Chart
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3


chmod 700 get_helm.sh
./get_helm.sh

Add Helm Stable Charts for Your Local Client
helm repo add stable https://charts.helm.sh/stable

Add Prometheus Helm Repository
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

Create Prometheus Namespace
kubectl create namespace prometheus
kubectl get ns
Install Prometheus using Helm
helm install stable prometheus-community/kube-prometheus-stack -n Prometheus

Verify prometheus installation
kubectl get pods -n Prometheus

Check the services file (svc) of the Prometheus
kubectl get svc -n Prometheus

Expose Prometheus and Grafana to the external world through Node Port
Important

change it from Cluster IP to NodePort after changing make sure you save the file and open the assigned nodeport to the service.

kubectl edit svc stable-kube-prometheus-sta-

Verify service
kubectl get svc -n Prometheus

Now,let’s change the SVC file of the Grafana and expose it to the outer world
kubectl edit svc stable-grafana -n prometheus

Check grafana service
kubectl get svc -n prometheus
Get a password for grafana
kubectl get secret --namespace prometheus stable-grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
Note

![alt text](Image_assets/image-65.png)

![alt text](Image_assets/image-66.png)

![alt text](Image_assets/image-67.png)

![alt text](Image_assets/image-68.png)

![alt text](Image_assets/image-69.png)

![alt text](Image_assets/image-70.png)
![alt text](Image_assets/image-71.png)
![alt text](Image_assets/image-72.png)

Username: admin

http://52.66.204.159:30780/query
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/119f781c-a5a1-485b-bf5e-3f6d78ffcbd2" />

http://52.66.204.159:30727/login

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/cc354ff2-b516-48d3-9307-b1a577b63e6a" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/7382fcc0-f74b-40c1-a08f-bc6867988984" />
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/5c5266ba-5c56-4381-b53f-9e30835c2018" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/97399c5e-e766-4827-9a8d-835032c76c8c" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/36573059-c0c8-441f-973d-b77007102243" />

Step : 15 : shared Library setup
Shared library github repo: 
https://github.com/bharathrm555/Capestone_project_HVRD.git
Go to manage Jenkins->system
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/8eb4babf-d3d2-42a9-b8fa-b0553019d622" />


Look for Global Trusted Pipeline Libraries
Fill as given below
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/e7776ed7-45b8-483a-bc25-c0b350969256" />

Save

Now usage of shared library
Insert @Library('Shared') _ at the beginning of pipeline








Creating a jenkins job-  capstone-CI
capstone-CI

@Library('Shared') _
pipeline {
    agent any
    
    environment{
        SONAR_HOME = tool "Sonar"
    }
    
    parameters {
        string(name: 'ADMIN_DOCKER_TAG', defaultValue: '', description: 'Setting docker image for latest push')
        string(name: 'FRONTEND_DOCKER_TAG', defaultValue: '', description: 'Setting docker image for latest push')
        string(name: 'BACKEND_DOCKER_TAG', defaultValue: '', description: 'Setting docker image for latest push')
    }
    
    stages {
        stage("Validate Parameters") {
            steps {
                script {
                    if (params.FRONTEND_DOCKER_TAG == '' || params.BACKEND_DOCKER_TAG == '' || params.ADMIN_DOCKER_TAG == '') {
                        error("ADMIN_DOCKER_TAG, FRONTEND_DOCKER_TAG and BACKEND_DOCKER_TAG must be provided.")
                    }
                }
            }
        }
        stage("Workspace cleanup"){
            steps{
                script{
                    cleanWs()
                }
            }
        }
        
        stage('Git: Code Checkout') {
            steps {
                script{
                    code_checkout("https://github.com/bharathrm555/Capestone_project_HVRD.git","main")
                }
            }
        }
        
        stage("Trivy: Filesystem scan"){
            steps{
                script{
                    trivy_scan()
                }
            }
        }

stage("OWASP: Dependency check"){
            steps{
                script{
                    owasp_dependency()
                }
            }
        }

 
        
        stage("SonarQube: Code Analysis"){
            steps{
                script{
                    sonarqube_analysis("Sonar", "Hero-Capstone-Project", "hero-capstone-project")
                }
            }
        }
        
        stage("SonarQube: Code Quality Gates"){
            steps{
                script{
                    sonarqube_code_quality()
                }
            }
        }
             
            
        
        
        stage("Docker: Build Images"){
            steps{
                script{
                        dir('admin'){
                            docker_build("shopnow-admin","${params.ADMIN_DOCKER_TAG}","bharathrm247")
                        }
                    
                        dir('backend'){
                            docker_build("shopnow-backend","${params.BACKEND_DOCKER_TAG}","bharathrm247")
                        }
                    
                        dir('frontend'){
                            docker_build("shopnow-frontend","${params.FRONTEND_DOCKER_TAG}","bharathrm247")
                        }
                }
            }
        }
        
        stage("Docker: Push to DockerHub"){
            steps{
                script{
                    docker_push("shopnow-admin","${params.ADMIN_DOCKER_TAG}","bharathrm247") 
                    docker_push("shopnow-backend","${params.BACKEND_DOCKER_TAG}","bharathrm247")
                    docker_push("shopnow-frontend","${params.FRONTEND_DOCKER_TAG}","bharathrm247")
                }
            }
        }
    }
    post{
        success{
        
           build job: "capstone-CD",
	   wait: true,
           propagate: false,
           parameters: [
           string(name: 'ADMIN_DOCKER_TAG', value: "${params.ADMIN_DOCKER_TAG}"),
           string(name: 'FRONTEND_DOCKER_TAG', value: "${params.FRONTEND_DOCKER_TAG}"),
           string(name: 'BACKEND_DOCKER_TAG', value: "${params.BACKEND_DOCKER_TAG}")
           ]
        }
    }
}

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/fd573bde-a38d-4520-b4dc-31124d915096" />


Also create another Jenkins job – capstone-CD
capstone-CD
@Library('Shared') _
pipeline {
    agent any
    
    parameters {
        string(name: 'ADMIN_DOCKER_TAG', defaultValue: '', description: 'Admin Docker tag of the image built by the CI job')
        string(name: 'FRONTEND_DOCKER_TAG', defaultValue: '', description: 'Frontend Docker tag of the image built by the CI job')
        string(name: 'BACKEND_DOCKER_TAG', defaultValue: '', description: 'Backend Docker tag of the image built by the CI job')
    }

    stages {
        stage("Workspace cleanup"){
            steps{
                script{
                    cleanWs()
                }
            }
        }
        
        stage('Git: Code Checkout') {
            steps {
                script{
                    code_checkout("https://github.com/bharathrm555/Capestone_project_HVRD.git","main")
                }
            }
        }
        
        stage('Verify: Docker Image Tags') {
            steps {
                script{
                    echo "ADMIN_DOCKER_TAG: ${params.ADMIN_DOCKER_TAG}"
                    echo "FRONTEND_DOCKER_TAG: ${params.FRONTEND_DOCKER_TAG}"
                    echo "BACKEND_DOCKER_TAG: ${params.BACKEND_DOCKER_TAG}"
                }
            }
        }
        
        
      stage("Update: Helm values.yaml files") {
    steps {
        script {

            dir('kubernetes/helm/charts/admin') {
                sh """
                    sed -i "s/^[[:space:]]*tag:.*/  tag: ${params.ADMIN_DOCKER_TAG}/" values.yaml
                """
            }

            dir('kubernetes/helm/charts/backend') {
                sh """
                    sed -i "s/^[[:space:]]*tag:.*/  tag: ${params.BACKEND_DOCKER_TAG}/" values.yaml
                """
            }

            dir('kubernetes/helm/charts/frontend') {
                sh """
                    sed -i "s/^[[:space:]]*tag:.*/  tag: ${params.FRONTEND_DOCKER_TAG}/" values.yaml
                """
            }
        }
    }
}
        
        stage("Git: Code update and push to GitHub"){
            steps{
                script{
                    withCredentials([gitUsernamePassword(credentialsId: 'Github-cred', gitToolName: 'Default')]) {
                        sh '''
                        echo "Checking repository status: "
                        git status
                    
                        echo "Adding changes to git: "
                        git add .
                        
                        echo "Commiting changes: "
                        git commit -m "Updated environment variables"
                        
                        echo "Pushing changes to github: "
                        git push https://github.com/bharathrm555/Capestone_project_HVRD.git main
                    '''
                    }
                }
            }
        }
    }
  post {
        success {
            script {
                emailext attachLog: true,
                from: 'bethedesigner.247g@gmail.com',
                subject: "Shopnow Application has been updated and deployed - '${currentBuild.result}'",
                body: """
                    <html>
                    <body>
                        <div style="background-color: #FFA07A; padding: 10px; margin-bottom: 10px;">
                            <p style="color: black; font-weight: bold;">Project: ${env.JOB_NAME}</p>
                        </div>
                        <div style="background-color: #90EE90; padding: 10px; margin-bottom: 10px;">
                            <p style="color: black; font-weight: bold;">Build Number: ${env.BUILD_NUMBER}</p>
                        </div>
                        <div style="background-color: #87CEEB; padding: 10px; margin-bottom: 10px;">
                            <p style="color: black; font-weight: bold;">URL: ${env.BUILD_URL}</p>
                        </div>
                    </body>
                    </html>
            """,
            to: 'bethedesigner.247g@gmail.com',
            mimeType: 'text/html'
            }
        }
      failure {
            script {
                emailext attachLog: true,
                from: 'bethedesigner.247g@gmail.com',
                subject: "Shopnow Application build failed - '${currentBuild.result}'",
                body: """
                    <html>
                    <body>
                        <div style="background-color: #FFA07A; padding: 10px; margin-bottom: 10px;">
                            <p style="color: black; font-weight: bold;">Project: ${env.JOB_NAME}</p>
                        </div>
                        <div style="background-color: #90EE90; padding: 10px; margin-bottom: 10px;">
                            <p style="color: black; font-weight: bold;">Build Number: ${env.BUILD_NUMBER}</p>
                        </div>
                    </body>
                    </html>
            """,
            to: 'bethedesigner.247g@gmail.com',
            mimeType: 'text/html'
            }
        }
    }
}

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/b97353d7-14f7-478b-8516-2135a02eadd5" />

Running Capstone-CI job in Jenkins

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/926e5cbf-07ea-4b94-85db-05d2ec651d8f" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/ce36a24e-a831-43bf-b2fc-2e23446cef8f" />

Capstone-CI will automatically trigger capstone-CD

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f4333d74-ddc7-49df-a0af-191dfc2343c5" />

Image updated in dockerhub.com repo by capstone-CI Jenkins job

![alt text](Image_assets/image-73.png)

Version updated automatically in github repo at
kubernetes/helm/charts/admin/values.yaml and frontend,backend etc by capstone-CD Jenkins job
![alt text](Image_assets/image-74.png)

Then argocd will pull the code from github repo and deploy into eks cluster

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/e1071146-65fe-4eca-8ccf-63c8357d20bc" />

Shopnow app frontend will be available at 
http://ac28051b6575f4e289fde2dc87abb669-9807b455609f8957.elb.ap-south-1.amazonaws.com/bharathrm

![alt text](Image_assets/image-75.png)

Shopnow app admin will be available at 
http://ac28051b6575f4e289fde2dc87abb669-9807b455609f8957.elb.ap-south-1.amazonaws.com/bharathrm-admin
![alt text](Image_assets/image-76.png)


Getting success on gmail
![alt text](Image_assets/image-77.png)


Delete Using kubectl (Recommended)

First list apps:

kubectl get applications -n argocd

Delete all applications:

kubectl delete applications --all -n argocd

![alt text](Image_assets/image-78.png)

delete:
eksctl delete nodegroup \
  --cluster=shopnow-cluster \
  --region=ap-south-1 \
  --name=shopnow
![alt text](Image_assets/image-79.png)

eksctl delete cluster \
  --name=shopnow-cluster \
  --region=ap-south-1
![alt text](Image_assets/image-80.png)

aws eks list-clusters --region ap-south-1

aws ec2 delete-key-pair \
  --key-name eks-nodegroup-key \
  --region ap-south-1

rm eks-nodegroup-key.pem  (local)

aws iam list-open-id-connect-providers

aws iam delete-open-id-connect-provider \
  --open-id-connect-provider-arn <OIDC_ARN>

aws iam delete-open-id-connect-provider \
  --open-id-connect-provider-arn arn:aws:iam::254292659362:oidc-provider/oidc.eks.ap-south-1.amazonaws.com/id/20BC84A3F1FC691114C361B6F1AFA6AD

Terraform destroy
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/7d6612f3-b10b-4bba-b4de-f5976c419f75" />

![alt text](Image_assets/image-81.png)

#############################




































