# TransLink MCP Server Tests

This directory contains the test suite for the TransLink MCP Server.

## Running Tests

### Using uv

To run the tests with `uv`, use the following commands:

```bash
# Install development dependencies
uv pip install -e ".[dev]"

# Run all tests
uv run pytest mcp_server_translink/test

# Run tests with verbose output
uv run pytest mcp_server_translink/test -v

# Run a specific test file
uv run pytest mcp_server_translink/test/test_server.py

# Run a specific test
uv run pytest mcp_server_translink/test/test_server.py::TestTranslinkTools::test_get_trip_updates_success
```

## Test Structure

The test suite is organized as follows:

-   `test_init.py` - Tests for the initialization and configuration of the MCP server
-   `test_server.py` - Tests for the server implementation and API interaction functions
-   `test_enum.py` - Tests for the TranslinkTool enumeration
-   `conftest.py` - Shared pytest fixtures

## Test Coverage

The tests cover the following aspects of the TransLink MCP Server:

1. Server initialization and configuration

    - Proper handling of the API key configuration
    - Error handling for missing API key

2. API Functions

    - Proper handling of requests to the TransLink API endpoints
    - Success cases with valid responses
    - Error handling for API failures

3. MCP Server Implementation

    - Tool registration and listing
    - Tool call routing to the appropriate functions
    - Error handling for unknown tools

4. TranslinkTool Enumeration
    - Verification of enum values and members
