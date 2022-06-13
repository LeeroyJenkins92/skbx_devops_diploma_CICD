# skbx_devops_diploma_CICD

# Deploying YC infrustructure for CI/CD #

# Terraform Part#

#: git clone https://github.com/LeeroyJenkins92/skbx_devops_diploma_CICD

#: cd ./skbx_infra/Terraform 
#: terraform init

TIPS: Dont forget to replace VARS to your data in provider block (main.tf)

<!-- provider "yandex" {
  token     = var.token
  cloud_id  = var.cloud_id
  folder_id = var.folder_id
  zone      = "ru-central1-a"
} -->

TIPS: Also you should create meta.txt to store there ssh key for connection to terrafrom vps.
Example below:

<!-- #cloud-config
users:
  - name: debain
    groups: sudo
    shell: /bin/bash
    sudo: ['ALL=(ALL) NOPASSWD:ALL']
    ssh-authorized-keys:
      - ssh-rsa my-super-secure-keydebain@example.com -->

#: terraform plan
#: terraform apply

# Installing runner and Nginx

TIPS: Ensure that you have installed ansible and python
Replace ipv4 adresses in hosts file to your data
Also keep your secrets in ansible vault

#: ansible-playbook -b -e@ansible-secrets.enc ./runner.yml -vvv
#: ansible-playbook -b -e@ansible-secrets.enc ./nginx.yml -vvv

