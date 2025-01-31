# neo4j-aura-go-cli

draft notes:

Command to set credentials
```bash

./neo4j-cli aura credential add --name "AuraDev1" --client-id AURA_CLIENT_ID --client-secret YOUR_AURA_CLIENT_SECRET
```


Command to state which credential (by name) to use:
```bash
./cli-binary aura credential use "AuraDev1"
```

Command to remove credential by name:
```bash
./cli-binary aura credential remove "CORRECT Aura API Credentials"
```

## Codebase 
//TODO: add links to individual code
//TODO: clean up markdown for codebase directory-code for mo'better aesthetics 

link to codebase - https://github.com/neo4j/neo4j-cli/tree/main/aura-cli
### `aura-cli/common` directory
The common directory in the Aura CLI contains shared/core functionality used across different parts of the application

#### `aura-cli/common/clicfg` directory
The clicfg directory contains code for handling configuration files used by the CLI.

#### `aura-cli/common/clicfg/credentials` directory
The credentials directory contains code for handling credentials used by the CLI.

#### `clicfg/credentials/aura.go`
handles the core credential management for Neo4j Aura with the following key functionality:

- Stores and manages multiple Aura credentials (client ID/secret pairs)
- Handles default credential selection
- Manages OAuth access tokens and their expiration
- Provides CRUD operations for credentials:
  - Add(): Add new credentials
  - Remove(): Delete existing credentials
  - List(): Show all credentials
  - Get(): Retrieve specific credentials
  - SetDefault(): Set the default credential
- Token management:
  - UpdateAccessToken(): Updates access tokens with expiration
  - ClearAccessToken(): Removes access tokens
  - HasValidAccessToken(): Checks if token is still valid

#### `clicfg/credentials/credentials.go
This file handles the persistence layer for credentials with these features:

- Manages the credentials file storage (default: ~/neo4j/cli/credentials.json)
- Uses afero filesystem abstraction for better testability
- Handles:
  - File loading/saving
  - JSON serialization/deserialization
  - Automatic file creation if not exists
  - Safe file operations

The system is designed to:
- Store multiple sets of credentials securely
- Handle OAuth token lifecycle
- Provide a clean interface for credential management
- Persist credentials between CLI sessions
- Support default credential selection for convenience

#### `clierr` directory
The clierr directory contains code for handling errors in the CLI.

#### error.go

this file defines custom error types for the CLI application. It provides three distinct categories of errors:

1. NewUsageError(message string): Used for invalid command usage
- Used for user input/usage errors
- for example, invalid flags, missing required arguments

2. NewUpstreamError(message string):
- For temporary API/network issues
- rate limiting, temporary service unavailability
- Suggests that retrying might resolve the issue

3. NewFatalError(message string):
- Used for unrecoverable errors
- invalid credentials, missing required arguments
- Operation cannot be completed


#### `clicmd` directory
The clicmd directory contains code for handling commands in the CLI.



#### `neo4j-cli` directory

#### `neo4j-cli/cli/main.go`

#### `neo4j-cli/aura` directory

#### `neo4j-cli/aura/cmd` directory

#### `neo4j-cli/aura/cmd` directory

#### `neo4j-cli/aura/internal` directory

#### `neo4j-cli/aura/internal/api` directory

#### `neo4j-cli/aura/internal/flags` directory

#### `neo4j-cli/aura/internal/output` directory

#### `neo4j-cli/aura/internal/subcommands` directory

#### `neo4j-cli/aura/internal/api` directory






