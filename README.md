# Migration to API version
Now the new version of the checkin script is migrated from selemium to pydoll and get the traffic with api.

# Use uv as package manager
I have changed the package manager to uv, so please install the [uv](https://docs.astral.sh/uv/getting-started/installation/) first:

```bash
# install in linux or macos
curl -LsSf https://astral.sh/uv/install.sh | sh

# install in windows
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

# Make sure your IP is clean
Now the dirty ip will trigger the cloudflare firewall, so please use the clean ip to check in! (That means automation for checking in with github action is infeasible.)

# Getting start
First, install the environment with uv under the root of the project:
```bash
uv sync
```
Then, copy the .env.example to .env, and update the arguments to your account.

Use `uv run main.py` to start the script.

Add the start command to schedule such as crontab if you like.

```crontab
0 0 0 * * * /home/user(change to your user name)/.local/bin/uv run /somewhere_the_project_in/main.py 
```

Enjoy it!
