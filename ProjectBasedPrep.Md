### **Software Development Life Cycle (SDLC) & Agile Methodologies**

Both SDLC and Agile methodologies are frameworks for software development, but they differ in approach and execution. Let’s go step by step.

---

## **1. Software Development Life Cycle (SDLC)**

SDLC is a structured process for developing high-quality software efficiently. It consists of **phases** that guide software development from inception to deployment and maintenance.

### **Phases of SDLC**

1. **Planning** – Define project scope, objectives, and feasibility.
2. **Requirement Analysis** – Gather and document software requirements.
3. **Design** – Create architectural and detailed design for the system.
4. **Implementation (Coding)** – Develop the software based on design specifications.
5. **Testing** – Verify and validate that the software meets requirements.
6. **Deployment** – Release the software to production.
7. **Maintenance & Support** – Fix issues, update, and improve the software.

### **SDLC Models**

There are different models of SDLC:

* **Waterfall Model** (Linear, sequential, each phase is completed before moving to the next)
* **V-Model** (Verification and validation at each step)
* **Spiral Model** (Iterative development with risk assessment)
* **Iterative Model** (Cyclic development, refining after each iteration)
* **Agile Model** (Flexible, iterative approach focused on rapid delivery)

---

## **2. Agile Methodologies**

Agile is a **flexible and iterative** approach to software development. Unlike traditional SDLC models (like Waterfall), Agile focuses on delivering small, working parts of software **frequently** and **incrementally**.

### **Key Principles of Agile (as per the Agile Manifesto)**

1. **Individuals & Interactions** over processes and tools.
2. **Working Software** over comprehensive documentation.
3. **Customer Collaboration** over contract negotiation.
4. **Responding to Change** over following a plan.

### **Popular Agile Frameworks**

1. **Scrum** – Uses sprints (time-boxed iterations), daily stand-up meetings, and roles like Product Owner, Scrum Master, and Development Team.
2. **Kanban** – Uses visual boards to track work in progress (WIP) and optimize flow.
3. **SAFe (Scaled Agile Framework)** – Agile methodology for large organizations.
4. **Lean** – Focuses on reducing waste and delivering value faster.

---

## **SDLC vs. Agile**

| Feature                  | SDLC (Waterfall)                     | Agile                                          |
| ------------------------ | ------------------------------------ | ---------------------------------------------- |
| **Approach**             | Sequential                           | Iterative & Incremental                        |
| **Flexibility**          | Less flexible, changes are difficult | Highly flexible, embraces changes              |
| **Delivery**             | Delivered at the end of the process  | Delivered in small increments                  |
| **Customer Involvement** | Minimal                              | Continuous involvement                         |
| **Testing Phase**        | Comes after development              | Continuous testing & integration               |
| **Documentation**        | Detailed upfront documentation       | Light documentation, focus on working software |

---

### **Which One to Use?**

* If the project **requirements are clear** from the start → **SDLC (Waterfall, V-Model, etc.)**
* If the project requires **continuous changes, quick releases** → **Agile (Scrum, Kanban, etc.)**

Would you like me to explain Agile Scrum in detail or give a real-world example of SDLC vs. Agile? 🚀
# **Git & Git Stages Explained**

## **What is Git?**

Git is a **distributed version control system (DVCS)** that helps developers track changes in their code, collaborate with teams, and maintain different versions of their projects efficiently.

### **Key Features of Git**

✅ Tracks changes in files.
✅ Supports branching and merging.
✅ Works offline (local repository).
✅ Enables collaboration using remote repositories (like GitHub, GitLab, Bitbucket).

---

## **Git Workflow & Stages**

Git has three main areas where changes move through:

1️⃣ **Working Directory** – Where you modify files.
2️⃣ **Staging Area (Index)** – Where you add files before committing.
3️⃣ **Local Repository (Commits)** – Where committed changes are stored locally.
4️⃣ **Remote Repository (GitHub, GitLab, etc.)** – Where you push commits to collaborate with others.

### **Git Stages & Important Commands**

| **Git Stage** | **Description**                                | **Command**                     |
| ------------- | ---------------------------------------------- | ------------------------------- |
| **Untracked** | New file not tracked by Git                    | `git status`                    |
| **Staging**   | File added to staging area (ready for commit)  | `git add <file>` or `git add .` |
| **Committed** | Change saved in local repository               | `git commit -m "Message"`       |
| **Pushed**    | Change uploaded to remote repository           | `git push origin <branch>`      |
| **Fetched**   | Updates retrieved from remote (but not merged) | `git fetch`                     |
| **Merged**    | Fetched updates merged into local branch       | `git merge`                     |
| **Stashed**   | Temporarily saves uncommitted changes          | `git stash`                     |
| **Popped**    | Applies stashed changes back                   | `git stash pop`                 |

---

## **1. `git add` (Move changes to Staging Area)**

Adds file(s) to the **staging area**, preparing them for a commit.

```sh
git add <filename>    # Add a single file
git add .             # Add all changes in the current directory
```

🔹 **Example:**
You modify `index.html` and want to track it:

```sh
git add index.html
```

---

## **2. `git commit` (Save changes in Local Repository)**

Saves changes from the **staging area** to the **local repository**.

```sh
git commit -m "Updated index page with new section"
```

🔹 **Example:**
You staged `index.html`, now commit it:

```sh
git commit -m "Added new section to index.html"
```

---

## **3. `git push` (Upload changes to Remote Repository)**

Pushes local commits to the **remote repository** (e.g., GitHub).

```sh
git push origin <branch-name>
```

🔹 **Example:**
You committed changes to `feature-branch` and now push it:

