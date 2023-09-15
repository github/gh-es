# GH ES CLI usage documentation

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


### See also

* [es access]
## gh es access

Manage access to all configured GHES nodes

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es]
## gh es cluster status

```
gh es cluster status [flags]
```

Get the status of services running on each cluster node

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


### See also

* [es cluster]
## gh es cluster

Perform operations on GHES cluster

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es]
## gh es config metadata

```
gh es config metadata [flags]
```

Get GHES metadata of all configured nodes

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


### See also

* [es config]
## gh es config

Get GHES configuration information of all configured nodes

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es]
## gh es configure

```
gh es configure [flags]
```

Configures the CLI to be able to connect with the GitHub Enterprise Manage API and stores the configuration and provided authentication parameters locally.

### Options


<dl class="flags">
<dt><code>-t</code>, <code>--auth-type &lt;string&gt;</code></dt>
<dd>Type of authentication to use: {root site administrator|Management Console user account|internal API key}</dd>

<dt><code>-a</code>, <code>--auto</code></dt>
<dd>Use to auto-configure when running locally on the GHES instance (using internal API key authentication only)</dd>

<dt><code>-n</code>, <code>--hostname &lt;string&gt;</code></dt>
<dd>GHES instance hostname</dd>

<dt><code>-p</code>, <code>--password &lt;string&gt;</code></dt>
<dd>Password to authenticate with</dd>

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


### See also

* [es]
## gh es help

```
gh es help [command]
```

Help provides help for any command in the application.
Simply type es help [path to command] for full details.

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es]
## gh es maintenance get

```
gh es maintenance get [flags]
```

Check maintenance status on all configured nodes

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


### See also

* [es maintenance]
## gh es maintenance set

```
gh es maintenance set [flags]
```

Configure the maintenance mode on all configured nodes, including setting an IP Exception List, enabling on a scheduled time in the future and providing a custom maintenance mode message.

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
<dd>Configure when to enable/disable maintenance mode, enter 'now' or a RFC3339 format time</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es maintenance]
## gh es maintenance

```
gh es maintenance
```

Enable or disable maintenance mode on all configured nodes

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es]
## gh es ping

```
gh es ping
```

Ping the instance

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es]
## gh es release version

```
gh es release version [flags]
```

Get GHES version of all configured nodes

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


### See also

* [es release]
## gh es release

Get GHES release information of all configured nodes

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es]
## gh es replication status

```
gh es replication status [flags]
```

Show replication status for each replication channel to the primary

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


### See also

* [es replication]
## gh es replication

Perform operations on GHES replication

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es]
## gh es topologyconfig get

```
gh es topologyconfig get
```

Get topology configuration from GHES instance in INI-style

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es topologyconfig]
## gh es topologyconfig set

```
gh es topologyconfig set [flags]
```

Set GHES topology configuration by providing an INI-style configuration string

### Options


<dl class="flags">
<dt><code>-c</code>, <code>--config &lt;string&gt;</code></dt>
<dd>Configure topology by providing  string in INI-style</dd>
</dl>


### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es topologyconfig]
## gh es topologyconfig

```
gh es topologyconfig
```

Get or set topology configuration

### Options inherited from parent commands


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


### See also

* [es]
## gh es

A GitHub CLI extension to manage your GHES instance 

### Options


<dl class="flags">
<dt><code>--json</code></dt>
<dd>Format results as JSON</dd>
</dl>


