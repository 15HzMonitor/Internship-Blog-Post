# SANS ISC Internship Setup: AWS DShield Sensor + DShield SIEM 
# Introduction
This is a blog post documentation on how to set up the DShield Sensor in AWS, DShield SIEM locally, and connecting them both. <br>
I initially setup a Raspberry Pi5 to use as a DShield Sensor, but ultimately switched to AWS after a while. <br>
I then added a DShield SIEM hosted locally on my network and connected the AWS sensor into it to utilize for my attack observations. <br>
This walkthrough is based on multiple documentations that have been compiled into one, and I have linked their GitHub pages under the “References and Resources” section. 
<br>
<br>

# Requirements - Hardware, Software, and Accounts

### Hardware

1. A machine to host your DShield SIEM. This can be a laptop, a desktop, or a virtual machine running on your desktop. <br>
  If you're planning to run the SIEM 24/7, I suggest to use something different than your daily production machine. <br>
  In my case, I reused an old desktop to use as my SIEM so that it can run 24/7. <br>
  Below are the minimum specs required to run the SIEM (based on Guy's documentation for the Ubuntu Setup [[1]](https://github.com/bruneaug/DShield-SIEM#ubuntu-setup)): <br>
   - Minimum 8+ GB RAM<br>
     - If the amount of RAM assigned to each containers (see below) is more than 2GB, consider increasing the server RAM capacity.<br>
   - 4-8 Cores<br>
   - Add 2 partitions, one for the OS, the other for docker<br>
   - Minimum 300 GB partition assigned to /var/lib/docker (I used a 1TB SATA drive) <br>

2. USB flash drive(s) to put your Ubuntu ISO to be installed to your repurposed machine. Have at least 16GB, and it must be clear of any data since you will be using Rufus, and it will format the USB stick when creating a boot drive.
<br>

### Software

1. Ubuntu 22.04 LTS Live Server 64-bit for your DShield SIEM. You can download the ISO on the [Ubuntu Server Page](https://ubuntu.com/download/server).

2. Rufus Software to put your Ubuntu ISO into a bootable USB. You can find the latest Rufus version on the [Rufus downloads page](https://rufus.ie/downloads/).

3. (Optional) a software such as Parted Magic or DBAN to wipe the machine you will be using.

4. Your router's software to create a static IP for your SIEM and do port forwarding
<br>

### Accounts

1. A SANS Internet Storm Center (ISC) Account for your API key to enter in your sensor. You can sign up on the [ISC sign up page](https://isc.sans.edu/register.html).

2. An AWS Account to deploy your DShield Sensor using the Free Tier offer. <br> If you don't have one yet, you can sign up on the [AWS sign up page](https://signin.aws.amazon.com/signup?request_type=register).

3. An AlienVault OTX account for generating the API code to link to your DShield SIEM. <br> You can sign up on the [AlienVault OTX sign up page](https://otx.alienvault.com/).
<br>

# Setup Process

## 1. [Setup your DShield Sensor](./1.%20AWS%20DShield%20Sensor%20Setup.md).
  1.	Sign up for an AWS Account.
  2.	Setup EC2 Instance
  3.	Install & setup DShield Sensor
  4.	Configure EC2 Security

## 2. [Setup your DShield SIEM](./2.%20Setup%20Your%20DShield%20SIEM.md). <br>
  1. Install Ubuntu Server to a physical machine.<br> <!-- TO-DO: Create a page on how to intall Ubuntu Server to a machine -->
  2. (Option) Install Ubuntu Server virtually through VMWare.<br> <!-- TO-DO: Create a page on how to install Ubuntu Server virtually through VMWare -->
  3. Build a Docker Partition.<br> <!-- TO-DO: Either Link Guy's page on how to build a docker partion, or create a page dedicated for it. The amount of storage might need to be defined. -->
  4. Install Docker.<br> <!-- TO-DO: Create a page on how to install Docker -->
  5. Install and Configure DShield ELK.<br> <!-- TO-DO: Create a page on how to Configure DShield ELK based on Guy's Configurations-->


An optional setup for using Raspberry Pi as a SIEM has been written by another SANS Student, and can be found on their [GitHub page](https://github.com/amelete11235/homelab/blob/main/Installing%20DShield%20SIEM%20on%20a%20Raspberry%20Pi%205%20-%208%20GB%20RAM/Installing%20DShield%20SIEM%20on%20a%20Raspberry%20Pi%205%20-%208%20GB%20RAM.md).
   
## 3. [Configure Filebeat and connect your DShield Sensor to DShield SIEM](./3.%20Configure%20Filebeat%20on%20DShield%20Sensor.md).


## 4. [Harden your DShield SIEM](./4.%20Harden%20your%20DShield%20SIEM.md).


# References and Resources

[1] https://github.com/bruneaug/DShield-SIEM#ubuntu-setup <br>

### Resources
- AWS Guides and Documentation - https://aws.amazon.com/getting-started/?nc1=f_cc
- Rufus - https://rufus.ie/downloads/
- SANS Internet Storm Center - https://isc.sans.edu/
- https://github.com/bruneaug/DShield-SIEM#ubuntu-setup
- https://ubuntu.com/download/server
- https://rufus.ie/downloads/
- https://isc.sans.edu/register.html
- https://signin.aws.amazon.com/signup?request_type=register
- https://otx.alienvault.com/


Special thanks to the writers of these GitHub documentations:<br>

[DShield-ISC](https://github.com/DShield-ISC/dshield) <br>
[amalete11235](https://github.com/amelete11235/homelab/blob/main/Installing%20DShield%20SIEM%20on%20a%20Raspberry%20Pi%205%20-%208%20GB%20RAM/Installing%20DShield%20SIEM%20on%20a%20Raspberry%20Pi%205%20-%208%20GB%20RAM.md) <br>
[bruneaug](https://github.com/bruneaug/DShield-SIEM/tree/main)<br>
[fkadriver](https://github.com/fkadriver/Dshield-ELK) <br>
