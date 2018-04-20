
.. _lab_2:

------------------------------
Lab 2 - Sizer (Instructor Led)
------------------------------

Overview
++++++++

Learn how Nutanix engineers and partners can leverage the Sizer tool to select the right combination of hardware.

Using Notes
+++++++++++

Open \http://sizer.nutanix.com

.. figure:: images/ahv_lab02_01.png

Login with your **My Nutanix Login** credentials.

Click **+ Create New Scenario**, and create a demo Scenario.

.. figure:: images/ahv_lab02_02.png

Enter a **Scenario Name**.

Highlight the different vendor hardware models that support Nutanix software.

.. figure:: images/ahv_lab02_03.png

Highlight the scenario objective fields, and why it is important to put as much info in as possible.

.. figure:: images/ahv_lab02_04.png

Click **+ Add Workload**.

.. figure:: images/ahv_lab02_05.png

Enter a **Workload Name**.

Highlight the different workload types.

.. figure:: images/ahv_lab02_06.png

Select **Server Virtualization**, and click **Next**.

Fill out the following fields and click **Save**:

- **Server Profile Size** - Large
- **Number of VM's** - 100
- **Container Replication Factor** - RF2
- **Disable Compression for Pre-Compressed Data** - No
- **Erasure Coding** - Unchecked
- **Block Awareness** - Unchecked
- **Encrypt Storage for VM** - Unchecked
- **Data Protection** - No

.. figure:: images/ahv_lab02_07.png

Click **Modify** in the **Sizing Options** section.

.. figure:: images/ahv_lab02_08.png

Highlight the different **Sizing Options** under **Automatic**.

.. figure:: images/ahv_lab02_09.png

Highlight the different changes you can make under **Manual**.

.. figure:: images/ahv_lab02_10.png

.. figure:: images/ahv_lab02_11.png

Highlight and explain **Sizing Details**.

.. figure:: images/ahv_lab02_12.png

Highlight and explain **Sizing Charts**.

.. figure:: images/ahv_lab02_13.png

Highlight and explain **Financial Analysis**.

.. figure:: images/ahv_lab02_14.png

Highlight and explain **Rack View**.

.. figure:: images/ahv_lab02_15.png

Click the :fa:`ellipsis-v`, and then click **Download BOM**.

.. figure:: images/ahv_lab02_16.png

Ensure that all options are checked, and click **Download**.

.. figure:: images/ahv_lab02_17.png

Review the BOM.

.. literalinclude:: BOM-Workshop_Demo.pdf

Takeaways
+++++++++

- Sizer is an excellent tool to ensure a coorectly sized Nutanix Software solution.
-	Sizer is available for customers and prospects here: \http://go.nutanix.com/size-your-data-center.html
- Demo Video on YouTube: \https://www.youtube.com/watch?v=uS8C5bzYr_s
