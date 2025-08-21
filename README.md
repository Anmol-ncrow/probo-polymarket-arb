# arb-bot

![Arbitrage Bot Architecture](image.png)

An arbitrage bot that finds price differences between Probo and Polymarket platforms and executes trades automatically.

## Setup

### Prerequisites
- [Bun](https://bun.sh) runtime (recommended) or Node.js 18+
- [Visual Studio Code](https://code.visualstudio.com/) (recommended)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Anmol-ncrow/probo-polymarket-arb.git
cd probo-polymarket-arb
```

2. Install dependencies:
```bash
bun install
# or with npm
npm install
```

3. **Note**: The `clob-client` dependency needs to be set up separately. This appears to be a custom Polymarket CLOB (Central Limit Order Book) client that needs to be added to the project.

### Opening in VSCode

#### Option 1: Using the workspace file (Recommended)
1. Open VSCode
2. Use `File > Open Workspace from File...`
3. Select `probo-polymarket-arb.code-workspace`

#### Option 2: Direct folder opening
1. Open VSCode
2. Use `File > Open Folder...`
3. Select the repository folder

#### Option 3: Command line
```bash
# If you have VSCode CLI installed
code probo-polymarket-arb.code-workspace
# or
code .
```

VSCode will automatically:
- Suggest installing recommended extensions (TypeScript, Bun, Prettier, etc.)
- Apply project-specific settings
- Enable TypeScript support with proper configuration
- Provide debugging configurations for both Bun and Node.js
- Set up build and test tasks

### Environment Setup

Create a `.env` file in the root directory with your API credentials:
```bash
POLYMARKET_API_KEY=your_api_key_here
POLYMARKET_API_SECRET=your_api_secret_here
POLYMARKET_PASS_PHRASE=your_pass_phrase_here
PRIVATE_KEY=your_ethereum_private_key_here
RPC_URL=your_rpc_url_here
CLOB_API_URL=https://clob.polymarket.com
```

### Running the Bot

```bash
# Run once
bun run index.ts

# Run in development mode (with file watching)
bun run dev

# Run tests
bun run test

# Type checking
bun run type-check
```

### VSCode Features Configured

#### Extensions
- **TypeScript**: Enhanced TypeScript support
- **Bun**: Bun runtime support and debugging
- **Prettier**: Code formatting
- **ESLint**: Code linting (when configured)

#### Debugging
- **Run with Bun**: Primary debug configuration using Bun runtime
- **Run with Node**: Fallback debug configuration using Node.js
- **Run Tests**: Debug test files

#### Tasks (Access via `Ctrl+Shift+P` > "Tasks: Run Task")
- **build**: Build the project
- **run**: Run the application
- **test**: Run tests
- **install**: Install dependencies

#### Settings
- Auto-formatting on save
- Import organization
- TypeScript preferences
- Optimized search exclusions

### Project Structure
```
├── .vscode/                    # VSCode configuration
│   ├── settings.json          # Editor settings
│   ├── launch.json           # Debug configurations
│   ├── tasks.json            # Build tasks
│   └── extensions.json       # Recommended extensions
├── clob-client/              # Polymarket CLOB client (needs setup)
├── index.ts                  # Main application entry
├── polymarket.ts             # Polymarket API integration
├── probo.ts                  # Probo API integration
├── types.ts                  # TypeScript type definitions
├── index.test.ts             # Test file
└── probo-polymarket-arb.code-workspace  # VSCode workspace file
```

This project was created using `bun init` in bun v1.2.2. [Bun](https://bun.sh) is a fast all-in-one JavaScript runtime.

