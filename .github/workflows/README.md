# GitHub Actions Workflows

This directory contains GitHub Actions workflows for the AndroidAPS project.

## Claude Code Integration

The repository includes two Claude Code workflows that are **disabled by default**:

- `claude.yml` - Responds to @claude mentions in issues and pull requests
- `claude-code-review.yml` - Automatically reviews pull requests

### Enabling Claude Code

To enable these workflows, a repository administrator needs to:

1. Set up the Claude Code OAuth token:
   - Go to repository Settings > Secrets and variables > Actions
   - Add a secret named `CLAUDE_CODE_OAUTH_TOKEN` with your Claude Code OAuth token

2. Enable the workflows:
   - Go to repository Settings > Secrets and variables > Actions > Variables tab
   - Add a repository variable named `CLAUDE_CODE_ENABLED` with value `true`

### Why are these workflows disabled by default?

These workflows are disabled to prevent CI failures when the Claude Code integration is not fully configured. Without proper OIDC token configuration, the workflows would fail with "401 Unauthorized - Invalid OIDC token" errors.

## Other Workflows

- `aaps-ci.yml` - Main CI pipeline for building AAPS
- `pr-ci.yml` - Pull request CI pipeline
- `keystore-export.yml` - Keystore encryption and backup
- `cherry-pick-ci.yml` - Cherry-pick commits and build pre-release features
