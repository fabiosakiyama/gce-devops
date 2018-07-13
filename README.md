# gce-devops
A DevOps project to create an environment on GCE, using:
- Github for a mock app repository
- Jenkins to be triggered by github whenever a commit happens
- Dockerhub to store the app image, builded by jenkins
- Rundeck to get the app image and deploy on kubernetes
- Kubernetes to orchestrate the containers that the app will run

All installations and configurations will be made using:
- Vagrant to provide the VMs on Google
- Puppet to install/configure the tools

# Installing Vagrant
EzPz, just download vagrant from the official website https://www.vagrantup.com/downloads.html and install the package

# Configuring GCP
To configure your google cloud environment with Vagrant, first follow this guide: https://github.com/mitchellh/vagrant-google
If you're using Ubuntu, you may need to install the following packages before:

    ruby-dev
    pkg-config
    gcc
    build-essential

That should be enough to install vagrant google plugin.
Test the default Vagrantfile described on the link and run "vagrant up --provision=google"

# Starting the VMs
Check the Vagrantfile and configure with your credentials, then use vagrant up to start them.

## Ansible
# Installing ansible
EzPz, just run sudo yum install ansible

# Configuring ansible hosts
Configure your ansible hosts just like this repo example, except the addresses.

# Running the playbooks
Run the playbooks (inside, starting with:
- puppetserver.yaml
- puppetagent.yaml
- jenkins.yaml

