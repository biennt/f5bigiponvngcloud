# Quick start guide for F5 BIG-IP on VNG Cloud
# Table of Contents
## [I. General setup](#I)
### [1.Launching F5 BIGIP Virtual Edition](#I1)
### [2.Accessing F5 BIGIP Instance Management Interface](#I2)
### [3.Licensing your F5 BIGIP instance](#I3)
### [4.Re-configure the network](#I4)
### [5.Provisioning modules](#I5)
### [6.Changing the password](#I6)
## <a href='/waf/README.md'>II. Getting started - Advanced WAF</a>
## <a href='/slb/README.md'>III. Getting started - Server Load Balancing</a>
## <a href='/gslb/README.md'>IV. Getting started - Global Server Load Balancing</a>

## I. General setup <a name="I"></a>
### 1.Launching F5 BIGIP Virtual Edition <a name="I1"></a>
Login to the VNG Cloud Portal
![VNG Cloud Portal Login](/img/vng-portal-login.png)

From the landing page, click on vMarketplace
![VNG Cloud Portal Login](/img/vng-portal-landingpage.png)

In the search text box of Marketplace, type bigip then select "F5-BIGIP Virtual Edtion - BYOL".<br>
BYOL means Bring Your Own Licence - You need to have your own license to utilize the instance. Please have the license key with you before proceeding to the next steps.<br>
If you want to get the trial license, please go here https://www.f5.com/trials/big-ip-virtual-edition
![VNG Cloud Portal Login](/img/vng-portal-marketplace-search-bigip.png)

Click on "LAUNCH ON COMPUTE ENGINE" from the product page of F5-BIGIP Virtual Edition - BYOL
![VNG Cloud Portal Login](/img/vng-portal-launch-bigip.png)

Choose the instance flavor as you want. It's recommended that you should start with 16GB RAM and 4 vCPU, with at least 80GB storage as root volume.
![VNG Cloud Portal Login](/img/vng-portal-bigip-instance-config.png)

Below is the summary page of what will be created and the cost
![VNG Cloud Portal Login](/img/vng-portal-bigip-launch-summary.png)

Prepare to checkout..
![VNG Cloud Portal Login](/img/vng-portal-checkout.png)

Applying any coupon..
![VNG Cloud Portal Login](/img/vng-bigip-checkout2.png)

Make the payment..
![VNG Cloud Portal Login](/img/vng-bigip-cloud-checkout3.png)

Payment confirmation
![VNG Cloud Portal Login](/img/vng-big-ip-checkout-done.png)

Wait for about 5 to 10 minutes, your instance will be ready as shown in the example below
![VNG Cloud Portal Login](/img/vng-bigip-instance-detail.png)

### 2.Accessing F5 BIGIP Instance Management Interface <a name="I2"></a>
Check your inbox, you will have an email from VNG Cloud team with detail of how to access your instance.<br>
Example as the one below:
![VNG Cloud Portal Login](/img/vng-bigip-logindetail.png)

Adjusting your Security Group (inbound rules) to allow accessing ports 22/tcp, 8443/tcp for management interfaces of the instance itself. Other ports such as 80, 443 should be opened for your application later on.
![VNG Cloud Portal Login](/img/vng-securitygroup.png)

### 3.Licensing your F5 BIGIP instance <a name="I3"></a>
Access to the Web-based management interface of the F5 BIGIP instance as mentioned in the email from VNG Cloud team.<br>
Typically, it is https://<wan_IP>:8443<br>
Click on "Activate"
![VNG Cloud Portal Login](/img/vng-bigip-license.png)

Key in the license key string. If your instance can reach the internet directly, you can choose Automatic as Activation Method. If not, click on Manual and follow the next steps
![VNG Cloud Portal Login](/img/vng-bigip-license-key.png)

Manual activation:<br>
Step 1: select and copy to clipboard all the text in "Dossier"<br>
Step 2: Click on "Click here to access F5 Licensing Server"<br>
Step 3: Paste the Dossier text in https://activate.f5.com/license/dossier.jsp
![VNG Cloud Portal Login](/img/license-activate1.png)

Step 4: Accept User Legal Agreement
![VNG Cloud Portal Login](/img/license-activate2.png)

Step 5: Copy the content or download the license file
![VNG Cloud Portal Login](/img/license-activate3.png)

Step 6: Paste the content of the license file into "License" text field of your F5 BIGIP instance. Then click Next<br>
![VNG Cloud Portal Login](/img/license-activate4.png)

Your instance will be restarting some services and ready after few minutes
### 4.Re-configure the network <a name="I4"></a>

Access the instance via SSH by user root, then launch TMSH to re-configure the network settings
```
[root@bigip1:Active:Standalone] ~ # tmsh
```
Disable DHCP on management interface
```
modify sys db dhclient.mgmt value disable
```
Re-configure the self IP and adding a default route<br>
(10.4.222.3/24 and 10.4.222.1 are the ip address and default gateway assigned by DHCP on VNG Cloud on instance start)
```
create net self self1_nic address 10.4.222.3/24 vlan internal
create net route defaultroute network 0.0.0.0/0 gw 10.4.222.1
```
Save the configuration
```
save sys config
```

### 5.Provisioning modules <a name="I5"></a>
Depend on your license and usage, you should go to System --> Resource Provisioning to turn on/off the modules.<br>
Below is an example screenshot of activating Advanced Web Application Firewall and Application Visibility and Reporting modules.
![VNG Cloud Portal Login](/img/vng-bigip-provisioning.png)

### 6.Changing the password <a name="I6"></a>
Before starting to configure anything further, REMEMBER TO CHANGE THE PASSSWORD of admin user.<br>
Goto System --> Users --> User List --> Select admin user --> Change the password. You can give "admin" the access to SSH by selecting "Advanced Shell" or "tmsh".<br>
If you open SSH to public, REMEMBER to change the ROOT password as well. Make it very difficult or disable root login completely.
![VNG Cloud Portal Login](/img/change-password.png)

You can continue with other tasks such as configuring NTP, timezone, hostname, DNS, remote syslog.. but they are optional sometimes. It's up to you.<br>
You've just finished the basic setup of F5 BIGIP instance in VNG Cloud.<br>

Congratulation! and do not forget to check out <a href='https://support.f5.com/csp/home'>F5 Networks official support page</a>

