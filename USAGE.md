# GH ES CLI usage documentation

## gh es configure

```
gh es configure [flags]
```

Configures the CLI to be able to connect with the Manage GitHub Enterprise Server API and stores the configuration and provided authentication parameters locally.

### Options


<dl class="flags">
<dt><code>-t</code>, <code>--auth-type &lt;string&gt;</code></dt>
<dd>Type of authentication to use: {root site administrator|Management Console user account|internal API key}</dd>

<dt><code>-a</code>, <code>--auto</code></dt>
<dd>Use to auto-configure when running locally on the GHES instance (using internal API key authentication only)</dd>

<dt><code>-b</code>, <code>--bootstrap</code></dt>
<dd>Use bootstrap mode to only set the hostname for the initial configuration of a GHES appliance</dd>

<dt><code>-n</code>, <code>--hostname &lt;string&gt;</code></dt>
<dd>GHES instance hostname</dd>

<dt><code>-p</code>, <code>--password &lt;string&gt;</code></dt>
<dd>Password to authenticate with</dd>

<dt><code>-r</code>, <code>--reset</code></dt>
<dd>Use to reset and delete the currently configured CLI credentials locally</dd>

<dt><code>-s</code>, <code>--status</code></dt>
<dd>View current configuration status and verify connectivity</dd>

<dt><code>-u</code>, <code>--username &lt;string&gt;</code></dt>
<dd>Username to authenticate with</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Configure the CLI and enter the credentials interactively
$ gh es configure

# Configure the CLI and provide credentials as flags
$ gh es configure --hostname ghes.github.net --auth-type "root site administrator" --password passworD1

# View the current status of the local CLI configuration and verify the connection
$ gh es configure --status

# Configure CLI in bootstrap mode for the initial configuration of a GitHub Enterprise Server appliance
$ gh es configure --bootstrap

# Reset the local CLI configuration
$ gh es configure --reset
```

## gh es ping

```
gh es ping
```

Ping the GitHub Enterprise Server instance and verify the stored API credentials.

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es access set-password

```
gh es access set-password [flags]
```

Update GHES root site administrator password which is also used for access to the Management Console.
In the case that the CLI is currently configured using the root site administrator, the stored authentication parameters need to be updated by running the `configure` command.

### Options


<dl class="flags">
<dt><code>-p</code>, <code>--password &lt;string&gt;</code></dt>
<dd>New Password</dd>

<dt><code>-c</code>, <code>--password-confirmation &lt;string&gt;</code></dt>
<dd>Password Confirmation</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
$ gh es access set-password --password passworD1 --password-confirmation passworD1
```

## gh es access get-ssh-key

```
gh es access get-ssh-key
```

Get SSH keys from the authorized_keys file on all configured nodes.

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Get configured SSH keys.
$ gh es access get-ssh-key
```

## gh es access add-ssh-key

```
gh es access add-ssh-key [flags]
```

Add SSH key to the authorized_keys file on all configured nodes.

### Options


<dl class="flags">
<dt><code>-i</code>, <code>--file &lt;string&gt;</code></dt>
<dd>Path of the SSH key to add</dd>

<dt><code>-k</code>, <code>--key &lt;string&gt;</code></dt>
<dd>SSH key to add</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Add an SSH Key.
$ gh es access add-ssh-key -k "ssh-rsa..."

# Add an SSH Key from a file.
$ gh es access add-ssh-key -i "/path/to/key.pub"
```

## gh es access remove-ssh-key

```
gh es access remove-ssh-key [flags]
```

Remove SSH key from the authorized_keys file on all configured nodes.

### Options


<dl class="flags">
<dt><code>-i</code>, <code>--file &lt;string&gt;</code></dt>
<dd>Path of the SSH key to remove</dd>

<dt><code>-k</code>, <code>--key &lt;string&gt;</code></dt>
<dd>SSH key to remove</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Remove an SSH Key.
$ gh es access remove-ssh-key -k "ssh-rsa..."

