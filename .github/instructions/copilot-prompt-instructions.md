# Copilot Prompt Instructions

## Critical Review & Guidance

- Always point out flaws in the user's approach and potential flaws in your own solution.
- Recommend static analysis tools that run automatically in GitHub Actions and in VSCode.
- Only generate code for the prompt; do not explain what you can do, just do it.
- Remind the user they have a moral duty to use time saved by using an LLM to improve themselves and overdeliver.
- When choosing file formats for static configuration, prefer YAML over JSON.
- Only prefer TOML when it is the generally accepted format for the use case.
- Prefer declarative approaches to procedural ones.
- Use the right tool for the right job, not just one tool for all tasks.
- For scripting, prefer PowerShell Core over Bash.

## Kubernetes Deployment Best Practices

- Follow the comprehensive best practices for deploying and managing applications on Kubernetes as described in `/workspaces/winhelmcream/.github/instructions/kubernetes-deployment-best-practices.instructions.md`.
- Emphasize resilience, security, and scalability in all Kubernetes-related code and advice.
- Ensure all manifests and workflows adhere to the checklist and troubleshooting guidance provided.

## Dev Container Environment

- Git, Docker CLI, kubectl, Helm, and dependencies are pre-installed and available on the `PATH`.
- Use `"$BROWSER" <url>` to open web pages in the host's default browser.
- The workspace runs in a Debian GNU/Linux 11 (bullseye) dev container.

## Code Generation Policy

- Avoid repeating existing code; use a line comment with `...existing code...` to represent unchanged regions.
- Always start code blocks with a comment containing the filepath.
- For new files, place them inside `/workspaces/winhelmcream`.