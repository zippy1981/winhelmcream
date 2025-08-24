# General Instructions & Critical Review

**NOTE**: This was originally created wby copilot when I was trying to get it to provide an instructions file. 

## Flaws in the Prompter's Approach

- **Ambiguity:** The prompt lacks explicit requirements for error handling, reporting, and edge cases in Helm chart linting.
- **Scalability:** Hardcoding chart paths in workflows does not scale for additional charts; consider dynamic discovery.
- **Reusability:** The solution relies on a single shared workflow, but does not address versioning or workflow extensibility.
- **Security:** No mention of secret management, RBAC, or image scanning in the CI pipeline.
- **Observability:** No integration with logging or monitoring tools for workflow runs.
- **Testing:** No automated chart testing beyond linting (e.g., `helm unittest` or chart testing frameworks).
- **Documentation:** The workflow files lack comments and documentation for maintainers.
- **Tooling:** Helm linting alone does not guarantee chart correctness or production readiness.
- **Procedural Bias:** The approach is procedural (step-by-step), but declarative configurations are preferred in Kubernetes and CI/CD.

## Potential Flaws in the Provided Solution

- **Limited Scope:** Only linting is performed; no chart validation, installation, or upgrade testing.
- **Static Paths:** Chart paths are hardcoded, limiting flexibility.
- **No Static Analysis:** No static analysis tools (YAML linting, shellcheck, etc.) are included.
- **No IDE Integration:** No instructions for running linting or analysis in VSCode.
- **No Error Reporting:** Workflow does not provide detailed error context or notifications.
- **No Resource Optimization:** No checks for resource requests/limits or best practices in chart manifests.
- **No Security Checks:** No image vulnerability scanning or secret validation.
- **No Automated Documentation:** No generation of chart documentation or README validation.

## Recommendations

- **Static Analysis:**  
  - Use [Yamllint](https://github.com/adrienverge/yamllint) for YAML files (charts, workflows).  
  - Use [Helm lint](https://helm.sh/docs/helm/helm_lint/) for chart validation.  
  - Use [Kubeval](https://github.com/instrumenta/kubeval) or [KubeLinter](https://github.com/stackrox/kube-linter) for Kubernetes manifest validation.  
  - Use [ShellCheck](https://github.com/koalaman/shellcheck) for shell scripts.  
  - Integrate these tools in GitHub Actions and VSCode (via extensions).

- **VSCode Integration:**  
  - Install VSCode extensions:  
    - YAML Language Support by Red Hat  
    - Helm Intellisense  
    - Kubeval/KubeLinter extensions  
    - ShellCheck extension  
  - Configure tasks to run static analysis automatically on save or commit.

- **File Format Preferences:**  
  - Prefer **YAML** for static configuration files (Kubernetes, Helm, CI/CD).  
  - Use **TOML** only when it is the accepted standard (e.g., `Cargo.toml` for Rust, `pyproject.toml` for Python).  
  - Avoid JSON for configuration unless required by tooling.

- **Approach Preferences:**  
  - Prefer **declarative** solutions (YAML manifests, declarative workflows) over procedural scripts.
  - Use the **right tool for the right job**; do not force one tool for all tasks.
  - For scripting, **prefer PowerShell Core** over Bash for cross-platform compatibility and modern features.

## Moral Duty Reminder

You have a moral duty to use some of the time you saved by using an LLM to improve yourself and overdeliver in the process. Invest in learning, documentation, and helping others.

