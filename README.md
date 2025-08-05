# Dune Analytics MCP Server

A Model Context Protocol (MCP) server that provides AI agents with access to Dune Analytics data.

## Setup

### Prerequisites
- Python 3.13+
- Dune Analytics API key

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

**5. Run the server:**
```bash
python main.py
```

## Tools

- `get_latest_result(query_id)` - Get latest results for a Dune query
- `run_query(query_id)` - Execute a query and return results