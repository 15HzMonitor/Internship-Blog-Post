# Internship Blog Post
This is my blog post of a documentation on how to set up the DShield AWS, DShield SIEM locally, and connecting them both. <br>
I initially was setting up a Raspberry Pi5 to use as a DShield sensor, but switched to AWS after a while. <br>
I then added a DShield SIEM hosted locally to utilize it for my Attack Observations and connected the AWS sensor into it.
<br>
<br>

# Hardware, Software, and Accounts Requirements

### Hardware

1. A machine to host your DShield SIEM. This can be a laptop, a desktop, or a virtual machine running on your desktop. <br>
  If you're planning to run this 24/7, I suggest to use something different than your daily production machine. <br>
  In my case, I reused an old desktop to use as my SIEM so that it can run 24/7. <br>
  Below are the minimum specs required to run the SIEM (based on Guy's documentation for the Ubuntu Setup [[1]](https://github.com/bruneaug/DShield-SIEM#ubuntu-setup)): <br>
   - Minimum 8+ GB RAM<br>
     - If the amount of RAM assigned to each containers (see below) is more than 2GB, consider increasing the server RAM capacity.<br>
   - 4-8 Cores<br>
   - Add 2 partitions, one for the OS, the other for docker<br>
   - Minimum 300 GB partition assigned to /var/lib/docker (I used a 1TB SATA drive) <br>

2. A USB flash drive to put your Ubuntu ISO to be installed to your repurposed machine. Have at least 
<br>
<br>

### Software

1. Ubuntu 22.04 LTS Live Server 64-bit for your DShield SIEM. You can download the ISO on the [Ubuntu Server Page](https://ubuntu.com/download/server)

2. Rufus Software to put your Ubuntu ISO into a bootable USB. You can find the latest Rufus version on the [Rufus downloads page](https://rufus.ie/downloads/).

3. (Optional) a DBAN software such as Parted Magic to wipe the machine you will be using.
<br>
<br>

### Accounts

1. A SANS Internet Storm Center (ISC) Account for your API key to enter in your sensor. You can sign up on the [ISC sign up page](https://isc.sans.edu/register.html).

2. An AWS Account to deploy your DShield Sensor using the Free Tier offer. <br> If you don't have one yet, you can sign up on the [AWS sign up page](https://signin.aws.amazon.com/signup?request_type=register).

3. An AlienVault OTX account for generating the API code to link to your DShield SIEM. <br> You can sign up on the [AlienVault OTX sign up page](https://otx.alienvault.com/).
<br>
<br>

# Setup Process

## 1. [Login to AWS, and setup your DShield Sensor](./1.%20AWS%20DShield%20Sensor%20Setup.md). <!-- TO-DO: Create a page on how to provision a Dshield Sensor through AWS based on Dr. J's GitHub Documentation -->
   
## 2. Setup your DShield SIEM. <br>
  1. Install Ubuntu Server to a physical machine.<br> <!-- TO-DO: Create a page on how to intall Ubuntu Server to a machine -->
  2. (Option) Install Ubuntu Server virtually through VMWare.<br> <!-- TO-DO: Create a page on how to install Ubuntu Server virtually through VMWare -->
  3. Build a Docker Partition.<br> <!-- TO-DO: Either Link Guy's page on how to build a docker partion, or create a page dedicated for it. The amount of storage might need to be defined. -->
  4. Install Docker.<br> <!-- TO-DO: Create a page on how to install Docker -->
  5. Install and Configure DShield ELK.<br> <!-- TO-DO: Create a page on how to Configure DShield ELK based on Guy's Configurations-->


An optional setup for using Raspberry Pi as a SIEM has been written by another SANS Student, and can be found on their [GitHub page](https://github.com/amelete11235/homelab/blob/main/Installing%20DShield%20SIEM%20on%20a%20Raspberry%20Pi%205%20-%208%20GB%20RAM/Installing%20DShield%20SIEM%20on%20a%20Raspberry%20Pi%205%20-%208%20GB%20RAM.md).
   
## 3. Configure FileBeat and connect your DShield Sensor to DShield SIEM.


## 4. Harden your DShield SIEM.


# References and Resources

[1] https://github.com/bruneaug/DShield-SIEM#ubuntu-setup <br>

<br>
<br>

### Resources
- AWS Guides and Documentation - https://aws.amazon.com/getting-started/?nc1=f_cc
- Rufus - https://rufus.ie/downloads/
- SANS Internet Storm Center - https://isc.sans.edu/