```sh
git push origin feature-branch
```

---

## **4. `git fetch` (Retrieve changes from Remote without Merging)**

Fetches new changes from the remote repository but **does NOT merge them** into the local branch.

```sh
git fetch origin
```

🔹 **Example:**
You check if there are new updates from the remote repo:

```sh
git fetch origin main
```

---

## **5. `git pull` (Fetch + Merge in one step)**

Fetches and **merges** remote changes into your local branch.

```sh
git pull origin <branch-name>
```

🔹 **Example:**
Update your local `main` branch with remote changes:

```sh
git pull origin main
```

---

## **6. `git stash` (Temporarily Save Changes Without Committing)**

If you have uncommitted changes but need to switch branches, **stash them**.

```sh
git stash         # Save changes
git stash list    # View stashed changes
git stash pop     # Apply the last stashed change
git stash drop    # Delete the last stashed change
```

🔹 **Example:**
You're working on `feature-branch` but need to switch branches:

```sh
git stash
git checkout main
git pull origin main
git checkout feature-branch
git stash pop
```

---

## **Handling Merge Conflicts in Git**

Merge conflicts happen when two people modify the same file and Git cannot automatically merge them.

### **How to Resolve a Merge Conflict?**

1️⃣ **Try merging normally**

```sh
git merge <branch-name>
```

2️⃣ **If there’s a conflict, Git marks the file like this:**

```diff
<<<<<<< HEAD
Your changes
=======
Their changes
>>>>>>> branch-name
```

3️⃣ **Manually edit the file, keeping the correct version.**
4️⃣ **Stage the resolved file**

```sh
git add <conflicted-file>
```

5️⃣ **Commit the merge resolution**

```sh
git commit -m "Resolved merge conflict"
```

6️⃣ **Push the resolved changes**

```sh
git push origin <branch-name>
```

---

## **Conclusion**

* `git add` → Stage changes
* `git commit` → Save changes locally
* `git push` → Upload changes to remote
* `git fetch` → Get changes from remote without merging
* `git pull` → Fetch + Merge changes
* `git stash` → Temporarily save changes
* Resolve conflicts manually when merging

Would you like a **hands-on exercise** or a **real-world use case**? 🚀
### **Real-World Use Case of a Git Conflict**

#### **Scenario: Two Developers Working on the Same File**

Imagine two developers, **Alice** and **Bob**, are working on a web application. Both are modifying the same file (`index.html`) on different branches.

#### **Step 1: Alice Makes a Change & Pushes**

1. Alice creates a new branch and modifies `index.html`:

   ```sh
   git checkout -b feature-header
   echo "<h1>Welcome to My Website</h1>" >> index.html
   git add index.html
   git commit -m "Added a header to the homepage"
   git push origin feature-header
   ```

2. She then creates a **Pull Request (PR)** and merges the changes into `main`.

---

#### **Step 2: Bob Makes a Conflicting Change**

1. Bob also creates a new branch and makes a different change in `index.html`:

   ```sh
   git checkout -b feature-footer
   echo "<footer>Contact us at support@example.com</footer>" >> index.html
   git add index.html
   git commit -m "Added a footer to the homepage"
   ```

2. Bob tries to push his changes:

   ```sh
   git push origin feature-footer
   ```

   ✅ **Success** (No conflicts yet because his branch is separate).

---

#### **Step 3: Bob Tries to Merge into `main`**

1. Bob switches to `main` and pulls the latest changes:

   ```sh
   git checkout main
   git pull origin main
   ```

   ✅ **Now, his local `main` branch includes Alice’s changes.**

2. Bob merges his feature branch into `main`:

   ```sh
   git merge feature-footer
   ```

   ❌ **Merge Conflict Occurs!**

---

#### **Step 4: Resolving the Conflict**

Git shows a conflict message:

```sh
CONFLICT (content): Merge conflict in index.html
```

Bob opens `index.html` and sees this:

```diff
<<<<<<< HEAD
<h1>Welcome to My Website</h1>
=======
<footer>Contact us at support@example.com</footer>
>>>>>>> feature-footer
```

🛠 **Bob manually edits the file to include both changes:**

```html
<h1>Welcome to My Website</h1>
<footer>Contact us at support@example.com</footer>
```

---

#### **Step 5: Finalizing the Merge**

1. Bob marks the conflict as resolved:

   ```sh
   git add index.html
   ```

2. He commits the merge resolution:

   ```sh
   git commit -m "Resolved conflict: Added both header and footer"
   ```

3. He pushes the final, conflict-free version to `main`:

   ```sh
   git push origin main
   ```

✅ **Now the repository has both Alice’s header and Bob’s footer!**

---

### **Key Learnings from This Conflict**

🔹 Always **pull the latest changes** before starting work:

```sh
git pull origin main
```

🔹 Use **branches** to isolate changes.
🔹 If a conflict occurs:

* **Manually edit** the conflicting file.
* **Keep the correct changes** from both versions.
* **Commit & push** after resolving the conflict.

Would you like to try a **hands-on Git conflict exercise**? 🚀
## **Infrastructure as Code (IaC) & Tools: Terraform vs Ansible**

### **What is Infrastructure as Code (IaC)?**

Infrastructure as Code (IaC) is the practice of **automating infrastructure deployment and management** using code instead of manual processes.

✅ Benefits of IaC:

* **Consistency** – Avoids configuration drift.
* **Automation** – Reduces manual intervention.
* **Scalability** – Quickly provisions multiple environments.
* **Version Control** – Tracks infrastructure changes in Git.

---

## **IaC Tools: Terraform & Ansible**

