# Self-Healing CI with Dagger - Sample Application

This repository is a demo of self-healing CI with Dagger.

When CI fails on a pull request, an agent is triggered automatically. It spins up a containerized environment with the failing PR, all source code and dependencies, runs the test suite, inspects the errors, iterates on the code until the tests pass, and then opens a new PR branched off the original for human approval.

## Requirements

The following secrets must be configured in the GitHub repository:

- `OPENAI_API_KEY`
- `GH_API_TOKEN`
- `DAGGER_CLOUD_TOKEN` (optional)

## Usage

### Activate agent

- Open a PR in the repository with a deliberate bug
- When CI tests fail, the agent triggers automatically
- The agent comments on the original PR with its analysis and fix summary
- The agent opens a new PR with the repair for human review and approval
- Sample PR and fix: https://github.com/vikram-dagger/fastapi-sample-app/pull/134

### Run tests manually

```shell
docker compose up
docker exec -it fastapi_app bash
pytest # in the container shell
```
