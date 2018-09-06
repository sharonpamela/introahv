.. _lab_deploy_workloads:

-------------------------
Lab - Deploying Workloads
-------------------------

Overview
++++++++

Learn about basic VM deployment.

Image Configuration
+++++++++++++++++++

Nutanix's Image Service is where you can store your build ISOs, as well as Disk Images you create (similar to VMware Templates).

We will upload a small Linux distro (Raspian OS) to use for deploying VMs.

In **Prism Central > Explore**, click **Images**.

Next click **Add Image**, and click **URL**.

Fill out the following fields and click **Upload File**:

- **Enter Image URL** - http://vx2-downloads.raspberrypi.org/pixel_x86/images/pixel_x86-2016-12-13/2016-12-13-pixel-x86-jessie.iso

.. figure:: images/deploy_workloads_01.png

Next, fill out the following fields and click **Save**:

- **Image Name** - RaspberryPI-*intials*
- **Image Type** - ISO
- **Image Description** - (Optional) Add a description

.. figure:: images/deploy_workloads_02.png

.. note::

  Image management in Prism Central allows you to upload images that can be used to deploy workloads in any of the clusters registered to that Prism Central instance.
  An image can also be uploaded directly from a cluster's Prism Element.
  This tool can also convert VM disk images to formats that AHV can understand.
  The image service supports raw, vhd, vhdx, vmdk, vdi, iso, and qcow2 disk formats.

Creating a Linux VM
+++++++++++++++++++

Deploy a Linux VM from Prism Central.

In **Prism Central > Explore > VMs**, click **Create VM**.

Fill out the following fields and click **Save**:

- **Name** - Linux_VM-*intials*
- **Description** - (Optional) Description for your VM.
- **vCPU(s)** - 1
- **Number of Cores per vCPU** - 1
- **Memory** - 2 GiB

.. figure:: images/deploy_workloads_03.png

- Select **+ Add New Disk**
- **Type** - DISK
- **Operation** - Clone from Image Service
- **Image** - RaspberryPI-*intials* (The Image we added above)
- **Storage Container** - Default Container
- Select **Add**

.. figure:: images/deploy_workloads_04.png

- Select **Add New NIC**
- **VLAN Name** - Primary
- Select **Add**

Click **Save** to create the VM.

Creating a Windows VM
+++++++++++++++++++++

Deploy a Windows VM from Prism Central.

.. note::

  Nutanix provides a set of guest tools and drivers comparable to VMware Tools. To install a Windows-based OS, the I/O drivers must be provided at install time. Nutanix provides a customized set of virtualized I/O drivers for Windows OS on AHV.

In **Prism Central > Explore > VMs**, click **Create VM**.

Fill out the following fields and click **Save**:

- **Name** - Windows_VM-*intials*
- **Description** - (Optional) Description for your VM.
- **vCPU(s)** - 2
- **Number of Cores per vCPU** - 1
- **Memory** - 4 GiB
- Select :fa:`pencil` next to CDROM
- **Operation** - Clone from Image Service
- **Image** - Windows VM ISO
- Select **Update**

- Select **+ Add New Disk**
- **Type** - DISK
- **Operation** - Allocate on Storage Container
- **Storage Container** - Default Container
- **Size (GiB)** - 30 GiB
- Select **Add**

- Select **+ Add New Disk**
- **Type** - CDROM
- **Operation** - Clone from Image Service
- **Image** - Nutanix VirtIO
- Select **Add**

- Select **Add New NIC**
- **VLAN Name** - Primary
- Select **Add**

Click **Save** to create the VM.

Now lets power on the VM:

Select the VM, then click **Power On** from the **Actions** drop-down menu.

Next lets open a console session:

Select the VM, then click **Launch Console** from the **Actions** drop-down menu.

Progress through the standard install questions until you reach the Windows install location.

.. note::
Choose **Datacenter with GUI** and **Custom** installation when presented with the choice.

Click **Load Driver** and navigate to the CD where the Nutanix VirtIO is mounted.

Browse the CD, and select the directory that corresponds to the Windows OS being installed.

.. figure:: images/deploy_workloads_05.png

.. figure:: images/deploy_workloads_06.png

Select the three Nutanix drivers displayed (Press and hold the Ctrl key and select all three drivers):

- Balloon
- Ethernet adapter
- SCSI passthrough controller

.. figure:: images/deploy_workloads_07.png

Click Next.

After the drivers are loaded, the disk created in step 1 appears as an installation target. Select that disk and continue with the normal install process.

After the installation completes, the Windows install ISO can be unmounted and the additional CD-ROM used for the drivers can be removed from the VM.

Takeaways
+++++++++

- In this lab you saw how simple it is to deploy a Linux VM and a Windows VM.
- The Image Configuration tool allows you to have a catalog of available images to be used in VM deployments as needed and covering a broad format support which includes qcow, qcow2, vmdk, VHD, VHDx, RAW, and ISO.
