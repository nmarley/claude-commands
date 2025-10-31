# Start Command

Get ready to code! This command helps you quickly set up your development environment and get started with your project.

## Actions:
- Check project status
- Show current directory structure  
- Identify project characteristics
- Show git status if in a git repo
- Display any language-specific package scripts if available

Let me help you get started with this project:

## Project Overview
!pwd
!ls -la

## File Structure
!echo "=== Directory tree ===" && \
tree -L 2 2>/dev/null || find . -maxdepth 2 -type d | sort

## All Files
!echo "=== All files in project ===" && \
find . -maxdepth 2 -type f | sort

## Git Status
!git status 2>/dev/null || echo "Not a git repository"

## Context headers (keep short)
!echo "=== PROJECT ==="; head -n 30 docs/PROJECT.md 2>/dev/null || echo "missing docs/PROJECT.md"
!echo "=== AGENT ===";   head -n 30 docs/AGENT.md   2>/dev/null || echo "missing docs/AGENT.md"
!echo "=== TASKS ===";   sed -n '1,60p' docs/TASKS.md 2>/dev/null || echo "missing docs/TASKS.md"

<additional_instructions>
You have access to the `psql` CLI and can use the connection string in `.env` if applicable to the prompt.

You have access to the `gh` CLI for GitHub and the `glab` CLI for GitLab, if applicable to the user's prompt and depending on which git hosted is being used.

You may use READ-ONLY commands for any of these if the user requests something related to this.
</additional_instructions>

Ready. What's your focus for this session?
