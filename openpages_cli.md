---

copyright:
  years: 2015, 2023
lastupdated: "2023-07-31"

subcollection: openpages

keywords: _OpenPages_ CLI, _OpenPages_ command line , _OpenPages CLI_ terminal, _OpenPages CLI_ shell, _ObjectManager_

---

{{site.data.keyword.attribute-definition-list}}

<!-- File guidance:
This template is for introducing a command-line interface (CLI). It is a reference template intended to document productive use of the CLI. It is not intended for task information.
Name your file `offering-cli-name.md`, for example, `container-registry-cli.md` is the file name of the Container Registry CLI reference topic. Delete content examples and coding that you are not using for your offering. -->

<!-- Title guidance:
Add a title that describes your CLI and includes the base command. Formatting guidelines depend on how your content is delivered:
- As part of the core CLI: Provide a goal-oriented title, such as "Searching and managing the IBM Cloud catalog (ibmcloud catalog)": https://cloud.ibm.com/docs/cli?topic=cloud-cli-ibmcloud_catalog

- As a CLI plug-in: List the name of your CLI, such as "Container Registry CLI (ibmcloud cr): https://cloud.ibm.com/docs/cli?topic=container-registry-cli-plugin-containerregcli

Also provide an appropriate ID above that aligns with your offering name, for example: #container-registry-cli. *All* IDs must be unique across *all* CLI references. -->

