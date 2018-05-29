.. _lab_data_protection:

---------------------
Lab - Data Protection
---------------------

Overview
++++++++

Learn how to set up protection domains, create VM snapshots, and restore from those snapshots.

Data Protection
+++++++++++++++

In Prism, data protection policies are called protection domains (PDs). A PD is made up of a set of VMs and a policy. The available policies include snapshots, replication locations, and schedules.

VM snapshots
............

Create a VM snapshot and restore a VM from a snapshot.

In **Prism Element > VM**, click **VM**, then click **Table**.

Locate the Linux VM you created in the previous lab (Linux_VM-*intials*).

- If the VM is powered on, power it Off

Select the VM, then click **Snapshot** from the menu below the list of VMs.

Provide a name for your snapshot.

Return to VMs table and click the VM’s name to open its console window.

Click **Snapshots** to see your snapshot.

- Note the four available actions (Details, Clone, Restore, and Delete).

Click **Details** to see all of the VM’s properties at the time of the snapshot.

Now lets break our VM.

Click **Update** from the menu below and modify the original VM you took the snapshot of.

- Scroll down to the disks section and delete the CD-ROM and DISK by clicking the **X** icon for each item.
- Click **Save** to finalize the changes.

Now attempt to power on that VM and open its console window.

- Note that the VM no longer has any disks to boot from and that the 2048 game is displayed.

Power off the VM.

Select the VM, then click **VM Snapshots** from the menu below the list of VMs.

Click **Restore** to revert the VM to the state it was in before you removed the disks.

Attempt to power on the VM and open the console.

Verify that the VM boots successfully and that its configuration has been restored.

Configure a Protection Domain (PD)
..................................

In **Prism Element > Data Protection**, click **Data Protection**, then click **Table**.

Click **+ Protection Domain** to create a PD, then click Async DR.

Provide a name for the PD, and click **Create**.

Select the VMs that you want be members of the PD:

- Filter or scroll to select the VMs you created in this bootcamp to be part of the PD.
- Scroll down and click **Protect Selected Entities**.
- The selected VMs appear in the right-hand side table. Click **Next**.

Configure a local schedule:

- Click **New Schedule**.
- Select a frequency (for example, repeat every one day).

Configure a retention policy:

- Set the retention policy (for example, keep the last two snapshots).

.. note::

  Local is the only option in this lab environment because no remote targets are configured.

  You could setup a remote site with a neighbor cluster.

Click **Create Schedule**.

.. note::

  A Protection Domain can have multiple schedules.

Click **Close** to exit.

Takeaways
+++++++++

- Nutanix offers data protection solutions for virtual datacenters via different strategies including one-to-one or one-to-many replication.
- Nutanix provides data protection functions at the VM, file, and volume group level, so VMs and data remain safe in a crash-consistent environment.
- You can implement a data protection strategy by configuring protection domains and remote sites through the web console.
