# System Monitoring Reminder

## Why Use This Tool? 🤖⚡

Let's be honest—system monitoring isn't the most exciting task, and it's easy to forget. and suddenly... BOOM! An issue goes unnoticed, an alert is missed, and chaos ensues. The server gods weep, our Slack DMs explode, and we scramble to fix what could have been prevented. 😱🔥 

This GitHub Actions workflow ensures that no one forgets their monitoring duty by automatically sending reminders to the designated guardian. It helps the team stay proactive, reducing issues before they escalate. 

So, no more awkward "Oops, I thought you were monitoring!" moments. No more last-minute scrambling—just smooth, reliable monitoring! 🚀💪

## How It Works ⚙️

This GitHub Actions workflow runs on a set schedule and sends reminders to the designated system guardian on Slack. It fetches the rotation list from the project's GitHub Wiki, identifies the current guardian, and notifies them at the right time.

### Key Features:
- **Automated Reminders**: Sends Slack notifications on scheduled days to ensure system monitoring is never forgotten.
- **Guardian Rotation Handling**: Extracts the current guardian's details from the `Rotation.md` file in the GitHub Wiki.
- **Slack Integration**: Sends reminders to the designated Slack channel with the guardian’s mention.
- **End-of-Week Acknowledgment**: Recognizes and appreciates the guardian’s efforts every Friday.

## Setup Guide 🛠️

### 1. Add Repository Secrets
To enable Slack notifications, you need to configure the following secrets in your GitHub repository:

| Secret Name           | Description |
|----------------------|-------------|
| `SLACK_WEBHOOK_URL`  | Incoming webhook URL for Slack notifications. |
| `SLACK_CHANNEL_ID`   | ID of the Slack channel where reminders will be sent. |

Go to **GitHub Repo → Settings → Secrets and Variables → Actions → New Repository Secret** and add these values.

### 2. Configure the Rotation File
Ensure your team’s rotation is listed in the `Rotation.md` file inside the GitHub Wiki. The file should follow this format:

```
Title: Rotation

<!-- Note: The title becomes the file name, e.g., Rotation => Rotation.md -->

Body:
## System Monitoring Rotation  
Who is on duty next week? Add `🔥` to your name!

### Guardians (name: slack_member_id)
- Abir: U0634QPAAAA   
- XAbir: U0634QPBBBB 🔥 *(Current Guardian – Stay Vigilant! ⚡)*
- YAbir: U0634QPCCCC
- ZAbir: U0634QPDDDD  
- NO_Abir: U0634QPEEEE
```

The script will extract the name marked with `🔥` and send reminders accordingly.

### 3. GitHub Workflow File
Save the `rotation-reminder.yml` file in `.github/workflows/`. This file:
- Fetches the latest rotation list.
- Identifies the current guardian.
- Sends Slack reminders on specific days.

### 4. Scheduled Reminders
The workflow runs at these times:
- **Monday at 8:00 AM UTC** – Assigns the week's monitoring duty.
- **Friday at 8:00 AM UTC** – Thanks the guardian for their efforts.

## How to Trigger Manually
If needed, you can manually trigger the reminder:
1. Go to **GitHub Actions** in your repository.
2. Select **System Monitoring Reminder**.
3. Click **Run workflow**.

## Conclusion
With this tool, you'll never forget your system monitoring duties again. It keeps your team accountable, ensures smooth operations, and even adds some fun with Slack reminders. No more surprises—stay ahead of issues before they become problems! 🚀

