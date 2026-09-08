# werkstatt-fixture-deploy

Test fixture for Werkstatt's GitHub Deployments probe. Not a real application.

The "app" is `public/index.html`, a single static page. Nothing here is confidential.

## What this repo proves

1. A GitHub Deployment can be created for an exact commit SHA and an environment.
2. A workflow triggered by the `deployment` event checks out that exact SHA, not the branch head, and reports `deployment_status` back as `in_progress` then `success` or `failure`.
3. A deployment to an environment with a required reviewer is blocked until a human approves it.

## Environments

- `staging` — no protection rules, runs immediately.
- `production` — required reviewer, so a deployment waits for a human.

## Why this repo is public

The org is on the GitHub free plan, where environment protection rules only apply to public repositories. The probe needs the reviewer rule to be real, so the fixture is public rather than the probe being weakened.
