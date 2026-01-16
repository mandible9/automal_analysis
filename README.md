# Malware Analysis Automation Toolkit

A comprehensive, automated malware analysis pipeline designed to extract critical indicators from static and dynamic reports. This toolkit provides heuristic insights, interactive analysis via Claude Desktop (MCP), and professional PDF report generation.

## 📁 Project Structure

- **`/toolkit`**: The main analysis engine, including the MCP server, report generators, and heuristic analysis scripts.
- **`/scripts`**: Legacy/Standalone static and dynamic analysis scripts.
- **`/videos`**: Video demonstrations of the toolkit in action.

## 🚀 Key Features

- **Dual-Analysis Support**: Analyzes both **Static Reports** (YARA, strings, PE/ELF headers) and **Dynamic Reports** (strace, netstat, process logs).
- **Intelligent Extraction**: Automatically identifies Shared Objects (.so), Red-flagged IP addresses, and behavioral patterns.
- **Claude Desktop Integration**: Built-in MCP (Model Context Protocol) server for interactive malware analysis within Claude.
- **Automatic PDF Generation**: Creates professional reports with executive summaries and technical deep-dives.

## 🛠️ Setup & Installation

### 1. Prerequisites
- **Python 3.10+**
- **Node.js 18+** (required for the MCP server)

### 2. Installation
```powershell
# Navigate to the toolkit directory
cd toolkit

# Install Python dependencies
pip install requests reportlab pdfkit

# Install Node dependencies for MCP server
cd mcp_server
npm install
```

## 📖 Usage Guide

### Interactive Analysis (Claude Desktop)
To use this toolkit inside Claude Desktop, update your `claude_desktop_config.json` with the following configuration (replace `C:/path/to/` with your actual project path):

```json
{
  "mcpServers": {
    "malware-analysis": {
      "command": "node",
      "args": [
        "C:/path/to/malanalysi_automatation/toolkit/mcp_server/server.js"
      ]
    }
  }
}
```

### Local Analysis Scripts
You can also run analysis scripts manually from the `toolkit` folder:

- **Static Analysis**: `python static_windows.py <path-to-binary>`
- **Report Synthesis**: `python analyze_malware.py <path-to-report.txt>`

## 📺 Project Walkthroughs
Check the `videos` folder for demonstrations:
- `Claude MCP Integration Result.mp4`: Shows how to use the toolkit with Claude Desktop.
- `malware anlysis using the python file.mp4`: Demonstrates standalone python analysis.

## 🛡️ Privacy
All analysis is performed **locally**. Indicators are extracted using regex-based heuristics, and no data is sent to external APIs unless explicitly configured.
