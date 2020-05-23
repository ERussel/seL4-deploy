# Installation of seL4 system on the IBM Cloud server (WIP)
Example of how to deploy seL4 based system using PXE technology to Bare Metal [NO OS](https://cloud.ibm.com/docs/bare-metal?topic=bare-metal-bm-no-os) server on the IBM Cloud. This allows for greater automation for customers that need to build and deploy seL4 based system for each new application. 

## The code in this example will:
 - Create a new VLAN for PXE deployment environment
 - Create a new subnet on the PXE VLAN for use with DHCP
 - Create a VSI for use with PXE booting a Bare Metal [NO OS](https://cloud.ibm.com/docs/bare-metal?topic=bare-metal-bm-no-os) Server
 - Run Ansible Playbooks to:
    - Update the OS
    - Install and configure Dnsmasq and PXE
    - Download Ubuntu Server ISO
    - Copy ISO netboot tools in to the `tftpboot` directory
    - Copy Ubuntu ISO files to PXE Dir
    - Update the dnsmasq configuration 
    - Configure DHCP settings 
 - Create a support ticket to have the VSIs private IP set as the DHCP helper address on the appropriate VLAN. 
 - Deploy a NO OS server on to the PXE server VLAN.

## Prerequisites
To use this code you will need to make sure you have met the following requirements:

 - Terraform and the IBM Terraform provider plugin installed - [guide](https://cloud.ibm.com/docs/terraform?topic=terraform-getting-started#install).
 - Ansible installed - [guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) 

> If you already have Terraform v0.12 installed you will need to use a different machine or downgrade. The IBM Cloud Provider plugin only supports pre-v0.12 Terraform versions. 

## Configuration 
See the repositories [wiki](https://github.com/greyhoundforty/ibm_pxe_terraform/wiki) for a guide on how to use this example code. 
