.. Adding labels to the beginning of your lab is helpful for linking to the lab from other pages
.. _example_lab_2:

-------------
Example Lab 2
-------------

Overview
++++++++

Here is where we provide a high level description of what the user will be doing during this module. We want to frame why this content is relevant to an SE/Services Consultant and what we expect them to understand after completing the lab.

Using Notes
+++++++++++

Notes provide easily noticable interjections to lab instructions. Reasons to use a note include calling attention to a step that requires additional context or referencing external resources. Make sure to include a return before and after the note directive for it to render properly. **Please don't abuse notes.**

.. note::

  Check out `this <http://openalea.gforge.inria.fr/doc/openalea/doc/_build/html/source/sphinx/rest_syntax.html>`_ cheat sheet for helpful documentation on formatting text, links, tables, etc. in Restructured Text.

Using Icons
+++++++++++

The Prism UI includes several unlabeled icons. When directing a user to one of these actions or menus, use the example inline markup below:

In **Prism**, click :fa:`cog` **> Manage VM High Availability**.

.. figure:: images/1.png

Under **Disks**, select :fa:`pencil` to change the **CD-ROM** device configuration.

.. figure:: images/2.png

Click :fa:`eject` to unmount the disk image from the **CD-ROM** device.

It is **not** necessary to include inline icons when the are accompanied by a label/text in the UI, such as :fa:`times` **Delete**

Using Codeblocks
++++++++++++++++

You can insert code into your lab guides both inline and via external files. Inline is a great option for providing command line instructions or display shorter code snippets.

.. note::

  `Here <http://www.sphinx-doc.org/en/stable/markup/code.html>`_ is a reference for even more code options available in Sphinx, including emphasizing individual lines.

Inline
......

Using an SSH client, execute the following:

.. code-block:: bash
  :name: inline-code-example
  :caption: INLINE CODE EXAMPLE

  > ssh nutanix@<NUTANIX-CLUSTER-IP>
  > acli
  <acropolis> vm.create XD num_vcpus=4 num_cores_per_vcpu=1 memory=8G
  <acropolis> vm.disk_create XD cdrom=true empty=true
  <acropolis> vm.disk_create XD clone_from_image=<Windows 2012 Disk Image Name>
  <acropolis> vm.nic_create XD network=<Network Name> ip=<XD IP Address>
  <acropolis> vm.on XD

.. note:: When using **acli**, you can use the Tab key to autocomplete fields. Pressing Tab twice lists available namespaces and values.

The name/caption arguments are optional, and should only be used is you need to reference the code from another part of the document, like this: :ref:`inline-code-example`

External File
.............

Use the literalinclude directive to create a code block from an external file. The best option when dealing with longer scripts or the content of the script is maintained separate from the lab guide.

.. literalinclude:: example.py
   :language: python
   :emphasize-lines: 2,7-8
   :linenos:
   :caption: EXAMPLE.PY
   :name: literal-include-example

.. note:: For proper color markup, specify the language of your code using one of the supported lexers found at `pygments.org <http://pygments.org/docs/lexers/>`_.

Using Links
+++++++++++

Here is a link to a `Another Term <../appendix/glossary.html#another-term>`_ in the `Glossary <../appendix/glossary.html>`_. This approach doesn't require labels in your .rst files, but requires you to know the name of the file and anchor to which you are linking.

Here is a link to `an external site <http://www.google.com>`_.

You can also link directly to labels in your .rst files using the **ref** directive. This approach will automatically expand the name of the heading to which the label is applied. Here is an example of linking to :ref:`example_lab_1`.

Takeaways
+++++++++

- Here is where we summarize any key takeaways from the module
- Such as how a Nutanix feature used in the lab delivers value
- Or highlighting a differentiator
