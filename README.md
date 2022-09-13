# wild-apricot-slack-sync

You have a Wild Apricot community with members. You want to sync the list of members with users in a Slack workspace.

This tool will download all members from a Wild Apricot community, compare the email addresses with the users in a Slack workspace, and spit out a report of which Wild Apricot members need to be invited to Slack. It will also download all users from that Slack workspace, see if all of them are paying members in your Wild Apricot community, and spit out a report of which Slack users need to be deactivated.

Because Slack limits fully automated invites to Enterprise plans only, this tool will not automatically invite members. Instead, it'll give you a list of email addresses you can paste into Slack's "Invite users" dialog.

## Usage

```
--wild-apricot-api-key="abc..."     Wild Apricot API Key
--slack-token="xo..."               Slack Bot Token
--verbose                           Enable verbose mode
```

```
npx wild-apricot-slack-sync --wild-apricot-api-key="etwl..." --slack-token="xoxb-..."
```

Then, find a file called `wild-apricot-slack-sync-report.txt` in your working directory. It'll contain a list of people to invite and to deactivate.

## Getting a Wild Apricot API Key

Please see https://gethelp.wildapricot.com/en/articles/180-authorizing-external-applications

## Getting a Slack Token

1. Visit [https://api.slack.com/apps/](https://api.slack.com/apps/) and sign in to your workspace.
2. Click `Create New App`, enter a name (e.g., `wild-apricot-slack-sync`), and select your workspace.
3. When prompted for an App Manifest, just paste in the contents of the `slack-manifest.yaml` file in the root of this repo.
4. Select `Install to Workspace` at the top of that page (or `Reinstall to Workspace` if you have done this previously) and accept at the prompt.
5. Copy the `OAuth Access Token` (which will generally start with `xoxb`)

## License

MIT, please see License.md for details.