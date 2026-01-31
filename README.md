# Self-Healing CI with Dagger - Sample Application

## Requirements

The following secrets must be configured in the GitHub repository:

- `OPENAI_API_KEY`
- `GH_API_TOKEN`
- `DAGGER_CLOUD_TOKEN` (optional)

## Usage

### Activate agent

- Open a PR in the repository with a deliberate bug
- When CI tests fail, the agent triggers and investigate
- The agent writes a comment on the original PR with analysis/solution, and opens a sub-PR with a code fix

### Run tests manually

```shell
docker compose up
docker exec -it fastapi_app bash
pytest # in the container shell
```