# {{site.data.keyword.openpages_short}} CLI
{: #openpages_CLI}

<!-- Short description: REQUIRED
The short description section should include one to two sentences describing why a developer would want to use this cli. This should be conversational style. For search engine optimization, include your offering's CLI name. Keep the {: shortdesc} after the first paragraph so that the framework renders it properly.
Example: -->

The {{site.data.keyword.cloud}} command-line interface (CLI) provides extra capabilities for service offerings. You can use {{site.data.keyword.cloud_notm}} CLI to manage V2 service brokers and templates.
{: shortdesc}

<!-- Prerequisites: REQUIRED FOR PLUG-INS
This section tells users what's required to use the CLI commands.
- If your CLI is delivered as part of the core IBM Cloud CLI (not separately installable), this section isn't required.
- If your CLI is delivered as a plug-in to the core IBM Cloud CLI, include installation commands. If your plug-in requires detailed or lengthy configuration steps, link out to a separate task topic. -->

<!-- Change ID below to match your CLI. -->
## Prerequisites
{: #openpages_CLI-prereq}

* Install the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started).
* Install the {{site.data.keyword.openpages_short}} CLI by running the following command:

   ```sh
   ibmcloud plugin install openpages-cli
   ```
   {: pre}

   <!-- Replace the <cli-plugin> above with the name of your CLI plug-in. Run 'ibmcloud plugin repo-plugins' to find the name.-->

<!-- Optionally include any other post-installation configuration that might be required for your service. -->

You're notified on the command line when updates to the {{site.data.keyword.cloud_notm}} CLI and plug-ins are available. Be sure to keep your CLI up to date so that you can use the latest commands. You can view the current version of all installed plug-ins by running **`ibmcloud plugin list`**.
{: tip}

<!-- Other Prerequisites/Authorization/Environment: OPTIONAL
List any other prerequisites/authorization/environments that are required to use the CLI commands. Or give a brief introduction to the prerequisites/authorization/environments that the CLI commands might use. Use H3 headings (###) as needed to organize your content.
Example: -->

{{site.data.keyword.cloud_notm}} CLI requires Java&trade 1.8.0.
{: note}

<!-- Command entries: REQUIRED
Directly use the command name as title.  Add an anchor ID, for example, {: #login}, for each command entry. Include a sentence to briefly introduce the command, such as what the command does.

**Command syntax**: Add the command syntax by using three backticks before and after the syntax (```).

**Command options**: Use a definition list to introduce the options. Make one option a single list item.

Examples: Include one sentence to describe each example. Use 1 - 3 examples depending on the command's complexity, and use examples that show different parts of the command's functionality. For very complex commands, you can include additional examples, but make sure they're not too repetitive.
* Add the example by using three backticks ahead of and after the example (```)
* For copyable code snippets, multi-line, include {: codeblock} following the last set of backticks. A copy button will display in the framework output.
* For copyable commands, single line, include {: pre} following the last set of backticks. When displayed, it will show "$" at the beginning of the command example and a copy button, but the copy button will include just the command example.

Required command options should be listed without brackets, for example `-a API_ENDPOINT`. Command options that aren't required should be listed in [] square brackets within the command syntax example., such as `[--org ORG]`.

**Optional options**: Options that aren't required should be placed in the option's description, and notated in [] within the command syntax statement.

For example, the following command syntax has the optional options -o, -s and -r.
```
ibmcloud account user-invite USER_EMAIL [-o, --org ORG [--org-role ORG_ROLE]] [-s, --space SPACE, [--space-role SPACE_ROLE]] [-r, --region REGION]
```

* For each option, include in the option's description what the default behavior is if you don't specify it. For example, "If not specified, the default value is `true`." Not all options have a default value.
* Surround all values that the user inputs in `backticks` to denote that it's a literal value. For example: "Valid values are `true` or `false`".

**Variables**: Document variables by using all caps.

**Mutually exclusive options**:
In the command syntax statement, to indicate options that are mutually exclusive, use a `|` pipe symbol as shown in the following example:
```
[--resource-group-id RESOURCE_GROUP_ID | --resource-group-name RESOURCE_GROUP_NAME]
```
In this example, `resource-group-id` and `resource-group-name` are exclusive.

**Command output**: If the command has output, include an example of what the user will see. Be sure not to include any real names, account numbers, resource CRNs, API keys, or other sensitive information. Above the command output, include a description of any key pieces that the user might need to pay attention to.

-->

## `ibmcloud openpages help`
{: #ibmcloud_openpages_help}

On its own, the **`ibmcloud openpages help`** command displays the available top-level commands. When followed by another command, it displays specific help for that command.

```sh
ibmcloud openpages (help|h) [command]
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
ibmcloud openpages (list|ls)
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
n. instance_name (instance_GUID)
No OpenPages application targeted.
```
{: screen}

## `ibmcloud openpages objectmanager`
{: #ibmcloud_openpages_objectmanager}

Use this command to import and export data. The **`ibmcloud openpages objectmanager`** command also supports batch operations.

For help, run the command with the `help` parameter.

The ObjectManager commands are:

`batch`
:   Load (import) multiple loader XML files.

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
ibmcloud openpages objectmanager batch BATCH_LOADER_DIR BATCH_LOADER_LIST_FILE
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

Requires a batch loader list file that lists one or more XML loader files.

For more information, see [Batch loader file syntax and sample](https://www.ibm.com/docs/en/SSFUEU_9.0.0/op_grc_admin/t_adm_objectmanager_sample_batch_loader_list_file.html).

#### Example: Batch mode
{: #ibmcloud-openpages-objectmanager-batch-example}

```sh
ibmcloud openpages objectmanager batch /op/batch_files/ batch_file_list.txt
```
{: screen}

##### Output
{: ##ibmcloud-openpages-objectmanager-output-batch}

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


### **`ibmcloud openpages objectmanager dump`**
{: #ibmcloud-openpages-objectmanager-dump}

Use this command to dump (export) data.

```sh
ibmcloud openpages objectmanager dump EXPORT_DIR FILE_PREFIX
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

Use the **`objectmanager.properties`** file to specify the data to export.

For more information, see [Modifying the ObjectManager properties file](https://www.ibm.com/docs/en/SSFUEU_9.0.0/op_grc_admin/t_adm_modifying_the_objectmanager_properties_file.html).

#### Example: Exporting data
{: #ibmcloud-openpages-objectmanager-dump-example}

```sh
ibmcloud openpages objectmanager dump /home/files object_types
```
{: screen}

##### Output
{: ##ibmcloud-openpages-objectmanager-output-dump}

The command creates the following file:
**`/home/files/object_types-op-config.xml file`**


### **`ibmcloud openpages objectmanager load`**
{: #ibmcloud-openpages-objectmanager-load}

Use this command to load (import) data.

```sh
ibmcloud openpages objectmanager load LOADER_FILE_DIR FILE_PREFIX
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

Requires a single loader file. The file name must use the pattern `*-op-config.xml`.

For more information, see [Working with loader files](https://www.ibm.com/docs/en/SSFUEU_9.0.0/op_grc_admin/c_adm_working_with_loader_files.html).

#### Example: Importing data
{: #ibmcloud-openpages-objectmanager-load-example}

```sh
ibmcloud openpages objectmanager load /home/loader_files myfile
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
ibmcloud openpages objectmanager validate LOADER_FILE_DIR FILE_PREFIX
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

Requires a single loader file. The file name must use the pattern `*-op-config.xml`.

#### Example: Validating a file
{: #ibmcloud-openpages-objectmanager-validate-example}

```sh
ibmcloud openpages objectmanager validate /home/loader_files myfile
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
ibmcloud openpages (select|s) [GUID]
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
ibmcloud openpages (unselect|u) [GUID]
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
