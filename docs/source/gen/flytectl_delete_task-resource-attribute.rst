.. _flytectl_delete_task-resource-attribute:

flytectl delete task-resource-attribute
---------------------------------------

Deletes matchable resources of task attributes

Synopsis
~~~~~~~~



Deletes task  resource attributes for given project,domain combination or additionally with workflow name.

Deletes task resource attribute for project and domain
Here the command delete task resource attributes for  project flytectldemo and development domain.
::

 flytectl delete task-resource-attribute -p flytectldemo -d development 


Deletes task resource attribute using config file which was used for creating it.
Here the command deletes task resource attributes from the config file tra.yaml
defaults/limits are optional in the file as they are unread during the delete command but can be kept as the same file can be used for get, update or delete 
eg:  content of tra.yaml which will use the project domain and workflow name for deleting the resource

::

 flytectl delete task-resource-attribute --attrFile tra.yaml


.. code-block:: yaml

    domain: development
    project: flytectldemo
    defaults:
      cpu: "1"
      memory: "150Mi"
    limits:
      cpu: "2"
      memory: "450Mi"

Deletes task resource attribute for a workflow
Here the command deletes task resource attributes for a workflow core.control_flow.run_merge_sort.merge_sort

::

 flytectl delete task-resource-attribute -p flytectldemo -d development core.control_flow.run_merge_sort.merge_sort

Usage


::

  flytectl delete task-resource-attribute [flags]

Options
~~~~~~~

::

      --attrFile string   attribute file name to be used for delete attribute for the resource type.
  -h, --help              help for task-resource-attribute

Options inherited from parent commands
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

  -c, --config string    config file (default is $HOME/.flyte/config.yaml)
  -d, --domain string    Specifies the Flyte project's domain.
  -o, --output string    Specifies the output type - supported formats [TABLE JSON YAML DOT DOTURL]. NOTE: dot, doturl are only supported for Workflow (default "TABLE")
  -p, --project string   Specifies the Flyte project.

SEE ALSO
~~~~~~~~

* :doc:`flytectl_delete` 	 - Used for terminating/deleting various flyte resources including tasks/workflows/launchplans/executions/project.