# Remove an SSH Key from a file.
$ gh es access remove-ssh-key -i "/path/to/key.pub"
```

## gh es cluster status

```
gh es cluster status [flags]
```

Get the status of services running on each cluster node.

### Options


<dl class="flags">
<dt><code>-r</code>, <code>--cluster-role &lt;string&gt;</code></dt>
<dd>Filter by cluster role</dd>

<dt><code>-u</code>, <code>--uuid &lt;string&gt;</code></dt>
<dd>Filter by node</dd>

<dt><code>--verbose</code></dt>
<dd>Output detailed status for each cluster node and included services</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es config init

```
gh es config init [flags]
```

Bootstrap the GitHub Enterprise Server instance by initializing the configuration with a license and password.

### Options


<dl class="flags">
<dt><code>-l</code>, <code>--license &lt;string&gt;</code></dt>
<dd>Path to license file</dd>

<dt><code>-p</code>, <code>--password &lt;string&gt;</code></dt>
<dd>Password for the root site administrator</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es config get-metadata

```
gh es config get-metadata [flags]
```

Get GHES metadata for all configured nodes.

### Options


<dl class="flags">
<dt><code>-r</code>, <code>--cluster-role &lt;string&gt;</code></dt>
<dd>Filter by cluster role</dd>

<dt><code>-u</code>, <code>--uuid &lt;string&gt;</code></dt>
<dd>Filter by node</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es config apply

```
gh es config apply [flags]
```

Initiate a config-apply run on all configured nodes.

### Options


<dl class="flags">
<dt><code>-i</code>, <code>--run-id &lt;string&gt;</code></dt>
<dd>Filter by run id</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Trigger configapply run on the appliance.
$ gh es config apply
```

## gh es config get-apply-status

```
gh es config get-apply-status [flags]
```

Check config apply status on all configured nodes.

### Options


<dl class="flags">
<dt><code>-r</code>, <code>--cluster-role &lt;string&gt;</code></dt>
<dd>Filter by cluster role</dd>

<dt><code>-i</code>, <code>--run-id &lt;string&gt;</code></dt>
<dd>Filter by run id</dd>

<dt><code>-u</code>, <code>--uuid &lt;string&gt;</code></dt>
<dd>Filter by node</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Check config-apply status on all nodes.
$ gh es config get-apply-status

# Check config-apply status on a specific node identified by its UUID (node metadata can be retrieved with 'gh es config metadata').
$ gh es config get-apply-status --uuid 12345678-1234-1234-1234-123456789012

# Check config-apply status on all nodes with a specific cluster role.
$ gh es config get-apply-status --cluster-role WebServer

# Check config-apply status on all nodes with a specific run id.
$ gh es config get-apply-status --run-id 123456
```

## gh es config get-apply-events

```
gh es config get-apply-events [flags]
```

Check config apply events on all configured nodes.

### Options


<dl class="flags">
<dt><code>-r</code>, <code>--cluster-role &lt;string&gt;</code></dt>
<dd>Filter by cluster role</dd>

<dt><code>-i</code>, <code>--event-id &lt;string&gt;</code></dt>
<dd>Filter by event id</dd>

<dt><code>-u</code>, <code>--uuid &lt;string&gt;</code></dt>
<dd>Filter by node</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Check config-apply events on all nodes.
$ gh es config get-apply-events"

# Check config-apply events on a specific node identified by its UUID (node metadata can be retrieved with 'gh es config metadata').
$ gh es config get-apply-events" --uuid 12345678-1234-1234-1234-123456789012

# Check config-apply events on all nodes with a specific cluster role.
$ gh es config get-apply-events" --cluster-role WebServer

# Check config-apply events on all nodes with a specific evnt id.
$ gh es config get-apply-events" --event-id 12345678
```

## gh es config get-license

```
gh es config get-license
```

