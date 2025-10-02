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

# ## Recent Context (from docs/SESSIONS.md)
# !if [ -f docs/SESSIONS.md ]; then \
#   last_hdr_line=$(grep -n '^## [0-9]\{4\}-[0-9]\{2\}-[0-9]\{2\}$' docs/SESSIONS.md | tail -1 | cut -d: -f1); \
#   if [ -n "$last_hdr_line" ]; then \
#     echo "=== Last session (truncated) ==="; \
#     sed -n "${last_hdr_line},\$p" docs/SESSIONS.md | sed -n '1,60p'; \
#     echo "=== Last session → next ==="; \
#     sed -n "${last_hdr_line},\$p" docs/SESSIONS.md | awk 'f;/^next:/{print;f=1;next} f&&NF{print;next} f&&!NF{f=0}'; \
#   else \
#     echo "No session headings found in docs/SESSIONS.md"; \
#   fi; \
# else \
#   echo "No docs/SESSIONS.md yet"; \
# fi
# 
# ## Log open (prefill today's focus from last session's `next:` if present)
# !ts=$(date "+%Y-%m-%d %H:%M:%S"); \
#  day=$(date "+%Y-%m-%d"); \
#  { grep -q "^## $day$" docs/SESSIONS.md 2>/dev/null || printf "\n## %s\n" "$day" >> docs/SESSIONS.md; }; \
#  branch="$(git rev-parse --abbrev-ref HEAD 2>/dev/null || echo '-')"; \
#  if [ -f docs/SESSIONS.md ]; then \
#    last_hdr_line=$(grep -n '^## [0-9]\{4\}-[0-9]\{2\}-[0-9]\{2\}$' docs/SESSIONS.md | tail -1 | cut -d: -f1); \
#    if [ -n "$last_hdr_line" ]; then \
#      focus_lines=$(sed -n "${last_hdr_line},\$p" docs/SESSIONS.md | awk 'f;/^next:/{f=1;next} f&&NF{print "- "$0;next} f&&!NF{exit}'); \
#      if [ -n "$focus_lines" ]; then \
#        printf "start: %s  branch: %s\nfocus:\n%s\n\n" "$ts" "$branch" "$focus_lines" >> docs/SESSIONS.md; \
#      else \
#        printf "start: %s  branch: %s\nfocus:\n\n" "$ts" "$branch" >> docs/SESSIONS.md; \
#      fi; \
#    else \
#      printf "start: %s  branch: %s\nfocus:\n\n" "$ts" "$branch" >> docs/SESSIONS.md; \
#    fi; \
#  else \
#    printf "start: %s  branch: %s\nfocus:\n\n" "$ts" "$branch" >> docs/SESSIONS.md; \
#  fi


Ready. What's your focus for this session?
