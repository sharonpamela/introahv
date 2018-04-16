.. Adding labels to the beginning of your lab is helpful for linking to the lab from other pages
.. _example_lab_3:

-------------
Example Lab 3
-------------

Overview
++++++++

Here is where we provide a high level description of what the user will be doing during this module. We want to frame why this content is relevant to an SE/Services Consultant and what we expect them to understand after completing the lab.

Creating a VM
+++++++++++++

Example markup for creating a VM in Prism Element:

  In **Prism > VM > Table**, click **+ Create VM**.

  Fill out the following fields and click **Save**:

  - **Name** - Xtract-VM
  - **Description** - Xtract for VMs
  - **vCPU(s)** - 2
  - **Number of Cores per vCPU** - 2
  - **Memory** - 4 GiB
  - Select **+ Add New Disk**

    - **Operation** - Clone from Image Service
    - **Image** - Xtract-VM
    - Select **Add**
  - Remove **CD-ROM** Disk
  - Select **Add New NIC**

    - **VLAN Name** - Primary
    - **IP Address** - *10.21.XX.42*
    - Select **Add**

  Select the **Xtract-VM** VM and click **Power on**.

  Once the VM has started, click **Launch Console**.

Example markup for creating a VM in Prism Central:

  In **Prism Central > Explore > VMs**, click **Create VM**.

  Fill out the following fields and click **Save**:

  - **Name** - Xtract-VM
  - **Description** - Xtract for VMs
  - **vCPU(s)** - 2
  - **Number of Cores per vCPU** - 2
  - **Memory** - 4 GiB
  - Select **+ Add New Disk**

    - **Operation** - Clone from Image Service
    - **Image** - Xtract-VM
    - Select **Add**
  - Remove **CD-ROM** Disk
  - Select **Add New NIC**

    - **VLAN Name** - Primary
    - **IP Address** - *10.21.XX.42*
    - Select **Add**

  Select the **Xtract-VM** VM and click **Actions > Power on**.

  Once the VM has started, click **Actions > Launch console**.

Example markup for creating a Service in Calm:

  In **Application Overview > Services**, click :fa:`plus-circle`.

  Note **Service1** appears in the **Workspace** and the **Configuration Pane** reflects the configuration of the selected Service. You can rearrange the Service icons on the Workspace by clicking and dragging them.

  Fill out the following fields:

  - **Service Name** - APACHE_PHP
  - **Name** - APACHE_PHP_AHV
  - **Cloud** - Nutanix
  - **OS** - Linux
  - **VM Name** - APACHE_PHP
  - **Image** - CentOS
  - **Device Type** - Disk
  - **Device Bus** - SCSI
  - Select **Bootable**
  - **vCPUs** - 2
  - **Cores per vCPU** - 1
  - **Memory (GiB)** - 4
  - Select :fa:`plus-circle` under **Network Adapters (NICs)**
  - **NIC** - Secondary
  - **Crendential** - CENTOS

  Scroll to the top of the **Configuration Panel**, click **Package**.

  Fill out the following fields:

  - **Name** - APACHE_PHP_PACKAGE
  - **Install Script Type** - Shell
  - **Credential** - CENTOS

  Copy and paste the following script into the **Install Script** field:

  .. code-block:: bash

     #!/bin/bash
     set -ex
     # -*- Install httpd and php
     sudo yum update -y
     sudo yum -y install epel-release
     sudo rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm
     sudo yum install -y httpd php56w php56w-mysql

     echo "<IfModule mod_dir.c>
             DirectoryIndex index.php index.html index.cgi index.pl index.php index.xhtml index.htm
     </IfModule>" | sudo tee /etc/httpd/conf.modules.d/dir.conf

     echo "<?php
     phpinfo();
     ?>" | sudo tee /var/www/html/info.php
     sudo systemctl restart httpd
     sudo systemctl enable httpd

  Fill out the following fields:

  - **Uninstall Script Type** - Shell
  - **Credential** - CENTOS

  Copy and paste the following script into the **Uninstall Script** field:

  .. code-block:: bash

    #!/bin/bash
    echo "Goodbye!"

  Click **Save**.

Takeaways
+++++++++

- Here is where we summarize any key takeaways from the module
- Such as how a Nutanix feature used in the lab delivers value
- Or highlighting a differentiator
