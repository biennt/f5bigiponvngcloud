# Quick start guide for F5 BIG-IP on VNG Cloud
# Table of Contents
## [I. General setup](#I)
### [Launching F5 BIGIP Virtual Edition](#I1)
### [Accessing F5 BIGIP Instance Management Interface](#I2)
### [Licensing your F5 BIGIP instance](#I3)
### [Provisioning modules](#I4)
### [Changing the password](#I5)
## [II. Getting started - Advanced WAF](#II)
## [III. Getting started - Server Load Balancing](#III)
## [IV. Getting started - Global Server Load Balancing](#IV)


## I. General setup <a name="I"></a>
### Launching F5 BIGIP Virtual Edition <a name="I1"></a>
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
### Accessing F5 BIGIP Instance Management Interface <a name="I2"></a>
Check your inbox, you will have an email from VNG Cloud team with detail of how to access your instance.<br>
Example as the one below:
![VNG Cloud Portal Login](/img/vng-bigip-logindetail.png)
Adjusting your Security Group (inbound rules) to allow accessing ports 22/tcp, 8443/tcp for management of the instance itself. Other ports such as 80, 443 should be open for your application later on.
![VNG Cloud Portal Login](/img/vng-securitygroup.png)
### Licensing your F5 BIGIP instance <a name="I3"></a>
![VNG Cloud Portal Login](/img/vng-bigip-license.png)
step 11
![VNG Cloud Portal Login](/img/vng-bigip-license-key.png)
step 11
![VNG Cloud Portal Login](/img/license-activate1.png)
step 11
![VNG Cloud Portal Login](/img/license-activate2.png)
step 11
![VNG Cloud Portal Login](/img/license-activate3.png)
step 11
![VNG Cloud Portal Login](/img/license-activate4.png)
### Provisioning modules <a name="I4"></a>
![VNG Cloud Portal Login](/img/vng-bigip-provisioning.png)
### Changing the password <a name="I5"></a>
![VNG Cloud Portal Login](/img/change-password.png)

## II. Getting started - Advanced WAF <a name="II"></a>
to be updated
## III. Getting started - Server Load Balancing <a name="III"></a>
to be updated
## IV. Getting started - Global Server Load Balancing <a name="IV"></a>
to be updated