Display the license information. Provide information about topology, seat counts, expiration date, etc...

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es config check-license

```
gh es config check-license
```

Check the license information. Perform various checks like expiration date, topology check and file integrity.

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es config import-license

```
gh es config import-license [flags]
```

Import a new license. This does not immediately apply the license to the GitHub Enterprise Server, and requires a config-apply run to use the new license.

### Options


<dl class="flags">
<dt><code>-a</code>, <code>--apply</code></dt>
<dd>Wheter the license import command will rebuild the github application and apply the new license</dd>

<dt><code>-l</code>, <code>--license &lt;string&gt;</code></dt>
<dd>Path to license file</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es config get-settings

```
gh es config get-settings [flags]
```

Get current settings of the GitHub Enterprise Server instance, which are ready to be applied.

### Options


<dl class="flags">
<dt><code>-t</code>, <code>--target-hostname &lt;string&gt;</code></dt>
<dd>(Optional) Run on node with specific hostname. Default to the cluster delegate.</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es config set-settings

```
gh es config set-settings [flags]
```

Update a subset or all of GHES settings in preparation to applying them.

### Options


<dl class="flags">
<dt><code>-s</code>, <code>--settings &lt;string&gt;</code></dt>
<dd>Provide updated settings as JSON string</dd>

<dt><code>-t</code>, <code>--target-hostname &lt;string&gt;</code></dt>
<dd>(Optional) Run on node with specific hostname. Default to the cluster delegate.</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Update settings with a JSON string interactively
$ gh es config set-settings

# Supply settings to be updated as a JSON string
$ gh es config set-settings --settings '{"abuse_rate_limiting":{"cpu_millis_per_minute":500}}'
```

## gh es maintenance set

```
gh es maintenance set [flags]
```

Configure the maintenance mode on all configured or specific UUID-identified  nodes, including setting an IP exception list, enabling on a scheduled time in the future and providing a custom maintenance mode message.

### Options


<dl class="flags">
<dt><code>-e</code>, <code>--enabled &lt;string&gt;</code></dt>
<dd>Enable/disable maintenance mode: {true|false}</dd>

<dt><code>-i</code>, <code>--ip-exception-list &lt;strings&gt;</code></dt>
<dd>Configure an IP exception list by entering comma separated IP addresses or CIDR blocks</dd>

<dt><code>-m</code>, <code>--message &lt;string&gt;</code></dt>
<dd>Customize maintenance mode message</dd>

<dt><code>-u</code>, <code>--uuid &lt;string&gt;</code></dt>
<dd>Change maintenance mode for a specific node by entering node uuid</dd>

<dt><code>-w</code>, <code>--when &lt;string&gt;</code></dt>
<dd>Configure when to enable/disable maintenance mode, enter 'now' or a RFC3339 format time (e.g. '2024-01-02T15:04:05+00:00')</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Enable maintenance mode on all configured nodes.
$ gh es maintenance set --enabled true

# Disable maintenance mode on all configured nodes.
$ gh es maintenance set --enabled false

# Enable maintenance mode on a UUID-identified node (node metadata can be retrieved with 'gh es config metadata').
$ gh es maintenance set --enabled true --uuid 12345678-1234-1234-1234-123456789012

# Enable maintenance mode on all configured nodes on a schedule.
$ gh es maintenance set --enabled true --when 2024-01-02T15:04:05+00:00

# Enable maintenance mode on all configured nodes with an IP exception list, making the GHES appliance only accessible by the set IP addresses or CIDR blocks.
$ gh es maintenance set --enabled true --ip-exception-list "10.0.1.2,192.168.0.0/16"

# Enable maintenance mode on all configured nodes and display a custom message to end users.
$ gh es maintenance set --enabled true --message "Unavailable due to upgrade"
```

## gh es maintenance get

```
gh es maintenance get [flags]
```

Check maintenance status on all configured nodes.

### Options


