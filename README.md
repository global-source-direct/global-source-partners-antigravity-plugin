# GlobalSource Partners for Gemini CLI

Access expert emerging-markets research from [GlobalSource Partners](https://www.globalsourcepartners.com/) directly within Gemini CLI.

This extension connects Gemini CLI to the GlobalSource Partners remote Model Context Protocol (MCP) server, enabling Gemini to search research covering economics, politics, public policy and sovereign risk.

## Features

* Search GlobalSource Partners research by topic, country, company or individual.
* Find relevant reports and analysis.
* Filter research by entity and publication date.
* Access public research without signing in.
* Authenticate as a GlobalSource Partners client for expanded access.

## Installation

Install the extension from GitHub:

```bash
gemini extensions install https://github.com/global-source-direct/global-source-partners-gemini-extension
```

Restart Gemini CLI after installation.

To confirm that the extension is installed:

```bash
gemini extensions list
```

Within an active Gemini CLI session, you can inspect the connected MCP server and its available tools using:

```text
/mcp
```

## Usage

Ask Gemini questions such as:

```text
Summarise the latest GlobalSource Partners research on Brazil.
```

```text
What does GlobalSource Partners research say about Argentina's economic outlook?
```

```text
Find recent research concerning sovereign risk in emerging markets.
```

```text
What are GlobalSource Partners' analysts saying about monetary policy in Mexico?
```

Gemini will invoke the GlobalSource Partners MCP tools when they are relevant to your request.

## Client authentication

The MCP server provides public access without requiring authentication.

GlobalSource Partners clients can authenticate to receive expanded access to research included in their subscription. In Gemini CLI, use:

```text
/mcp auth global-source-partners
```

Follow the browser-based authorization process and sign in with your GlobalSource Partners account.

Gemini CLI securely stores the resulting OAuth tokens and refreshes them when necessary.

## Updating

To update the extension:

```bash
gemini extensions update global-source-partners
```

To enable automatic updates when installing it:

```bash
gemini extensions install https://github.com/global-source-direct/global-source-partners-gemini-extension --auto-update
```

## Uninstalling

```bash
gemini extensions uninstall global-source-partners
```

## MCP server

The extension connects to the GlobalSource Partners Streamable HTTP MCP endpoint:

```text
https://www.globalsourcepartners.com/mcp
```

The server is also published in the official Model Context Protocol Registry as:

```text
com.globalsourcepartners/emerging-markets-research
```

## About GlobalSource Partners

[GlobalSource Partners](https://www.globalsourcepartners.com/) provides independent, locally based economic and political research covering emerging and frontier markets.

Its network of in-country experts provides investors and decision-makers with analysis of economics, politics, policy and sovereign risk.

## Privacy and terms

Use of the GlobalSource Partners service is subject to the policies and terms published on the [GlobalSource Partners website](https://www.globalsourcepartners.com/).

When Gemini uses this extension, relevant parts of your request may be sent to the GlobalSource Partners MCP server to perform searches and retrieve research.
