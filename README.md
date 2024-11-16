# Internship Blog Post
This is my blog post of a documentation on how to set up the Dshield AWS, DShield SIEM locally, and connecting them both. <br>
I initially was setting up a Raspberry Pi5 to use as a Dshield sensor, but switched to AWS after a while. <br>
I then added a Dshield SIEM hosted locally to utilize it for my Attack Observations and connected the AWS sensor into it.


## Hardware, Software, and Accounts Requirements

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

1. A USB flash drive to put your Ubuntu ISO to be installed to your repurposed machine.



### Software

1. Ubuntu 22.04 LTS Live Server 64-bit for your DShield SIEM. You can download the ISO on the [Ubuntu Server Page](https://ubuntu.com/download/server)

### Accounts

1. A SANS Internet Storm Center (ISC) Account. You can sign up on the [ISC sign up page](https://isc.sans.edu/register.html).

2. An AWS Account to deploy your DShield Sensor using the Free Tier offer. <br> If you don't have one yet, you can sign up on the [AWS sign up page](https://signin.aws.amazon.com/signup?request_type=register).

3. An AlienVault OTX account for generating the API code to link to your Dshield SIEM. <br> You can sign up on the [AlienVault OTX sign up page](https://otx.alienvault.com/).


## Setup Process

#### 1. Login to AWS, and [setup your DShield Sensor](./AWS%20DShield%20Sensor%20Setup.md).
   
#### 2. Setup your DShield SIEM. <br>
  1. Install Ubuntu Server to a physical machine.
  2. (Option) Install Ubuntu Server to a virtual machine.
  3. Build a Docker Partition
  4. Install Docker
  5. Install and Configure DShield ELK
  6. 
   
#### 3. Configure FileBeat and connect your DShield Sensor to DShield SIEM.


#### 4. Harden your DShield SIEM.


## References

[1] https://github.com/bruneaug/DShield-SIEM#ubuntu-setup <br>

