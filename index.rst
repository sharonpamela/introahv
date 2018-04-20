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

HPOC Info Provided by instructor
++++++++++++++++++++++++++++++++

- **Cluster IP** - 10.21.XX.37
- **Username** - admin
- **Password** - HPOC Password
- **HPOC Subnet** - 10.21.XX.0
- **Subnet Mask** - 255.255.255.128
- **Gateway** - 10.21.XX.1
- **DNS Servers** - 10.21.253.10,10.21.253.11

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
