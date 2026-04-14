Automatically raise PRs from GitHub issues
==========================================

This repo contains github actions to do agent-based development using Claude code, that can be used by other repositories.
When you label an issue "ready for agent", a github action is triggered that uses the issue description in a prompt to implement the issue.
The github action uses the claude code github action in non-interactive mode to implement and test the entire feature.
After the development loop is complete, claude raises a pull request.
When changes are requested on the pull request, claude implements all review comments and updates the PR.

Resources:
* https://code.claude.com/docs/en/github-actions
