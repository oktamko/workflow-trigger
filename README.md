# Trigger

Starts a workflow in another repository on a schedule (Mon–Fri, every 20 minutes).

It exists because scheduled runs in a private repository were being dropped by GitHub, while
manually started ones worked. This public repository holds only the schedule; the code and
all configuration live elsewhere.

## Secrets

| Secret | What |
|---|---|
| `TARGET_REPO` | `owner/name` of the repository whose `bot.yml` should be started |
| `BOT_TRIGGER_TOKEN` | Fine-grained personal access token limited to that one repository, with **Actions: Read and write** |

No data is stored here. If the token is missing or wrong, the run fails and GitHub sends an e-mail.
