# UniSpec Repository

The central marketplace for UniSpec modes, connectors, and workflows.

## What is this?

The UniSpec Repository is a collection of community-contributed packages that extend UniSpec:

- **Modes** - Custom workflows (Sprint, Kanban, Docs, RFC, etc.)
- **Connectors** - Commands that become MCP tools (test runners, linters, builders)
- **Workflows** - Pre-built workflow definitions for different languages/frameworks


## Contributing

Want to share your mode or connector with the world? Here's how:

### 1. Create Your Package

Your package should have this structure:

```
my-awesome-mode/
├── mode.toml          # Required: Mode metadata
├── skill.md          # Required: Agent persona
├── workflows/        # Optional: Workflow definitions
├── areas/           # Optional: Area templates
└── connectors/     # Optional: Custom connectors
```

### mode.toml Required Fields

```toml
[package]
name = "my-awesome-mode"
description = "What this mode does"
repo_url = "https://github.com/yourusername/my-awesome-mode"
license = "MIT"  # Required!
author = "Your Name"
version = "1.0.0"

[mode]
name = "my-awesome-mode"
display_name = "My Awesome Mode"
```

### 2. Submit to the Repository

1. Fork the [unispec-repo](https://github.com/uwzis/unispec-repo) repo
2. Add your package to `unispec-repo.toml`
3. Submit a PR

### Package Format

```toml
[package.my-package]
name = "My Package Name"
description = "What it does in one line"
repo_url = "https://github.com/username/repo"
license = "MIT"  # Required!
category = "mode"  # "mode", "connector", or "workflow"
tags = ["tag1", "tag2"]  # Optional tags
```

### License Requirements

- **Required**: Every package MUST have a `license` field
- **Recommended**: MIT, Apache-2.0, or BSD-3-Clause
- **Why?** UniSpec will check and warn users before installing packages without a license

## Official Repository

The default UniSpec repository is hosted at:
- https://github.com/uwzis/unispec-repo

This repo is fetched when you run `unispec repo list` or `unispec repo install`.

## Adding Custom Repositories

You can add your own repository:

```bash
unispec repo add-custom https://github.com/your-org/your-repo.toml
```

## Package Categories

### Modes
Complete workflows with areas, workflows, and agent configurations.
- Examples: Simple, Sprint, Kanban, Docs, RFC

### Connectors
Commands that become MCP tools.
- Examples: test-runner, linter, builder, deployer

### Workflows
Step-by-step workflow definitions.
- Examples: Rust workflows, JS workflows, API workflows

## Tips

1. **Start simple** - Don't over-engineer your first mode
2. **Document well** - Your skill.md explains how the agent should behave
3. **Test locally** - Run `unispec init` with your mode before sharing
4. **Use standard structure** - Follow the mode.toml format above

---

Made with 🦫 by the UniSpec community
