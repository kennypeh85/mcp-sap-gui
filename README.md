# MCP SAP GUI Server

An [MCP (Model Context Protocol)](https://modelcontextprotocol.io/) server that enables AI assistants to interact with SAP GUI for Windows through the SAP GUI Scripting API.

It is client-agnostic: if your MCP client can launch a local `stdio` server, it can use this project. Examples in this README use Claude because the setup is easy to demonstrate, but the same server can be used from Codex, GitHub Copilot, Gemini CLI, and similar MCP-capable tools.

Current release: `0.2.0` for local Windows use over MCP `stdio`.

[![CI](https://github.com/kennypeh85/mcp-sap-gui/actions/workflows/ci.yml/badge.svg)](https://github.com/kennypeh85/mcp-sap-gui/actions/workflows/ci.yml)
[![Docs](https://github.com/kennypeh85/mcp-sap-gui/actions/workflows/docs.yml/badge.svg)](https://github.com/kennypeh85/mcp-sap-gui/actions/workflows/docs.yml)
[![Release](https://img.shields.io/github/v/release/kennypeh85/mcp-sap-gui)](https://github.com/kennypeh85/mcp-sap-gui/releases)

## What This Does

This server allows AI assistants to:
- Connect to SAP systems (like double-clicking in SAP Logon Pad) or attach to already-open sessions
- Execute any transaction code (MM03, VA01, SE38, /SCWM/MON, SE80, etc.) — no default restrictions
- Read and write screen fields, checkboxes, radio buttons, comboboxes, and tabs
- Select menu items from the menu bar (Table View, Edit, Selection, etc.)
- Navigate through SAP screens using keyboard keys and buttons
- Extract data from ALV grids (GuiGridView) and classic table controls (GuiTableControl)
- Interact with ALV toolbar buttons and context menus
- Read and interact with tree controls (TableTree, ColumnTree, SimpleTree)
- Take screenshots of SAP windows
- Discover screen elements for automation
- Automatically recover from stale COM references after SAP GUI restarts

## Example Conversation

```
User: "What's the description for material MAT-001 in system D01?"