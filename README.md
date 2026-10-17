# SK Caption Cleaner

## Old channel history cleanup

Set these environment variables in your host's secret manager (do not commit secret values):

- Required: `API_ID`, `API_HASH`, `BOT_TOKEN`, `DATABASE_URI`
- Required for old-post history: `HISTORY_SESSION` — a Pyrogram session for a Telegram user account that belongs to the source channel
- Required to use cleaner commands: `ADMINS` — the Telegram user ID(s), comma- or space-separated
- Optional: `DATABASE_NAME` (default `Cluster0`), `SESSION`, and `PORT`

Add the bot to the source channel as an administrator with permission to edit messages. The user account in `HISTORY_SESSION` must be a member of that channel so it can read old history.

Run `/cleaner`, add the exact text snippets to remove, then choose **Clean Post** and forward a post from the channel. The cleaner edits matching message text/captions in place; it does not download or re-upload media. It currently scans up to 10,000 recent posts per run.

Never put `HISTORY_SESSION` or other credentials in this repository. Configure them only through the hosting provider's secret manager.
