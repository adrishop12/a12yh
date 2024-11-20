# Telegram Video Downloader Bot

This is a Telegram bot designed to download videos from Terabox. Users can interact with the bot to generate tokens, download videos, and manage their sessions.

## Features

- Download videos from Terabox by sharing the link with the bot.
- Generate and refresh tokens for session management.
- Admin commands to manage users and video lists.

## Prerequisites

- Python 3.7 or higher (Python 3.11 Recommended)
- A Telegram account
- A bot token from [BotFather](https://telegram.me/botfather)
- Redis server for session management

## Installation

1. **Extract the provided ZIP file:**

   Unzip the provided archive to your desired directory.
2. **Install the required packages:**

   Open a terminal or command prompt in the extracted directory and run:

   ```bash
   pip install -r requirements.txt
   ```
3. **Set up your configuration:**

   Create a `config.py` file in the root directory with the following content:

   ```python
   API_ID = 'your_api_id' #get from my.telegram.org
   API_HASH = 'your_api_hash' #get from my.telegram.org
   BOT_TOKEN = 'your_bot_token' #Get from @botfather
   BOT_USERNAME = 'your_bot_username'
   FORCE_LINK = '@your_channel_username'
   ADMINS = [123456789, 987654321]  # List of admin user IDs
   ```

   Replace the placeholders with your actual API ID, API hash, bot token, bot username, and admin user IDs.
4. **Install Redis:**

   - **macOS:**

     You can install Redis using Homebrew. Open a terminal and run:

     ```bash
     brew install redis
     ```

     To start Redis, use:

     ```bash
     brew services start redis
     ```
   - **Windows:**

     Download the latest Redis MSI installer from the [Redis GitHub releases page](https://github.com/microsoftarchive/redis/releases).

     Run the installer and follow the instructions. Once installed, you can start Redis from the command prompt in a new terminal:

     ```bash
     redis-server
     ```

## Obtaining API ID and API Hash

1. **Log in to Telegram:**

   Go to [my.telegram.org](https://my.telegram.org) and log in with your phone number.
2. **Create a new application:**

   - Click on "API Development Tools".
   - Fill in the required fields to create a new application.
   - Once created, you will see your `API ID` and `API Hash`.

## Creating a Channel and Obtaining Private Channel Chat ID

1. **Create a new channel:**

   Open Telegram, go to the menu, and select "New Channel". Follow the prompts to create your channel.
2. **Add the bot to your channel:**

   Add your bot as an admin to the private channel.
3. **Get the chat ID:**

   - Forward a message from your channel to [@raw_data_bot](https://telegram.me/raw_data_bot).
   - The bot will reply with `chat_id` of the channel.

## Running the Bot

1. **Start the bot:**

   Run the following command in your terminal or command prompt:

   ```bash
   python main.py
   python bot.py
   ```

   Run both commands in different terminals.
2. **Interact with the bot:**

   - Use `/start` to begin interacting with the bot.
   - Use `/gen` to generate a new token.
   - Admins can use `/remove <user_id>` to remove a user and `/removeall` to clear all videos.

## Running on a VPS

To run the bot on a VPS in the background, you can use tools like `screen` or `tmux`. Here's how you can do it with `screen`:

1. **Install Screen:**

   If it's not already installed, you can install it using:

   ```bash
   sudo apt-get install screen
   ```
2. **Start a new screen session:**

   ```bash
   screen -S bot-session
   ```
3. **Run the bot:**

   Inside the screen session, run:

   ```bash
   python main.py
   python bot.py
   ```

   Run both commands in different screen windows. You can create a new window in screen by pressing `Ctrl+A` followed by `C`.
4. **Detach from the screen session:**

   Press `Ctrl+A` followed by `D` to detach from the session. The bot will continue running in the background.
5. **Reattach to the screen session:**

   To reattach to the session later, use:

   ```bash
   screen -r bot-session
   ```

## Credits

This bot was developed by Libman. For more information and updates, join the [LIBMANX Telegram channel](https://telegram.me/LIBMANX).

- **CREDIT:** [LIBMAN](https://telegram.me/PBARMYF)
