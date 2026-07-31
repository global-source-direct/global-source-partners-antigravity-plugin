# GlobalSource Partners for Google Antigravity

Access expert emerging-markets research from [GlobalSource Partners](https://www.globalsourcepartners.com/) directly within Google Antigravity.

This plugin connects Antigravity to the GlobalSource Partners remote Model Context Protocol (MCP) server, enabling its agents to search research covering economics, politics, public policy and sovereign risk.

## Features

* Search research by topic, country, company or individual.
* Find relevant reports and analysis.
* Filter research by entity and publication date.
* Access publicly available research without signing in.
* Authenticate as a GlobalSource Partners client for expanded access.

## Requirements

* [Google Antigravity CLI](https://antigravity.google/docs/cli/install)
* Git

## Install Antigravity CLI

On macOS or Linux, use Google’s installation script:

```bash
curl -fsSL https://antigravity.google/cli/install.sh | bash
```

On macOS, you can alternatively install it with Homebrew:

```bash
brew install --cask antigravity-cli
```

Launch Antigravity and complete the browser-based sign-in:

```bash
agy
```

## Install this plugin

Clone the repository:

```bash
git clone https://github.com/global-source-direct/global-source-partners-antigravity-plugin.git
```

Install the plugin:

```bash
agy plugin install ./global-source-partners-antigravity-plugin
```

Confirm that it is installed:

```bash
agy plugin list
```

Restart Antigravity after installation:

```bash
agy
```

Inside Antigravity, enter:

```text
/mcp
```

The MCP manager should show `global-source-partners` as connected and list its available research tools.

## Usage

Ask Antigravity questions such as:

```text
Using GlobalSource Partners research, summarise the latest analysis on Brazil.
```

```text
What does GlobalSource Partners research say about Argentina's economic outlook?
```

```text
Find recent research concerning sovereign risk in emerging markets.
```

```text
What are GlobalSource Partners analysts saying about monetary policy in Mexico?
```

Antigravity will invoke the GlobalSource Partners MCP tools when they are relevant to your request.

## Client authentication

The GlobalSource Partners MCP server provides public access without requiring authentication.

GlobalSource Partners clients can authenticate for expanded access to research included in their subscription. Antigravity supports automatic OAuth discovery and Dynamic Client Registration, so no OAuth client credentials need to be added to the plugin.

To authenticate:

1. Open Antigravity settings using `Cmd+,` on macOS or `Ctrl+,` on Windows and Linux.
2. Open **Customizations**.
3. Find the `global-source-partners` MCP server.
4. Click **Authenticate**.
5. Complete the authorization process in your browser.
6. Return to Antigravity and confirm that the server reconnects.

Availability of research after authentication depends on the user’s GlobalSource Partners subscription.

## Plugin structure

```text
global-source-partners-antigravity-plugin/
├── plugin.json
├── mcp_config.json
├── README.md
└── rules/
    └── global-source-partners.md
```

The `plugin.json` file identifies the Antigravity plugin:

```json
{
  "$schema": "https://antigravity.google/schemas/v1/plugin.json",
  "name": "global-source-partners",
  "description": "Search expert emerging-markets research on economics, politics, policy and sovereign risk."
}
```

The `mcp_config.json` file connects Antigravity to the remote Streamable HTTP MCP server:

```json
{
  "mcpServers": {
    "global-source-partners": {
      "serverUrl": "https://www.globalsourcepartners.com/mcp"
    }
  }
}
```

## Managing the plugin

List installed plugins:

```bash
agy plugin list
```

Disable the plugin:

```bash
agy plugin disable global-source-partners
```

Enable it again:

```bash
agy plugin enable global-source-partners
```

Uninstall it:

```bash
agy plugin uninstall global-source-partners
```

To install an updated version, pull the latest repository changes and reinstall the plugin:

```bash
cd global-source-partners-antigravity-plugin
git pull
cd ..
agy plugin uninstall global-source-partners
agy plugin install ./global-source-partners-antigravity-plugin
```

## MCP server

This plugin connects to:

```text
https://www.globalsourcepartners.com/mcp
```

The server is published in the official Model Context Protocol Registry as:

```text
com.globalsourcepartners/emerging-markets-research
```

## About GlobalSource Partners

[GlobalSource Partners](https://www.globalsourcepartners.com/) provides independent, locally based economic and political research covering emerging and frontier markets.

Its network of in-country experts provides investors and decision-makers with analysis of economics, politics, public policy and sovereign risk.

## Privacy and terms

Use of the GlobalSource Partners service is subject to the policies and terms published on the [GlobalSource Partners website](https://www.globalsourcepartners.com/).

When Antigravity uses this plugin, relevant portions of the user’s request are sent to the GlobalSource Partners MCP server to perform searches and retrieve research.