### **1. Terraform (Declarative - Provisioning Tool)**

Terraform is an **open-source IaC tool by HashiCorp** that automates **infrastructure provisioning** in cloud environments like AWS, Azure, and Google Cloud.

#### **Key Features of Terraform**

✅ **Declarative** – Define the desired state, and Terraform makes it happen.
✅ **Supports Multi-Cloud** – Works with AWS, Azure, GCP, Kubernetes, etc.
✅ **Immutable Infrastructure** – Replaces resources instead of modifying them.
✅ **State Management** – Stores infrastructure state (`terraform.tfstate`).
✅ **Modules & Reusability** – Allows modular code for reuse.

#### **Terraform Workflow**

1️⃣ **Write Code** – Define infrastructure in `.tf` files.
2️⃣ **Initialize** – `terraform init` to set up Terraform.
3️⃣ **Plan** – `terraform plan` to preview changes.
4️⃣ **Apply** – `terraform apply` to deploy infrastructure.
5️⃣ **Destroy** – `terraform destroy` to remove resources.

#### **Terraform Example: Create an AWS EC2 Instance**

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "web" {
  ami           = "ami-12345678"
  instance_type = "t2.micro"
}
```

Commands:

```sh
terraform init
terraform plan
terraform apply
```

✅ **Terraform creates the EC2 instance automatically.**

---

### **2. Ansible (Procedural - Configuration Management Tool)**

Ansible is an **open-source automation tool by Red Hat** used for **configuration management, application deployment, and orchestration**.

#### **Key Features of Ansible**

✅ **Agentless** – No need to install agents on servers.
✅ **Procedural Approach** – Defines steps to configure a system.
✅ **Uses YAML** – Easy-to-read playbooks.
✅ **Idempotent** – Ensures the same result even if run multiple times.
✅ **Works on SSH** – Secure remote execution.

#### **Ansible Workflow**

1️⃣ **Write Playbooks** – Define configurations in YAML files.
2️⃣ **Run Playbooks** – `ansible-playbook` executes automation tasks.
3️⃣ **Manage Hosts** – Uses inventory files for multiple servers.

#### **Ansible Example: Install Nginx on a Server**

```yaml
- name: Install Nginx on Ubuntu
  hosts: webserver
  become: yes
  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present
```

Commands:

```sh
ansible-playbook nginx.yml
```

✅ **Ansible installs Nginx automatically.**

---

## **Terraform vs Ansible: Key Differences**

| Feature              | Terraform                              | Ansible                                |
| -------------------- | -------------------------------------- | -------------------------------------- |
| **Purpose**          | Infrastructure provisioning            | Configuration management               |
| **Approach**         | Declarative (Define desired state)     | Procedural (Define steps to configure) |
| **Language**         | HCL (HashiCorp Configuration Language) | YAML                                   |
| **State Management** | Maintains state (`terraform.tfstate`)  | No state tracking                      |
| **Cloud Support**    | AWS, Azure, GCP, Kubernetes            | Works with any OS, cloud, and network  |
| **Installation**     | Requires Terraform CLI                 | Uses SSH (agentless)                   |
| **Idempotency**      | Recreates resources if needed          | Ensures same result every run          |
| **Example Use Case** | Create EC2 instance                    | Install and configure Apache/Nginx     |

---

### **When to Use Terraform vs. Ansible?**

✅ **Use Terraform** when provisioning cloud infrastructure (VMs, networks, storage).
✅ **Use Ansible** for configuring applications, installing software, and managing servers.
✅ **Use Both Together** for full automation:

* Terraform **creates the infrastructure** (e.g., AWS EC2).
* Ansible **configures the infrastructure** (e.g., installs Apache on EC2).

Would you like a **hands-on exercise** combining Terraform and Ansible? 🚀
# **Terraform State File & Terraform Blocks (Resource, Variable, etc.)**

## **1. What is a Terraform State File (`terraform.tfstate`)?**

Terraform **state file** is a JSON file that stores the current state of your infrastructure.

### **Purpose of Terraform State**

✅ **Tracks Infrastructure Changes** – Stores resource configurations to know what exists.
✅ **Enables Incremental Updates** – Only modifies resources that have changed.
✅ **Supports Collaboration** – Teams can share state files using remote backends (S3, Azure Storage, Terraform Cloud).

### **Terraform State File Example (`terraform.tfstate`)**

```json
{
  "resources": [
    {
      "type": "aws_instance",
      "name": "web",
      "provider": "provider.aws",
      "instances": [
        {
          "attributes": {
            "ami": "ami-12345678",
            "instance_type": "t2.micro"
          }
        }
      ]
    }
  ]
}
```

**Best Practices for Terraform State Management**
✅ **Use Remote State** – Store state in S3, Azure, or Terraform Cloud.
✅ **Enable State Locking** – Prevents simultaneous updates.
✅ **Never Manually Edit the State File** – Always use Terraform commands.

---

## **2. Terraform Blocks: Defining Infrastructure in Terraform**

Terraform uses **blocks** to define infrastructure components.

### **2.1 Terraform Block (`terraform` block)**

Defines Terraform settings, required providers, and backend configurations.

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
  backend "s3" {
    bucket = "terraform-state-bucket"
    key    = "state/terraform.tfstate"
    region = "us-east-1"
  }
}
```

✅ **Defines Provider Versions**
✅ **Configures Backend for Remote State**

---

### **2.2 Provider Block (`provider` block)**

Defines the cloud provider (AWS, Azure, GCP, etc.).

```hcl
provider "aws" {
  region = "us-east-1"
}
```

✅ **Required for cloud resources**
✅ **Can specify credentials (avoid hardcoding, use environment variables)**

