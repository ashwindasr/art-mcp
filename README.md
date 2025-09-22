# ART MCP Server

Model Context Protocol (MCP) server for querying BigQuery tables containing ART (Automated Release Tooling Team) build data.

## Features

- **query_art_builds**: Execute custom queries with filtering, field selection, and ordering
- **get_build_summary**: Get aggregated statistics and metrics about builds  
- **search_builds_by_package**: Find builds containing specific packages
- **get_failed_builds**: Analyze failed builds for debugging

## Setup

1. Install dependencies:
```bash
pip install -e .
```

2. Configure BigQuery access:
```bash
# Set up authentication
gcloud auth application-default login

# Copy and edit environment file
cp .env.example .env
# Edit .env with your BigQuery project/dataset/table details
```

3. Run the server:
```bash
python tools/bigquery_mcp_server.py
```

## Configuration

Set these environment variables:
- `BIGQUERY_PROJECT_ID`: Your GCP project ID
- `BIGQUERY_DATASET_ID`: BigQuery dataset name
- `BIGQUERY_TABLE_ID`: BigQuery table name



## Usage with Claude/Gemini

To make it work with Claude Code:
```
claude mcp add "bigquery-art" "python" "/Users/asdas/JetBrains/PycharmProjects/art-mcp/tools/bigquery_mcp_server.py"
```