<dl class="flags">
<dt><code>-r</code>, <code>--cluster-role &lt;string&gt;</code></dt>
<dd>Filter by cluster role</dd>

<dt><code>-u</code>, <code>--uuid &lt;string&gt;</code></dt>
<dd>Filter by node</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
# Check maintenance status on all nodes.
$ gh es maintenance get

# Check maintenance status on a specific node identified by its UUID (node metadata can be retrieved with 'gh es config metadata').
$ gh es maintenance get --uuid 12345678-1234-1234-1234-123456789012

# Check maintenance status on all nodes with a specific cluster role.
$ gh es maintenance get --cluster-role WebServer
```

## gh es release version

```
gh es release version [flags]
```

Get GHES version for all configured nodes.

### Options


<dl class="flags">
<dt><code>-r</code>, <code>--cluster-role &lt;string&gt;</code></dt>
<dd>Filter by cluster role</dd>

<dt><code>-u</code>, <code>--uuid &lt;string&gt;</code></dt>
<dd>Filter by node</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es replication status

```
gh es replication status [flags]
```

Show replication status for each replication channel to the primary.

### Options


<dl class="flags">
<dt><code>-r</code>, <code>--cluster-role &lt;string&gt;</code></dt>
<dd>Filter by cluster role</dd>

<dt><code>-u</code>, <code>--uuid &lt;string&gt;</code></dt>
<dd>Filter by node</dd>

<dt><code>--verbose</code></dt>
<dd>Output detailed status for each replication and included services</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es topologyconfig get

```
gh es topologyconfig get
```

Get topology configuration from the GHES instance in INI style.

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es topologyconfig set

```
gh es topologyconfig set [flags]
```

Set GHES topology configuration by providing a path to the cluster configuration file. This command will store the uploaded configuration in the configuration management service.

### Options


<dl class="flags">
<dt><code>-c</code>, <code>--config &lt;string&gt;</code></dt>
<dd>path to the cluster configuration file</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
$ gh es topologyconfig set --config /data/user/common/cluster.conf"
```

## gh es topologyconfig verify

```
gh es topologyconfig verify [flags]
```

Verify GHES topology configuration by providing a path to the cluster configuration file. This command will not apply or upload the configuration.

### Options


<dl class="flags">
<dt><code>-c</code>, <code>--config &lt;string&gt;</code></dt>
<dd>path to the cluster configuration file</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
$ gh es topologyconfig verify --config /data/user/common/cluster.conf
```

## gh es topologyconfig diff

```
gh es topologyconfig diff [flags]
```

Compares the existing GHES topology configurations with a provided cluster configuration file. This command will not apply or upload the configuration.

### Options


<dl class="flags">
<dt><code>-c</code>, <code>--config &lt;string&gt;</code></dt>
<dd>path to the cluster configuration file</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### Examples

```bash
$ gh es topologyconfig diff --config /data/user/common/cluster.conf
```

## gh es checks system-requirements

```
gh es checks system-requirements [flags]
```

Check if the configured cluster nodes meet the minimum system requirements in terms of memory, block storage size and root storage size depending on their configured role.

### Options


<dl class="flags">
<dt><code>-c</code>, <code>--cluster_config &lt;string&gt;</code></dt>
<dd>Provide path for cluster config file</dd>

<dt><code>-e</code>, <code>--external_hostname &lt;string&gt;</code></dt>
<dd>(Optional) Provide a hostname to reach the cluster</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


## gh es checks connectivity

```
gh es checks connectivity [flags]
```

Check if esstential ports are reachable on the cluster nodes.

### Options


<dl class="flags">
<dt><code>-c</code>, <code>--cluster_config &lt;string&gt;</code></dt>
<dd>(Optional) Provide path for cluster config file. Defaults to the current cluster topology</dd>

<dt><code>-t</code>, <code>--timeout &lt;string&gt;</code></dt>
<dd>(Optional) Provide a timeout for the check. Defaults to 60</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


