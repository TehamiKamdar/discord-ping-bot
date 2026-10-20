# Discord Ping Bot

A simple Discord bot built with **Node.js** and **discord.js**. This bot provides a `/ping` slash command to check whether the bot is online and responding correctly.

## Features

- `/ping` — Checks whether the bot is working and replies with `Pong! Bot is working.`
- Uses Discord slash commands.
- Simple and lightweight setup.
- Environment variables for secure token configuration.
- Guild-specific command registration for quick development and testing.

## Tech Stack

- [Node.js](https://nodejs.org/)
- [discord.js](https://discord.js.org/)
- [Discord Developer Portal](https://discord.com/developers/applications)
- dotenv

## Prerequisites

Before installing the bot, make sure you have:

- Node.js installed.
- npm installed (included with Node.js).
- A Discord application and bot created in the Discord Developer Portal.
- A Discord server where the bot has been invited.
- Git installed (optional, for cloning the repository).

## Installation

### 1. Clone the Repository

```bash
git clone YOUR_REPOSITORY_URL
cd YOUR_REPOSITORY_FOLDER
```

Replace `YOUR_REPOSITORY_URL` with your GitHub repository URL and `YOUR_REPOSITORY_FOLDER` with the actual project folder name.

Alternatively, download the repository as a ZIP file and extract it.

### 2. Install Dependencies

Run the following command inside the project directory:

```bash
npm install
```

This installs the dependencies listed in `package.json`.

If dependencies have not been saved in `package.json`, install them manually:

```bash
npm install discord.js dotenv
```

### 3. Configure Environment Variables

Create a `.env` file in the root directory:

```env
DISCORD_TOKEN=your_bot_token
CLIENT_ID=your_application_id
GUILD_ID=your_server_id
```

Replace the placeholder values with your actual credentials:

- `DISCORD_TOKEN`: Your bot token from the Discord Developer Portal.
- `CLIENT_ID`: Your Discord application's Application ID.
- `GUILD_ID`: The ID of your Discord server.

**Important:** Never share your bot token or commit your `.env` file to GitHub.

### 4. Register Slash Commands

Run the following command to register the bot's slash commands in your Discord server:

```bash
node deploy-commands.js
```

You should see a success message confirming that the commands have been registered.

Run this command again whenever you add or change slash commands.

### 5. Start the Bot

Start the bot using:

```bash
node index.js
```

If everything is configured correctly, your terminal should display a message confirming that the bot is online.

### 6. Test the Bot

1. Open your Discord server.
2. Type `/ping` in a text channel.
3. Select the Ping command.
4. The bot should reply:

```text
Pong! Bot is working.
```

## Project Structure

```text
discord-ping-bot/
├── index.js
├── deploy-commands.js
├── package.json
├── package-lock.json
├── .env
└── .gitignore
```

- `index.js` — Connects the bot to Discord and handles interactions.
- `deploy-commands.js` — Registers slash commands for your Discord server.
- `package.json` — Contains project metadata and dependencies.
- `.env` — Stores environment variables and credentials.
- `.gitignore` — Prevents sensitive files and dependencies from being committed.

## Required Discord Permissions

When inviting the bot, ensure that it has the required permissions and the `bot` and `applications.commands` OAuth2 scopes.

For this Ping Bot, broad administrative permissions are not necessary.

## Troubleshooting

**Bot does not come online**
- Verify that `DISCORD_TOKEN` is correct.
- Make sure your internet connection is working.
- Check the terminal for errors.

**`/ping` does not appear**
- Run `node deploy-commands.js` again.
- Verify that `CLIENT_ID` and `GUILD_ID` are correct.
- Make sure the bot was invited with the `applications.commands` scope.

**Missing module errors**
- Run `npm install` from the project directory.
- Verify that Node.js is installed using `node -v`.

## Security

Never upload your bot token to GitHub. Keep `.env` out of version control and regenerate the token immediately if it is accidentally exposed.

## License

This project is available for learning and personal use. Add a license file if you want to specify formal permissions for reuse and distribution.