---

### **2.3 Resource Block (`resource` block)**

Defines an infrastructure resource (like EC2, S3, VMs).

```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345678"
  instance_type = "t2.micro"
}
```

✅ **Each resource has a unique name (`web`)**
✅ **Defines attributes like `ami` and `instance_type`**

---

### **2.4 Variable Block (`variable` block)**

Defines reusable variables for dynamic configurations.

```hcl
variable "instance_type" {
  description = "EC2 instance type"
  type        = string
  default     = "t2.micro"
}
```

Usage in a resource block:

```hcl
resource "aws_instance" "web" {
  ami           = "ami-12345678"
  instance_type = var.instance_type
}
```

✅ **Makes configurations reusable and dynamic**
✅ **Supports default values**

---

### **2.5 Output Block (`output` block)**

Displays useful information after applying Terraform.

```hcl
output "instance_ip" {
  value = aws_instance.web.public_ip
}
```

✅ **Prints EC2 Public IP after deployment**

---

### **Summary of Terraform Blocks**

| **Block Type** | **Purpose**                               | **Example**            |
| -------------- | ----------------------------------------- | ---------------------- |
| `terraform`    | Sets Terraform settings & backend         | Remote state storage   |
| `provider`     | Defines cloud provider (AWS, Azure, GCP)  | AWS provider settings  |
| `resource`     | Creates cloud resources (VMs, S3, etc.)   | AWS EC2 instance       |
| `variable`     | Defines dynamic inputs                    | Instance type variable |
| `output`       | Displays outputs after applying Terraform | EC2 Public IP          |

---

### **Real-World Example Using All Blocks**

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
  backend "s3" {
    bucket = "terraform-state-bucket"
    key    = "state/terraform.tfstate"
    region = "us-east-1"
  }
}

provider "aws" {
  region = "us-east-1"
}

variable "instance_type" {
  description = "EC2 instance type"
  type        = string
  default     = "t2.micro"
}

resource "aws_instance" "web" {
  ami           = "ami-12345678"
  instance_type = var.instance_type
}

output "instance_ip" {
  value = aws_instance.web.public_ip
}
```

✅ **Deploys an EC2 instance with a dynamic instance type and prints its public IP.**

Would you like a **hands-on Terraform lab** or a **real-world project example**? 🚀
### **🚀 Real-World Terraform Project: Deploy a Scalable Web Application on AWS**

### **📝 Project Overview**

We will use **Terraform** to provision a **highly available web application** on AWS. This project includes:
✅ **VPC** – Custom network for security.
✅ **Subnets** – Public & Private subnets for scalability.
✅ **EC2 Instances** – Web servers running Nginx.
✅ **Load Balancer (ALB)** – Distributes traffic across instances.
✅ **Auto Scaling Group (ASG)** – Ensures high availability.
✅ **Security Groups** – Controls access to resources.
✅ **Remote State Storage** – Uses S3 for state management.

---

## **🛠 Prerequisites**

1️⃣ **Install Terraform**

```sh
sudo apt install terraform -y  # (Linux)
brew install terraform         # (Mac)
```

2️⃣ **Configure AWS CLI**

```sh
aws configure
```

Provide **Access Key, Secret Key, Region** (e.g., `us-east-1`).

---

## **📂 Project Directory Structure**

```
terraform-web-app/
├── main.tf          # Defines resources (EC2, ALB, ASG, VPC)
├── variables.tf     # Input variables
├── outputs.tf       # Output values
├── provider.tf      # AWS provider configuration
├── security.tf      # Security groups
├── autoscaling.tf   # Auto Scaling Group & Load Balancer
├── user-data.sh     # Script to install Nginx on EC2
```

---

## **🔹 Step 1: Define AWS Provider & Backend (`provider.tf`)**

Stores Terraform state in an **S3 bucket** for collaboration.

```hcl
terraform {
  backend "s3" {
    bucket         = "my-terraform-state-bucket"
    key            = "state/terraform.tfstate"
    region         = "us-east-1"
    encrypt        = true
  }
}

provider "aws" {
  region = "us-east-1"
}
```

---

## **🔹 Step 2: Create a VPC & Subnets (`main.tf`)**

Creates a **custom VPC with public and private subnets**.

```hcl
resource "aws_vpc" "web_vpc" {
  cidr_block = "10.0.0.0/16"
}

resource "aws_subnet" "public_subnet" {
  vpc_id            = aws_vpc.web_vpc.id
  cidr_block        = "10.0.1.0/24"
  map_public_ip_on_launch = true
}

