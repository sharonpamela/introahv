.. _lab_nutanix_technology_overview:

---------------------------------
Lab - Nutanix Technology Overview
---------------------------------

Overview
++++++++

Prism Element is the GUI management plane for Nutanix. Because its design is based on consumer product interfaces, it is more intuitive and easier to use than many enterprise application interfaces.

This lab will introduce the Prism Element UI layout and navigation, as well as basic UI concepts. Detailed sections are covered in later exercises.

Prism Element
+++++++++++++

From the Firefox web browser (preferred), log into the Nutanix Prism GUI using the Cluster IP.

Open \https://<*NUTANIX-CLUSTER-IP*>:9440

Fill out the following fields and click **Enter**:

- **Username** - admin
- **Password** - *HPOC Password*

.. figure:: images/ahv_lab01_01.png

Review the Home screen, and identify the following items:

- Hypervisor
- Version
- Hardware Model

.. figure:: images/ahv_lab01_02.png

Review the UI navigation options.

.. figure:: images/ahv_lab01_03.png

Examine the cluster hardware by using the navigation menu, and go to the Hardware.

In **Prism > Hardware**, click ** Hardware**, then click **Diagram**.

Review the hardware summary information:

- Blocks
- Hosts
- Memory
- CPU
- Disks

.. figure:: images/ahv_lab01_04.png

Review the other sections, and do a quick walk through

- VM
- Health
- Network
- Data Protection
- Storage
- Alerts
- Etc.

Review other sections of the Prism UI

- Health :fa:`heartbeat`
- Alarms :fa:`bell`
- Tasks :fa:`dot-circle`
- Search :fa:`search`
- Help :fa:`question`
- Configuration :fa:`cog`
- User :fa:`user`

.. figure:: images/ahv_lab01_05.png

Takeaways
+++++++++

- Prism is thoughtfully laid out UI
- Critical information is displayed front and center
