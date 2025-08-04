# Proxmox Setup

At the moment, my setup is super simple, consisting of a single node with the following:

- K8s Control Plane VM (Running Ubuntu Server 22.04)
- K8s Worker Node (Also running Ubuntu Server 22.04)

I've also made 2 templates with help from cloud-init:

- Ubuntu Server 22.04 Template
- K8s Worker Node template (built off of the Ubuntu Server 22.04 template)

TODOs:

- Look into ansible and terraform for automating things
- Get some of my config into code so it can be in version control
- Setup some nice way to ssh into my proxmox server view
