# AGENTS.md

This file provides guidance for AI coding agents working in this repository.

## Security and Safety Guidelines

AI coding agents must follow these guardrails at all times when working in this repository.

### Protect Sensitive Data

- Do not read, log, print, or commit secrets, credentials, API keys, tokens, or passwords. This includes values from environment variables, `.env` files, or any runtime configuration.
- Do not include personally identifiable information (PII) or customer financial data (e.g., payment details, loan records, account numbers) in code comments, log statements, test fixtures, or commit messages.
- Do not hardcode secrets or credentials into source files. Reference them only by environment variable name (e.g., `process.env.API_KEY`).
- Do not exfiltrate or transmit data to external services not already used by this application.

### Prevent Unauthorized Deployments

- Do not push to `main`, `master`, or any production-tracking branch directly. All changes must go through a pull request and receive explicit human approval.
- Do not trigger Heroku deployments (e.g., `git push heroku`) or any release pipeline without explicit instruction from a human.
- Do not modify `app.json`, `Procfile`, or deployment configuration in ways that could automatically trigger a production rollout.
- Do not create, modify, or delete Heroku resources (dynos, add-ons, environment config vars) without explicit approval.

### Avoid Destructive Operations

- Do not force-push to any branch (`git push --force` or `git push --force-with-lease`).
- Do not delete branches, tags, or any remote refs.
- Do not drop, truncate, or irreversibly migrate data. Any schema or data migration must be reviewed and approved by a human before execution.
- Do not run commands that are irreversible in production environments (e.g., removing payment records, clearing queues, resetting loan state).
- Do not modify or delete infrastructure configuration without explicit instruction and approval.