resource "aws_subnet" "private_subnet" {
  vpc_id     = aws_vpc.web_vpc.id
  cidr_block = "10.0.2.0/24"
}
```

---

## **🔹 Step 3: Define Security Groups (`security.tf`)**

Allows **HTTP (80) & SSH (22) access** to EC2 instances.

```hcl
resource "aws_security_group" "web_sg" {
  vpc_id = aws_vpc.web_vpc.id

  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

---

## **🔹 Step 4: Deploy EC2 Instances with User Data (`main.tf`)**

EC2 instances will install **Nginx automatically**.

```hcl
resource "aws_instance" "web" {
  ami                    = "ami-0c55b159cbfafe1f0"  # Amazon Linux 2
  instance_type          = "t2.micro"
  subnet_id              = aws_subnet.public_subnet.id
  security_groups        = [aws_security_group.web_sg.id]

  user_data = file("user-data.sh")
}

output "instance_public_ip" {
  value = aws_instance.web.public_ip
}
```

---

## **🔹 Step 5: Create a Load Balancer & Auto Scaling (`autoscaling.tf`)**

1️⃣ **Auto Scaling Group (ASG)** ensures **high availability**.
2️⃣ **ALB (Application Load Balancer)** distributes traffic.

```hcl
resource "aws_launch_configuration" "web_lc" {
  name          = "web-lc"
  image_id      = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  security_groups = [aws_security_group.web_sg.id]
  user_data = file("user-data.sh")
}

resource "aws_autoscaling_group" "web_asg" {
  launch_configuration = aws_launch_configuration.web_lc.id
  min_size             = 2
  max_size             = 5
  vpc_zone_identifier  = [aws_subnet.public_subnet.id]
}

resource "aws_lb" "web_lb" {
  name               = "web-lb"
  internal           = false
  load_balancer_type = "application"
  security_groups    = [aws_security_group.web_sg.id]
  subnets           = [aws_subnet.public_subnet.id]
}
```

---

## **🔹 Step 6: User Data Script (`user-data.sh`)**

Runs automatically to install **Nginx on EC2 instances**.

```sh
#!/bin/bash
sudo yum update -y
sudo yum install -y nginx
sudo systemctl start nginx
sudo systemctl enable nginx
echo "<h1>Welcome to Terraform Web App</h1>" | sudo tee /var/www/html/index.html
```

---

## **🚀 Step 7: Deploy the Infrastructure**

1️⃣ **Initialize Terraform**

```sh
terraform init
```

2️⃣ **Check the Execution Plan**

```sh
terraform plan
```

3️⃣ **Apply Changes**

```sh
terraform apply -auto-approve
```

4️⃣ **Get Load Balancer URL**

```sh
terraform output
```

5️⃣ **Access the Web App**
Open the **Load Balancer URL** in a browser to see:

```
Welcome to Terraform Web App
```

---

## **📌 Summary of the Project**

✅ **Terraform deploys a full web application stack:**

* **VPC & Subnets** (Networking)
* **Security Groups** (Access Control)
* **EC2 Instances** (Web Servers)
* **Auto Scaling Group** (Ensures Availability)
* **Load Balancer (ALB)** (Traffic Distribution)

✅ **Fully Automated with Terraform & User Data**
✅ **Scalable, Secure, and Production-Ready**

---

## **🎯 Next Steps**

1️⃣ **Enhance Security** – Use IAM Roles & S3 Backend Encryption.
2️⃣ **Use Terraform Modules** – Modularize resources for reuse.
3️⃣ **Implement CI/CD** – Automate deployments using **Jenkins/GitHub Actions**.

---

Would you like a **step-by-step video tutorial** or a **GitHub repo** with this project? 🚀
# **Managing Existing Cloud Resources with Terraform**

If you have existing resources in AWS, Azure, or GCP and want Terraform to manage them **without recreating**, follow these steps:

---

## **🛠 Scenario**

✅ You manually created an **EC2 instance in AWS** (or any cloud resource).
✅ Now, you want Terraform to **import & manage it** **without downtime**.

---

## **🔹 Step 1: Write a Terraform Configuration**

Create a Terraform file (`main.tf`) that **matches your existing resource**.

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "my_instance" {
  ami           = "ami-12345678"  # Match your existing AMI
  instance_type = "t2.micro"
}
```

⚠️ **Do not apply yet!** Terraform doesn't know the resource exists yet.

---

## **🔹 Step 2: Find the Existing Resource ID**

Find your instance in AWS:

```sh
aws ec2 describe-instances --query "Reservations[*].Instances[*].InstanceId" --output json
```

Example output:

```json
[
  "i-0abcd1234efgh5678"
]
```

---

## **🔹 Step 3: Import the Resource into Terraform State**

Run the **terraform import** command:

```sh
terraform import aws_instance.my_instance i-0abcd1234efgh5678
```

✅ Terraform now **maps the resource to your configuration**.

---

## **🔹 Step 4: Verify with Terraform Plan**

Check if Terraform recognizes the resource:

```sh
terraform plan
```

If Terraform shows **no changes**, everything is correctly mapped.

---

## **🔹 Step 5: Refresh & Update Configuration (Optional)**

If you want Terraform to **generate the correct config**, run:

```sh
terraform state show aws_instance.my_instance
```

You'll see output like this:

```hcl
ami           = "ami-12345678"
instance_type = "t2.micro"
public_ip     = "3.123.45.67"
```

Copy and update `main.tf` with these values.

---

## **📌 Key Notes**

✅ **Terraform will NOT recreate resources if imported properly**.
✅ **Always check `terraform plan` before applying changes**.
✅ **Use `terraform state show` to confirm imported resources**.
✅ **For multiple resources, repeat `terraform import` for each one**.

Would you like a **detailed example with another cloud provider (Azure/GCP)?** 🚀
## **What is Maven?**

**Maven** is a **build automation tool** primarily used for **Java projects**. It helps in:
✅ **Compiling** Java code
✅ **Managing dependencies** (via `pom.xml`)
✅ **Packaging** the application (JAR/WAR)
✅ **Running tests**
✅ **Deploying** the project

Maven follows the **Convention over Configuration** approach, meaning developers don’t need to write custom scripts for common tasks.

---

## **What is `pom.xml` in Maven?**

**`pom.xml` (Project Object Model)** is the **configuration file** of a Maven project. It defines:
✅ **Project metadata** (name, version, description)
✅ **Dependencies** (external libraries required)
✅ **Build plugins** (compilers, testing frameworks)
✅ **Build lifecycle** (phases like compile, test, package)

### **Example `pom.xml`**

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" 
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>my-app</artifactId>
    <version>1.0-SNAPSHOT</version>

    <dependencies>
        <!-- Adding a dependency (JUnit for testing) -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.13.2</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>
```

---

## **What is `mvn clean install` Command?**

This is a commonly used **Maven command** that executes **two main lifecycle phases**:

### **1️⃣ `mvn clean`**

* Deletes the **`target/` directory** (compiled files, previous builds).
* Ensures a **fresh build**.

### **2️⃣ `mvn install`**

* **Compiles** the code (`mvn compile`).
* **Runs tests** (`mvn test`).
* **Packages** the project (`mvn package`).
* **Installs the package** into the **local repository** (`~/.m2/repository`), so other projects can use it as a dependency.

### **Example Output of `mvn clean install`**

```sh
[INFO] Scanning for projects...
[INFO] Cleaning project...
[INFO] Compiling 5 source files...
[INFO] Running tests...
[INFO] Packaging JAR file...
[INFO] Installing my-app-1.0.jar to ~/.m2/repository/com/example/my-app/1.0
[INFO] BUILD SUCCESS
```

---

## **Maven Lifecycle & Important Phases**

Maven follows a structured **build lifecycle**:

| Phase     | Description                                                     |
| --------- | --------------------------------------------------------------- |
| `clean`   | Deletes previous build artifacts (`target/` folder).            |
| `compile` | Compiles Java source files.                                     |
| `test`    | Runs unit tests using frameworks like JUnit.                    |
| `package` | Creates a JAR/WAR file of the application.                      |
| `install` | Saves the package in the local repository (`~/.m2/repository`). |
| `deploy`  | Deploys the built package to a remote repository.               |

---

## **📌 Key Takeaways**

✔ **Maven** is a Java **build & dependency management tool**.
✔ **`pom.xml`** defines project dependencies, versions, and build configuration.
✔ **`mvn clean install`** removes old builds, compiles, tests, packages, and installs the project.
✔ Maven lifecycle automates the entire **build & deployment process**.

Would you like a **real-world example of Maven in a CI/CD pipeline**? 🚀
# **Real-World Example: Maven in a CI/CD Pipeline**

Let’s take a real-world scenario where **Maven** is used in a **CI/CD pipeline** to build, test, and deploy a **Spring Boot application** on a **Tomcat server** using **Jenkins**.

---

## **🚀 Scenario**

* A **Spring Boot application** (`my-app`) is developed using **Maven**.
* **Jenkins** is used to automate the CI/CD pipeline.
* The application is deployed to **Apache Tomcat** on an **AWS EC2 instance**.
* Code is stored in **GitHub**.

---

## **🛠️ Step-by-Step CI/CD Pipeline with Maven**

### **Step 1: Code is Pushed to GitHub**

Developers push changes to the `main` branch of a **GitHub repository** containing the **Maven-based Spring Boot project**.

---

### **Step 2: Jenkins Triggers the Build**

Jenkins is configured with a **GitHub webhook** to automatically trigger the pipeline when code is pushed.

---

### **Step 3: Maven Build & Test**

Jenkins executes the following **Maven commands**:

#### **🛠️ Build & Clean Project**

```sh
mvn clean
```

✅ **Deletes old compiled files** in `target/` directory.

#### **🛠️ Compile & Run Tests**

```sh
mvn test
```

✅ **Runs unit tests** (JUnit, Mockito).
✅ If tests **fail**, Jenkins **stops the pipeline**.

#### **🛠️ Package the Application**

```sh
mvn package
```

✅ **Creates a JAR/WAR file** in the `target/` folder.

#### **🛠️ Install the Artifact in the Local Repository**

```sh
mvn install
```

✅ Installs the JAR/WAR in the **local Maven repository (`~/.m2/repository`)**.

---

### **Step 4: Deploy to Apache Tomcat on AWS EC2**

#### **🔹 Copy the WAR file to Tomcat**

If packaging is successful, Jenkins uses **SSH or Ansible** to copy the WAR file to the **EC2 instance** where Apache Tomcat is running.

```sh
scp target/my-app-1.0.war ubuntu@ec2-instance:/opt/tomcat/webapps/
```

✅ Deploys `my-app-1.0.war` to **Tomcat’s webapps folder**.

#### **🔹 Restart Tomcat to Apply Changes**

```sh
ssh ubuntu@ec2-instance "sudo systemctl restart tomcat"
```

✅ Tomcat reloads the application.

---

### **Step 5: Notify & Monitor**

* Jenkins **sends a notification** (Slack, email) about the deployment status.
* Monitoring tools like **Zabbix or Prometheus** check app health.

---

## **📌 Complete Jenkins Pipeline Script**

```groovy
pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/user/my-app.git'
            }
        }
        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test with Maven') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                sh 'scp target/my-app-1.0.war ubuntu@ec2-instance:/opt/tomcat/webapps/'
                sh 'ssh ubuntu@ec2-instance "sudo systemctl restart tomcat"'
            }
        }
    }
}
```

---

## **📌 Key Takeaways**

✔ **Maven automates the build, test, and packaging process**.
✔ **Jenkins CI/CD pipeline automates deployment**.
✔ **Artifacts are deployed to Apache Tomcat on AWS EC2**.
✔ **Monitoring & notifications ensure stability**.

Would you like to see a **Docker-based deployment example instead?** 🚀
# **🚀 Maven + Docker Deployment in a CI/CD Pipeline**

In this scenario, we will use **Maven to build a Spring Boot application** and deploy it as a **Docker container** using **Jenkins CI/CD**.

---

## **🛠 Real-World Use Case**

✅ A **Spring Boot application** (`my-app`) is built using **Maven**.
✅ **Docker** is used to containerize the application.
✅ **Jenkins** automates the build, test, and deployment process.
✅ The containerized app is deployed to **AWS ECS (Elastic Container Service)** or **Kubernetes**.

---

## **🔹 Step-by-Step CI/CD Pipeline**

### **1️⃣ Developers Push Code to GitHub**

Developers push changes to a **GitHub repository** containing the **Maven-based Spring Boot project**.

---

### **2️⃣ Jenkins Triggers the CI/CD Pipeline**

Jenkins is configured with a **GitHub webhook** to automatically trigger when code is pushed.

---

### **3️⃣ Build & Test the Application with Maven**

Jenkins runs the following **Maven commands**:

#### **🛠 Clean and Build the Project**

```sh
mvn clean package
```

✅ **Removes old build artifacts** and **packages the application** into a JAR file.

#### **🛠 Run Unit Tests**

```sh
mvn test
```

✅ Runs unit tests using JUnit.
❌ **If tests fail, the pipeline stops.**

---

### **4️⃣ Build a Docker Image**

After a successful build, Jenkins creates a **Docker image** of the application.

#### **🔹 Create a `Dockerfile`**

Inside the project root, create a `Dockerfile`:

```dockerfile
FROM openjdk:17-jdk-slim
WORKDIR /app
COPY target/my-app-1.0.jar app.jar
EXPOSE 8080
CMD ["java", "-jar", "app.jar"]
```

✅ **Base Image:** Uses OpenJDK 17
✅ **Copies JAR file** from Maven build
✅ **Runs app on port 8080**

#### **🔹 Jenkins Builds Docker Image**

```sh
docker build -t my-app:latest .
```

✅ Creates a **Docker image** named `my-app:latest`

---

### **5️⃣ Push the Docker Image to Docker Hub or AWS ECR**

#### **🔹 Log in to Docker Hub**

```sh
echo "$DOCKER_PASSWORD" | docker login -u "$DOCKER_USERNAME" --password-stdin
```

#### **🔹 Tag and Push the Image**

```sh
docker tag my-app:latest my-dockerhub-user/my-app:latest
docker push my-dockerhub-user/my-app:latest
```

✅ The Docker image is now available on Docker Hub.

---

### **6️⃣ Deploy the Container to AWS ECS / Kubernetes**

#### **🔹 Deploy to AWS ECS**

```sh
aws ecs update-service --cluster my-cluster --service my-service --force-new-deployment
```

✅ Updates the **ECS service** with the new container.

#### **🔹 Deploy to Kubernetes**

```sh
kubectl apply -f deployment.yaml
```

✅ Deploys the app to **Kubernetes**.

---

## **📌 Complete Jenkins Pipeline Script**

```groovy
pipeline {
    agent any
    environment {
        DOCKER_IMAGE = "my-dockerhub-user/my-app:latest"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/user/my-app.git'
            }
        }
        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test with Maven') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }
        stage('Push Docker Image') {
            steps {
                sh 'echo "$DOCKER_PASSWORD" | docker login -u "$DOCKER_USERNAME" --password-stdin'
                sh 'docker push $DOCKER_IMAGE'
            }
        }
        stage('Deploy to AWS ECS') {
            steps {
                sh 'aws ecs update-service --cluster my-cluster --service my-service --force-new-deployment'
            }
        }
    }
}
```

---

## **📌 Key Takeaways**

✔ **Maven** builds and tests the application.
✔ **Docker** containerizes the application.
✔ **Jenkins** automates the CI/CD process.
✔ **Docker Hub / AWS ECR** stores the image.
✔ **AWS ECS / Kubernetes** deploys the application.

---

Would you like a **Terraform-based ECS deployment example?** 🚀
# **🚀 Terraform-Based ECS Deployment for a Maven + Docker App**

In this scenario, we'll use **Terraform** to deploy a **Maven-built, Dockerized Spring Boot application** to **AWS ECS (Elastic Container Service)**.

---

## **🛠 Use Case**

✅ **Spring Boot app** built using **Maven**.
✅ **Docker** containerizes the application.
✅ **Terraform** provisions AWS infrastructure (ECS, ALB, VPC, IAM, etc.).
✅ **Jenkins CI/CD** automates the pipeline.

---

## **1️⃣ Build & Push Docker Image**

Before deploying, we must **build the Docker image** and push it to **Amazon Elastic Container Registry (ECR)**.

### **🔹 Create an AWS ECR Repository**

```sh
aws ecr create-repository --repository-name my-app
```

✅ Creates a private **ECR repository**.

### **🔹 Authenticate Docker with AWS ECR**

```sh
aws ecr get-login-password | docker login --username AWS --password-stdin <AWS_ACCOUNT_ID>.dkr.ecr.<AWS_REGION>.amazonaws.com
```

### **🔹 Build and Push the Image**

```sh
docker build -t my-app .
docker tag my-app:latest <AWS_ACCOUNT_ID>.dkr.ecr.<AWS_REGION>.amazonaws.com/my-app:latest
docker push <AWS_ACCOUNT_ID>.dkr.ecr.<AWS_REGION>.amazonaws.com/my-app:latest
```

✅ The Docker image is now **stored in AWS ECR**.

---

## **2️⃣ Terraform Code for AWS ECS Deployment**

Now, we use **Terraform** to create:
✔ **VPC & Subnets**
✔ **ECS Cluster & Service**
✔ **Task Definition** (for the containerized app)
✔ **Application Load Balancer (ALB)**
✔ **IAM Roles & Security Groups**

---

### **🔹 `variables.tf` - Define Variables**

```hcl
variable "aws_region" { default = "us-east-1" }
variable "vpc_cidr" { default = "10.0.0.0/16" }
variable "subnet_cidr_1" { default = "10.0.1.0/24" }
variable "subnet_cidr_2" { default = "10.0.2.0/24" }
variable "ecs_cluster_name" { default = "my-cluster" }
variable "app_name" { default = "my-app" }
variable "container_port" { default = 8080 }
```

---

### **🔹 `network.tf` - VPC & Subnet Setup**

```hcl
resource "aws_vpc" "my_vpc" {
  cidr_block = var.vpc_cidr
  enable_dns_support = true
  enable_dns_hostnames = true
}

resource "aws_subnet" "subnet_1" {
  vpc_id = aws_vpc.my_vpc.id
  cidr_block = var.subnet_cidr_1
  availability_zone = "us-east-1a"
}

resource "aws_subnet" "subnet_2" {
  vpc_id = aws_vpc.my_vpc.id
  cidr_block = var.subnet_cidr_2
  availability_zone = "us-east-1b"
}
```

---

### **🔹 `ecs.tf` - ECS Cluster & Task Definition**

```hcl
resource "aws_ecs_cluster" "my_cluster" {
  name = var.ecs_cluster_name
}

resource "aws_ecs_task_definition" "my_task" {
  family                   = var.app_name
  requires_compatibilities = ["FARGATE"]
  network_mode             = "awsvpc"
  memory                   = "512"
  cpu                      = "256"
  execution_role_arn       = aws_iam_role.ecs_task_role.arn
  container_definitions    = <<DEFINITION
[
  {
    "name": "${var.app_name}",
    "image": "<AWS_ACCOUNT_ID>.dkr.ecr.${var.aws_region}.amazonaws.com/${var.app_name}:latest",
    "memory": 512,
    "cpu": 256,
    "essential": true,
    "portMappings": [
      {
        "containerPort": ${var.container_port},
        "hostPort": ${var.container_port}
      }
    ]
  }
]
DEFINITION
}
```

---

### **🔹 `alb.tf` - Application Load Balancer**

```hcl
resource "aws_lb" "my_alb" {
  name               = "my-alb"
  internal           = false
  load_balancer_type = "application"
  security_groups    = [aws_security_group.alb_sg.id]
  subnets           = [aws_subnet.subnet_1.id, aws_subnet.subnet_2.id]
}

resource "aws_lb_target_group" "tg" {
  name     = "my-tg"
  port     = 8080
  protocol = "HTTP"
  vpc_id   = aws_vpc.my_vpc.id
}

resource "aws_lb_listener" "http" {
  load_balancer_arn = aws_lb.my_alb.arn
  port              = 80
  protocol          = "HTTP"

  default_action {
    type             = "forward"
    target_group_arn = aws_lb_target_group.tg.arn
  }
}
```

---

### **🔹 `iam.tf` - IAM Role for ECS Task Execution**

```hcl
resource "aws_iam_role" "ecs_task_role" {
  name = "ecsTaskExecutionRole"

  assume_role_policy = jsonencode({
    Statement = [{
      Action = "sts:AssumeRole"
      Effect = "Allow"
      Principal = {
        Service = "ecs-tasks.amazonaws.com"
      }
    }]
    Version = "2012-10-17"
  })
}

resource "aws_iam_policy_attachment" "ecs_task_execution_role" {
  name       = "ecs-task-execution-role"
  roles      = [aws_iam_role.ecs_task_role.name]
  policy_arn = "arn:aws:iam::aws:policy/service-role/AmazonECSTaskExecutionRolePolicy"
}
```

---

## **3️⃣ Apply Terraform to Provision AWS Infrastructure**

Run the following Terraform commands:

```sh
terraform init
terraform plan
terraform apply -auto-approve
```

✅ This creates the **VPC, ECS Cluster, Task Definition, ALB, and IAM roles**.

---

## **4️⃣ Deploy the Docker Container to ECS**

Once Terraform has created the infrastructure, deploy the app using the ECS service:

```sh
aws ecs update-service --cluster my-cluster --service my-service --force-new-deployment
```

✅ The **new container version is deployed** to ECS.

---

## **5️⃣ Access the Application**

After deployment, find the **ALB DNS Name**:

```sh
aws elbv2 describe-load-balancers --query "LoadBalancers[*].DNSName"
```

Open the DNS in a browser:

```sh
http://<ALB-DNS-Name>
```

✅ Your application is now **live on AWS ECS!** 🎉

---

## **📌 Complete Jenkins CI/CD Pipeline for Terraform + Docker + ECS**

```groovy
pipeline {
    agent any
    environment {
        DOCKER_IMAGE = "<AWS_ACCOUNT_ID>.dkr.ecr.<AWS_REGION>.amazonaws.com/my-app:latest"
    }
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/user/my-app.git'
            }
        }
        stage('Build and Push Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
                sh 'docker push $DOCKER_IMAGE'
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform init'
                sh 'terraform apply -auto-approve'
            }
        }
        stage('Deploy to ECS') {
            steps {
                sh 'aws ecs update-service --cluster my-cluster --service my-service --force-new-deployment'
            }
        }
    }
}
```

---

## **📌 Key Takeaways**

✔ **Terraform provisions AWS infrastructure** (VPC, ECS, ALB, IAM).
✔ **Docker containerizes the application**.
✔ **ECR stores the image**, ECS runs the container.
✔ **Jenkins automates the CI/CD pipeline**.
✔ **ALB provides public access to the app**.

---

Would you like a **full video tutorial or a Kubernetes-based alternative?** 🚀
