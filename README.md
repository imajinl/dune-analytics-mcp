# Dune Analytics MCP Server

A Model Context Protocol (MCP) server that gives Claude access to Dune Analytics data for querying blockchain analytics.

## Setup

### Prerequisites
- Python 3.13+
- Dune Analytics API key
- Claude Desktop app

### Installation

**1. Clone and navigate to the project:**
```bash
git clone https://github.com/imajinl/dune-analytics-mcp.git
cd dune-analytics-mcp
```

**2. Create virtual environment:**

**Mac / Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

**Windows:**
```cmd
python -m venv venv
venv\Scripts\activate
```

**3. Install dependencies:**
```bash
pip install -e .
```

**4. Set up API key:**
Create a `.env` file in the project root:
```
DUNE_API_KEY=your_api_key_here
```

**5. Configure Claude Desktop:**

Add this to your Claude Desktop MCP configuration file:

**Mac:** `~/Library/Application Support/Claude/claude_desktop_config.json`
**Windows:** `%APPDATA%/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "dune-analytics": {
      "command": "python",
      "args": ["/path/to/your/dune-analytics-mcp/main.py"],
      "env": {
        "DUNE_API_KEY": "your_api_key_here"
      }
    }
  }
}
```

Replace `/path/to/your/dune-analytics-mcp/main.py` with the actual path to your main.py file.

**6. Restart Claude Desktop** to load the MCP server.

## Usage

Once configured, Claude will have access to these Dune Analytics tools. You can ask Claude to:

- "Get the latest results from Dune query 12345"
- "Run query 67890 and show me the data"
- "Fetch data from my Dune dashboard query"

## Available Tools

- `get_latest_result(query_id)` - Get latest cached results for a Dune query
- `run_query(query_id)` - Execute a query and return fresh results

Both tools return data in CSV format that Claude can analyze and visualize.