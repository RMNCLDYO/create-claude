# create-claude

⚡ **Zero-config Claude Code setup. One command, infinite productivity.**

Stop wasting time configuring Claude Code. Get production-ready agents, hooks, commands, and templates instantly.

[![npm version](https://img.shields.io/npm/v/create-claude.svg)](https://www.npmjs.com/package/create-claude)
[![npm downloads](https://img.shields.io/npm/dm/create-claude.svg)](https://www.npmjs.com/package/create-claude)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Requirements

- **Node.js** ≥ 20.0.0
- **Claude Code** (Anthropic's official CLI)
- **Operating Systems**: macOS, Linux, Windows
- **Architectures**: x64, ARM64

## Quick Start

```bash
npx create-claude
```

That's it. Your Claude Code is now supercharged.

## Install and Use

```bash
# Option 1: Use npx (recommended)
npx create-claude

# Option 2: Use npm init
npm init claude

# Option 3: Direct commands
create-claude
create-claude init

# Option 4: Short alias (after global install)
npm install -g create-claude
cld init
```

## Options

```bash
# Help
create-claude --help
cld --help

# Version
create-claude --version
cld --version

# Preview changes without applying
create-claude --dry-run
cld --dry-run
```

## What You Get

```
.claude/
├── agents/          # AI-powered code assistants
├── hooks/           # Auto-formatting & safety checks  
├── commands/        # Custom slash commands
├── scripts/         # Dynamic statusline
└── settings.json    # Full permissions config
```

**■ Production Agents**
- `pre-commit` - Pre-commit validation & testing
- `refactor` - Code cleanup & optimization

**▲ Smart Hooks** 
- `format` - Fast formatting on save
- `safety` - Command validation

**◇ Commands**
- `/validate` - Full lint/typecheck/format
- `/test` - Test runner with zero tolerance

**▪ Project Templates**
- Auto-detects your stack
- Customized for your runtime
- Git integration

## Supported Stacks

**Languages:** Rust, Go, Python, Java, C/C++, Node.js, Bun, TypeScript  
**Frameworks:** Next.js, Nuxt.js, NestJS, React, Vue, Angular, Svelte, Vite, Astro, Express, Fastify + more  
**Package Managers:** npm, yarn, pnpm, bun, pip, poetry, uv  
**Features:** Auto-formatting, pre-commit hooks, safety guards, progress indicators, smart backups

## API

```typescript
import { init, ErrorCode } from 'create-claude';

// Basic usage
const result = await init('/path/to/project');
console.log(result.message);

// With options
const dryRunResult = await init('/path/to/project', { dryRun: true });
if (dryRunResult.success) {
  console.log(`Would create ${dryRunResult.filesCreated} files`);
}

// Error handling
if (!result.success) {
  switch (result.errorCode) {
    case ErrorCode.NO_WRITE_PERMISSION:
      console.error('Permission denied');
      break;
    case ErrorCode.SKELETON_FILES_MISSING:
      console.error('Package corrupted, reinstall');
      break;
  }
}
```

## Safety & Backup System

**Bulletproof file safety** - Your existing configuration is never lost:

- **🔒 Atomic operations** - All-or-nothing file copying prevents partial states
- **📋 SHA256 verification** - Every backup verified with cryptographic integrity checks  
- **⏰ Timestamped backups** - Existing files moved to `.create-claude-backup-[timestamp]/`
- **🔄 Auto-recovery** - Failed operations automatically restore originals
- **🚫 Zero data loss** - 5-step verification process ensures 100% safety

```bash
# Safe overwrite example:
create-claude  # Backs up existing CLAUDE.md → .create-claude-backup-2025-08-23T12-34-56-789Z/
```

## Why create-claude?

- **▲ Instant setup** - No config files, no tutorials
- **◉ Secure defaults** - Built-in safety checks with pre/post hooks
- **↻ Smart backups** - Bulletproof file safety with SHA256 verification
- **◎ Opinionated** - Battle-tested best practices, zero decisions
- **🚀 Zero dependencies** - No supply chain vulnerabilities
- **⚡ Lightning fast** - < 2 seconds to full setup

## Testing Coverage

Extensively tested with comprehensive integration tests:

- **✅ Core Functionality**: Full initialization, dry-run mode, error scenarios
- **✅ Backup System**: Existing file preservation with SHA256 verification
- **✅ Framework Detection**: 15+ frameworks (Next.js, React, Vue, Angular, Svelte, etc.)
- **✅ Runtime Support**: Node.js, Python, Rust, Go, Java, C/C++, Bun, TypeScript  
- **✅ Package Managers**: npm, yarn, pnpm, bun, pip, poetry, uv
- **✅ Git Integration**: Clean repos, staged changes, untracked files, branch detection
- **✅ Safety Scenarios**: Existing files, permission errors, interruption recovery
- **✅ Statusline System**: Real-time project context with color coding
- **✅ Hook System**: Auto-formatting, safety validation, pre-commit checks
- **✅ Edge Cases**: Invalid directories, file permissions, atomic operations

## Troubleshooting

**Permission Errors**:
```bash
# Fix: Ensure write permissions in target directory
chmod 755 /path/to/project && create-claude
```

**Node Version Issues**:
```bash
# Fix: Upgrade to Node.js ≥ 20
nvm install 20 && nvm use 20
```

**Existing Config Conflicts**:
```bash
# Your original files are safely backed up in:
# .create-claude-backup-[timestamp]/
# You can restore them manually if needed
```

**Module Import Errors**:
```bash
# Fix: Ensure you have latest Claude Code installed
# The hooks require Node.js CommonJS compatibility
```

## Advanced Usage

**Restore from Backup**:
```bash
# Find your backup
ls -la .create-claude-backup-*

# Restore manually
cp .create-claude-backup-*/CLAUDE.md ./CLAUDE.md
cp -r .create-claude-backup-*/.claude ./.claude
```

**Custom Configuration**:
```bash
# Initialize, then customize
create-claude
# Edit .claude/settings.local.json
# Add custom agents to .claude/agents/
# Add custom hooks to .claude/hooks/
```

**CI/CD Integration**:
```bash
# In your CI pipeline
npx create-claude --dry-run  # Verify what would be installed
npx create-claude            # Install if checks pass
```

## Contributing

PRs welcome! Please read our [contributing guidelines](https://github.com/RMNCLDYO/create-claude/blob/main/CONTRIBUTING.md) first.

## Support

- 🐛 [Report bugs](https://github.com/RMNCLDYO/create-claude/issues)
- 💡 [Request features](https://github.com/RMNCLDYO/create-claude/issues/new)
- ⭐ [Star on GitHub](https://github.com/RMNCLDYO/create-claude)

---

Built by developers who got tired of manual Claude Code setup and unreliable tools.

## License

MIT