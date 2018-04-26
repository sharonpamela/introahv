.. title:: Introduction to Nutanix AHV

.. toctree::
  :maxdepth: 2
  :caption: Technology Overview Labs
  :name: _technology_overview
  :hidden:

  lab01_prism_element_tour/lab01_prism_element_tour

.. toctree::
  :maxdepth: 2
  :caption: Planning and Design Labs
  :name: _planning_and_design
  :hidden:

  lab02_sizer/lab02_sizer

.. toctree::
  :maxdepth: 2
  :caption: Installation and Configuration Labs
  :name: _installation_and_configuration
  :hidden:

  lab03/lab03
  lab04/lab04
  lab05/lab05
  lab06/lab06
  lab07/lab07
  lab08/lab08
  lab09/lab09
  lab10/lab10

.. toctree::
  :maxdepth: 2
  :caption: Deploying Workloads Labs
  :name: _deploying_workloads
  :hidden:

  lab11/lab11
  lab12/lab12
  lab13/lab13
  lab14/lab14
  lab15/lab15
  lab16/lab16
  lab17/lab17
  lab18/lab18
  lab19/lab19
  lab20/lab20
  lab21/lab21
  lab22/lab22

.. toctree::
  :maxdepth: 2
  :caption: Prism Central Monitoring and Management Labs
  :name: _prism_central_monitoring_and_management
  :hidden:

  lab23/lab23
  lab24/lab24
  lab25/lab25
  lab26/lab26
  lab27/lab27
  lab28/lab28
  lab29/lab29

.. toctree::
  :maxdepth: 2
  :caption: Capacity Planning Labs
  :name: _capacity_planning
  :hidden:

  lab30/lab30
  lab31/lab31

.. toctree::
  :maxdepth: 2
  :caption: Appendix
  :name: _appendix
  :hidden:

  appendix/glossary
  appendix/otherstuff

.. _getting_started:

---------------
Getting Started
---------------

Welcome to the Nutanix AHV Bootcamp! This workbook accompanies an instructor-led session that introduces Nutanix technologies and many common management tasks. The instructor will explain the exercises and answer any additional questions that you may have.
At the end of the bootcamp, attendees will have solid understanding of the concepts and technologies that make up the full Nutanix Enterprise Cloud stack and should be well prepared for a hosted or onsite proof-of-concept (POC) engagement.

What's New
++++++++++

- Workshop updated for the following software versions:
  - AOS 5.6
  - AFS 3.0
- Added :ref:`example_lab_3`

Environment Details
+++++++++++++++++++

Nutanix Workshops are intended to be run in the Nutanix Hosted POC environment. Your cluster will be provisioned with all necessary images, networks, and VMs required to complete the exercises.

Networking
..........

Hosted POC clusters follow a standard naming convention, where the numerical suffix corresponds to the subnet for that cluster:

- **Cluster Name** - POC\ *XYZ*
- **Subnet** - 10.21.\ *XYZ*\ .0
- **Cluster IP** - 10.21.\ *XYZ*\ .37

For example:

- **Cluster Name** - POC055
- **Subnet** - 10.21.55.0
- **Cluster IP** - 10.21.55.37

Throughout the Workshop there are multiple instances where you will need to substitue *XYZ* with the correct octet for your subnet, for example:

.. list-table::
   :widths: 25 75
   :header-rows: 1

   * - IP Address
     - Description
   * - 10.21.\ *XYZ*\ .37
     - Nutanix Cluster Virtual IP
   * - 10.21.\ *XYZ*\ .39
     - **PC** VM IP, Prism Central
   * - 10.21.\ *XYZ*\ .40
     - **DC** VM IP, NTNXLAB.local Domain Controller

Each cluster is configured with 2 VLANs which can be used for VMs:

.. list-table::
  :widths: 25 25 10 40
  :header-rows: 1

  * - Network Name
    - Address
    - VLAN
    - DHCP Scope
  * - Primary
    - 10.21.\ *XYZ*\ .1/25
    - 0
    - 10.21.\ *XYZ*\ .50-10.21.\ *XYZ*\ .124
  * - Secondary
    - 10.21.\ *XYZ*\ .129/25
    - *XYZ1*
    - 10.21.\ *XYZ*\ .132-10.21.\ *XYZ*\ .253

Credentials
...........

.. note::

  The *<Cluster Password>* is unique to each cluster and will be provided by the leader of the Workshop.

.. list-table::
   :widths: 25 35 40
   :header-rows: 1

   * - Credential
     - Username
     - Password
   * - Prism Element
     - admin
     - *<Cluster Password>*
   * - Prism Central
     - admin
     - *<Cluster Password>*
   * - Controller VM
     - nutanix
     - *<Cluster Password>*
   * - Prism Central VM
     - nutanix
     - *<Cluster Password>*

Each cluster has a dedicated domain controller VM, **DC**, responsible for providing AD services for the **NTNXLAB.local** domain. The domain is populated with the following Users and Groups:

.. list-table::
   :widths: 25 35 40
   :header-rows: 1

   * - Group
     - Username(s)
     - Password
   * - Administrators
     - Administrator
     - nutanix/4u
   * - SSP Admins
     - adminuser01-adminuser25
     - nutanix/4u
   * - SSP Developers
     - devuser01-devuser25
     - nutanix/4u
   * - SSP Power Users
     - poweruser01-poweruser25
     - nutanix/4u
   * - SSP Basic Users
     - basicuser01-basicuser25
     - nutanix/4u

Access Instructions
+++++++++++++++++++

The Nutanix Hosted POC environment can be accessed a number of different ways:

Citrix XenDesktop
.................

https://citrixready.nutanix.com - *Accessible via the Citrix Receiver client or HTML5*

**Nutanix Employees** - Use your NUTANIXDC credentials

**Non-Employees** - **Username:** POCxxx-User01 (up to POCxxx-User20), **Password:** *<Provided by Instructor>*

Employee Pulse Secure VPN
..........................

https://sslvpn.nutanix.com - Use your CORP credentials

Non-Employee Pulse Secure VPN
..............................

https://lab-vpn.nutanix.com - **Username:** POCxxx-User01 (up to POCxxx-User20), **Password:** *<Provided by Instructor>*

Under **Client Application Sessions**, click **Start** to the right of **Pulse Secure** to download the client.

Install and open **Pulse Secure**.

Add a connection:

- **Type** - Policy Secure (UAC) or Connection Server
- **Name** - HPOC VPN
- **Server URL** - lab-vpn.nutanix.com
