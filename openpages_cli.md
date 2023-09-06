---

copyright:
  years: 2015, 2023
lastupdated: "2023-07-31"

subcollection: openpages

keywords: _OpenPages_ CLI, _OpenPages_ command line , _OpenPages CLI_ terminal, _OpenPages CLI_ shell, _ObjectManager_

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.openpages_short}} CLI (ibmcloud openpages)
{: #openpages_CLI}

The {{site.data.keyword.openpages_short}} command-line interface (CLI) provides extra capabilities for {{site.data.keyword.openpages_short}}. For example, you can use {{site.data.keyword.openpages_short}} CLI to import and export configuration data, such as settings, application strings, role templates, and more.
{: shortdesc}

## Prerequisites
{: #openpages_CLI-prereq}

* Install the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started).
* Install the {{site.data.keyword.openpages_short}} CLI by running the following command:

   ```sh
   ibmcloud plugin install openpages
   ```
   {: pre}

* Before you run **`ibmcloud openpages`** commands, log in to {{site.data.keyword.cloud_notm}} by using the **`ibmcloud login`** command.
* Generate the template files for **`ibmcloud openpages`**. See [`ibmcloud openpages create-templates`]({: #ibmcloud_openpages_create-template})

   Copy the files to the directory where **`ibmcloud openpages`** is installed.

You're notified on the command line when updates to the {{site.data.keyword.cloud_notm}} CLI and plug-ins are available. Be sure to keep your CLI up to date so that you can use the latest commands. You can view the current version of all installed plug-ins by running **`ibmcloud plugin list`**.
{: tip}

{{site.data.keyword.cloud_notm}} CLI requires Java&trade; 1.8.0.
{: note}

## `ibmcloud openpages create-templates`
{: #ibmcloud_openpages_create-template}

Generates the following files:
-  **`objectmanager.properties`**
-  **`ObjectManagerExportFilters-Example.xml`**

Copy the generated files to the directory where **`ibmcloud openpages`** is installed.

You need to run the `ibmcloud openpages create-templates` command at least one time.

```sh
ibmcloud openpages om (create-templates|c) DIRECTORY
```
{: pre}

### Command options
{: #ibmcloud-openpages-create-templates-options}

`DIRECTORY` (string)
:   The full path of a local directory. The template files are created in this directory.

### Examples
{: #ibmcloud-openpages-create-templates-examples}

Create the templates and store them in the `\home\tmp\objectmanager` directory.

```sh
ibmcloud openpages c \home\tmp\objectmanager
```
{: screen}

## `ibmcloud openpages help`
{: #ibmcloud_openpages_help}

On its own, the **`ibmcloud openpages help`** command displays the available top-level commands. When followed by another command, it displays specific help for that command.

```sh
ibmcloud (openpages|op) help|h [command]
```
{: pre}

### Command options
{: #ibmcloud-openpages-help-options}

`command` (string)
:   An **`ibmcloud openpages`** command. Optional.

### Examples
{: #ibmcloud-openpages-help-examples}

Get a list of all **`ibmcloud openpages`** commands.
```sh
ibmcloud openpages help
```
{: screen}

Get help with the **`ibmcloud openpages objectmanager`** command.

```sh
ibmcloud openpages help objectmanager
```
{: screen}

## `ibmcloud openpages list`
{: #ibmcloud_openpages_list}

Use this command to get a list of all {{site.data.keyword.openpages_short}} instances in your IBM Cloud account.

```sh
ibmcloud (openpages|op) (list|ls)
```
{: pre}

### Command options
{: #ibmcloud-openpages-list-options}

None.

### Examples
{: #ibmcloud-openpages-list-examples}

```sh
ibmcloud openpages list
```
{: screen}

### Output
{: ##ibmcloud-openpages-list-output}

The command returns the following output:

```text
OpenPages application
0. instance_name (instance_GUID)
...
n. instance_name (instance_GUID)
No OpenPages application targeted.
```
{: screen}

## `ibmcloud openpages objectmanager`
{: #ibmcloud_openpages_objectmanager}

With the **`ibmcloud openpages objectmanager`** command, you can perform the following tasks:

-  Import (load) configuration data, such as object types and views, into OpenPages.
-  Export (dump) filtered or unfiltered configuration data from OpenPages. You can use this functionality, for example, to migrate configuration data from one instance to another.
-  Batch-load multiple loader files in a single session.

If you want to import and export instance data, you can use FastMap.
{: tip}

If you want to migrate data from an OpenPages on-premises environment to OpenPages as a Service, contact Support.

The ObjectManager commands are:

`batch`
:   Load (import) multiple loader XML files.

`create-templates`
:   Generate the **`objectmanager.properties`** and **`ObjectManagerExportFilters-Example.xml`** files.

`dump`
:   Dump (export) to XML.

`help`
:   Get help for the **`ibmcloud openpages objectmanager`** command.

`load`
:   Load (import) from a single loader XML file.

`validate`
:   Check that a single loader file is well-formed.

### **`ibmcloud openpages objectmanager batch`**
{: #ibmcloud-openpages-objectmanager-batch}

Use this command to load (import) multiple loader files.

```sh
ibmcloud (openpages|op) (objectmanager|om) batch BATCH_LOADER_DIR BATCH_LOADER_LIST_FILE
```
{: pre}

#### Command options
{: #ibmcloud-openpages-batch-options}

`BATCH_LOADER_DIR`
:   The directory where the BATCH_LOADER_LIST_FILE file and the loader files are stored.

`BATCH_LOADER_LIST_FILE`
:   The file name of the batch loader list file.

#### Prerequisites
{: #ibmcloud_openpages_objectmanager-prereqs-batch}

* Set a target instance by using the **`ibmcloud openpages select`** command.

* Create a batch loader list file that lists one or more XML loader files.

   For more information, see [Batch loader file syntax and sample](https://www.ibm.com/docs/en/SSFUEU_9.0.0/op_grc_admin/t_adm_objectmanager_sample_batch_loader_list_file.html).

#### Example: Batch mode
{: #ibmcloud-openpages-objectmanager-batch-example}

```sh
ibmcloud openpages om batch /op/batch_files/ batch_file_list.txt
```
{: screen}

##### Output
{: ##ibmcloud-openpages-objectmanager-output-batch}

The command returns the following output:

```text
Total Objects processed
Total Validation Errors
Total Exceptions
Processing finished
Elapsed time
Copied <file> to <directory>
```
{: screen}


### **`ibmcloud openpages objectmanager dump`**
{: #ibmcloud-openpages-objectmanager-dump}

Use this command to dump (export) data.

```sh
ibmcloud (openpages|op) (objectmanager|om) dump EXPORT_DIR FILE_PREFIX
```
{: pre}

#### Command options
{: #ibmcloud-openpages-dump-options}

`EXPORT_DIR`
:   The full path to the directory where the BATCH_LOADER_LIST_FILE file and the loader files are stored.

`FILE_PREFIX`
:   The prefix to append to the output file.

#### Prerequisites
{: #ibmcloud_openpages_objectmanager-prereqs-dump}

* Set a target instance by using the **`ibmcloud openpages select`** command.
* Use the **`objectmanager.properties`** file to specify the data to export.

   For more information, see [Modifying the ObjectManager properties file](https://www.ibm.com/docs/en/SSFUEU_9.0.0/op_grc_admin/t_adm_modifying_the_objectmanager_properties_file.html).

#### Example: Exporting data
{: #ibmcloud-openpages-objectmanager-dump-example}

```sh
ibmcloud openpages om dump /home/files object_types
```
{: screen}

##### Output
{: ##ibmcloud-openpages-objectmanager-output-dump}

The command creates the following file:
**`/home/files/object_types-op-config.xml`**


### **`ibmcloud openpages objectmanager load`**
{: #ibmcloud-openpages-objectmanager-load}

Use this command to load (import) data.

```sh
ibmcloud (openpages|op) (objectmanager|om) load LOADER_FILE_DIR FILE_PREFIX
```
{: pre}

#### Command options
{: #ibmcloud-openpages-load-options}

`LOADER_FILE_DIR`
:   The full path of the directory where the loader file is stored.

`FILE_PREFIX`
:   The prefix of the loader file.
:   For example, if the loader file is called `myfile-op-config.xml`, use `myfile` for this parameter.

#### Prerequisites
{: #ibmcloud_openpages_objectmanager-prereqs-load}

* Set a target instance by using the **`ibmcloud openpages select`** command.
* Prepare a loader file. The file name must use the pattern `*-op-config.xml`.

   For more information, see [Working with loader files](https://www.ibm.com/docs/en/SSFUEU_9.0.0/op_grc_admin/c_adm_working_with_loader_files.html).

#### Example: Importing data
{: #ibmcloud-openpages-objectmanager-load-example}

```sh
ibmcloud openpages om load /home/loader_files myfile
```
{: screen}

##### Output
{: ##ibmcloud-openpages-objectmanager-output-load}

The command returns the following output:

```text
?
Total Objects processed
Total Validation Errors
Total Exceptions
Processing finished
Elapsed time
Copied <file> to <directory>
```
{: screen}


### **`ibmcloud openpages objectmanager validate`**
{: #ibmcloud-openpages-objectmanager-validate}

Use this command to verify that a loader file is well-formed.

```sh
ibmcloud (openpages|op) (objectmanager|om) validate LOADER_FILE_DIR FILE_PREFIX
```
{: pre}

#### Command options
{: #ibmcloud-openpages-validate-options}

`LOADER_FILE_DIR`
:   The full path of the directory where the loader file is stored.

`FILE_PREFIX`
:   The prefix of the loader file.
:   For example, if the loader file is called `myfile-op-config.xml`, use `myfile` for this parameter.


#### Prerequisites
{: #ibmcloud_openpages_objectmanager-prereqs-validate}

* Set a target instance by using the **`ibmcloud openpages select`** command.
* Requires a single loader file. The file name must use the pattern `*-op-config.xml`.

#### Example: Validating a file
{: #ibmcloud-openpages-objectmanager-validate-example}

```sh
ibmcloud openpages om validate /home/loader_files myfile
```
{: screen}

##### Output
{: ##ibmcloud-openpages-objectmanager-output-validate}

The command returns the following output:

```text
?
Total Objects processed
Total Validation Errors
Total Exceptions
Processing finished
Elapsed time
Copied <file> to <directory>
```
{: screen}

## `ibmcloud openpages select`
{: #ibmcloud_openpages_select}

Use this command to select the {{site.data.keyword.openpages_short}} instance on which you want to run subsequent commands.

```sh
ibmcloud (openpages|op) (select|s) [GUID]
```

### Command options
{: #ibmcloud-openpages-select-options}

`[GUID]` (string)
:   The GUID of the instance you want to select. If you leave this parameter empty, the command returns a numbered list of instances. Type the number of the instance that you want to select.

### Examples
{: #ibmcloud-openpages-select-examples}

Get a numbered list of instances.

```sh
ibmcloud openpages select
```
{: pre}

### Output
{: ##ibmcloud-openpages-select-output}

The command returns the following output:

```text
OpenPages application
0. instance_name (instance_GUID)
1. instance_name (instance_GUID)
No OpenPages application targeted.
```
{: screen}

## `ibmcloud openpages unselect`
{: #ibmcloud_openpages_unselect}

Use this command to deselect an {{site.data.keyword.openpages_short}} instance.

```sh
ibmcloud (openpages|op) (unselect|u) [GUID]
```

### Command options
{: #ibmcloud-openpages-unselect-options}

`GUID` (string)
:   The GUID of the instance you want to deselect. If you leave this parameter empty, the command returns a numbered list of instances. Type the number of the instance that you want to deselect.

### Examples
{: #ibmcloud-openpages-unselect-examples}

Get a numbered list of instances that are currently selected.

```sh
ibmcloud openpages unselect <instance_GUID>
```
{: pre}

### Output
{: ##ibmcloud-openpages-unselect-output}

The command returns the following output:

```text
?
```
{: screen}
