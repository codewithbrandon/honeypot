# honeypot

## Objective

The Cloud-Native Threat Detection Lab project aimed to establish a high-interaction, open-source Honeypot environment to passively collect and analyze real-world threat intelligence. The primary goal was to deploy TPOT (The Honeypot Project) onto a DigitalOcean Droplet to Establish a secure, external-facing server for attracting adversarial traffic

### Skills Learned


- Cloud Deployment & Administration: Provisioning and securing a Linux server (Droplet) on the DigitalOcean platform.
- Linux Security Hardening: Creating non-root users and ensuring system packages are up-to-date prior to deployment.
- Elastic Stack Mastery: Proficiency in utilizing Kibana dashboards (via TPOT) to visualize and analyze real-time malicious traffic.
- Honeypot Technology: Practical installation and configuration of the multi-honeypot system using Docker.
- Network Security: Identifying and changing default SSH port configurations post-installation for enhanced security.

### Tools Used

- Cloud Infrastructure: DigitalOcean (Droplet), running Ubuntu 24.04 LTS.
- Honeypot Distribution: TPOT (The Honeypot Project).
- Administration: SSH (Secure Shell) client (PowerShell terminal).
- Software: apt-get, git, adduser, usermod, Kibana, Suricata.

## Steps

*Ref 1: Droplet Provisioning Details*
<img src="hpotlab/ref1.png" />

- This screenshot shows the details of the newly provisioned DigitalOcean Droplet, tzmnc-web-server1, including its public IP address (129.212.188.183), which will be used for SSH access and TPOT deployment.


*Ref 2: Initial SSH Connection*
<img src="hpotlab/ref2.png" />

- The first successful SSH connection to the Droplet as the root user, confirming connectivity and noting the initial system details and pending security updates for the Ubuntu 24.04 LTS installation.


*Ref 3: System Hardening - Package Updates*
<img src="hpotlab/ref3.png" />

- Running apt-get update && apt-get upgrade -y to ensure the operating system is fully updated and patched, which is a critical preparatory step before installing new services.

*Ref 4: System Hardening - User Creation*
<img src="hpotlab/ref4.png" />

- Creating a new non-root user named martin using the adduser command, a fundamental security practice to avoid daily use of the privileged root account.

*Ref 5: System Hardening - Sudo Privileges*
<img src="hpotlab/ref5.png" />

- Granting the newly created user martin administrative privileges by adding them to the sudo group using the usermod -aG sudo martin command.

*Ref 6: System Hardening - User Context Switch*
<img src="hpotlab/ref6.png" />

- Switching the current shell session from root to the standard user martin using su martin to perform the rest of the installation as a non-privileged user.

*Ref 7: TPOT Repsository Cloning*
<img src="hpotlab/ref7.png" />

- Executing the git clone command as the user martin to download the tpotce (TPOT Community Edition) installation files from the Telekom Security GitHub repository.

