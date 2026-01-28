Ansible AWS EC2 Automation

# Ansible AWS EC2 Automation 🚀

This project demonstrates **end-to-end AWS EC2 automation using Ansible**.
It covers infrastructure provisioning, dynamic inventory, and server configuration
using **Ansible roles**, following real-world DevOps best practices.

---

## 🔧 What This Project Does

✔ Creates an AWS Security Group using Ansible  
✔ Launches an EC2 instance  
✔ Uses **AWS Dynamic Inventory** (no static IPs)  
✔ Groups EC2 instances using AWS tags  
✔ Configures EC2 using **Ansible Roles**  
✔ Installs and manages **Apache Web Server**  
✔ Deploys a custom `index.html` page  

---

## 🧱 Project Structure

Ansible-aws-ec2/
│
├── aws_ec2.yaml              # AWS dynamic inventory configuration
├── create-sg.yml             # Security Group creation
├── create-ec2.yml            # EC2 instance creation
├── main.yml                  # Infrastructure orchestration
├── configure-ec2.yml         # EC2 configuration using roles
├── requirements.yml          # Ansible collections
│
├── roles/
│   └── webserver/
│       ├── tasks/main.yml        # Apache installation & config
│       ├── handlers/main.yml     # Restart Apache handler
│       ├── templates/index.html.j2
│       └── defaults/main.yml     # Default variables
│
├── vars.yml
├── vars-lab.yml
├── .gitignore
└── README.md

---

## 🧠 Key Concepts Used

- Ansible Playbooks
- Ansible Roles
- AWS EC2
- AWS Security Groups
- **Dynamic Inventory (amazon.aws.aws_ec2)**
- SSH Key-based authentication
- Idempotent automation
- Infrastructure as Code (IaC)

---

## ⚙️ Prerequisites

- AWS Account
- EC2 Key Pair
- Python 3.x
- Ansible
- AWS CLI configured

Install required collection:

```bash
ansible-galaxy collection install -r requirements.yml

▶️ How to Run the Project

1️⃣ Create Infrastructure (SG + EC2)
ansible-playbook main.yml
This will:
	•	Create Security Group
	•	Launch EC2 instance
	•	Apply AWS tags

⸻

2️⃣ Verify Dynamic Inventory
ansible-inventory -i aws_ec2.yaml --graph
You should see EC2 grouped by tags.

⸻

3️⃣ Configure EC2 (Apache Role)
ansible-playbook -i aws_ec2.yaml configure-ec2.yml
This will:
	•	Install Apache
	•	Start and enable Apache service
	•	Deploy a custom web page

⸻

🌐 Output

Open your browser:
http://<EC2_PUBLIC_IP>
You should see your custom Apache page 🎉

⸻

🔐 Security Notes
	•	SSH access uses key-based authentication
	•	No credentials are hardcoded
	•	AWS access handled via environment or AWS CLI

⸻

🧪 Tested On
	•	Ubuntu 22.04 EC2
	•	AWS Region: ap-south-1
	•	Ansible Core 2.20+

  📌 Interview Talking Points

“I automated AWS EC2 provisioning using Ansible with dynamic inventory,
eliminating static IP management. I used Ansible roles for configuration
management, ensuring reusability and idempotency.”

⸻

👤 Author

Chethan
Aspiring Cloud & DevOps Engineer
GitHub: https://github.com/chethankumar93532-eng
