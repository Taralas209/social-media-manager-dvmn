# Social Media Manager

This project serves to schedule and manage social media posts using the Google Sheets API and the APIs of various social media platforms such as VK, OK, and Telegram.

## Dependency Installation:

```pip install -r requirements.txt```

## Preparation for Launch

To launch the bot, you need to:

1. Create a .env file in the root directory with the scripts.
2. Get the Telegram bot token, create a bot through BotFather in Telegram, get the token and specify it as the TELEGRAM_TOKEN environment variable. For example: `TELEGRAM_TOKEN=3253423236:SSDDSfghhft54gdf`
3. Get the chat and group identifiers where you need to publish, and specify them as environment variables:
  - `TG_CHAT_ID`. For example: `TG_CHAT_ID=@My_chat`
  - `VK_CHAT_ID`. For example: `VK_CHAT_ID=-226320423`
  - `VK_GROUP_ID`. For example: `VK_GROUP_ID=226320423`
  - `ALBUM_ID`. For example: `ALBUM_ID=296452847`
  - `VK_CHAT_ID`. For example: `TG_CHAT_ID=@My_chat`
  - `OK_GROUP_ID`. For example: `OK_GROUP_ID=70000002834827`
4. Get the VK API application token, and specify it as the VK_TOKEN environment variable. For example: `VK_TOKEN=vk1.a.UzvFkeu24SxHp_Wg9Sgjdytztj65hfjO5rDC6SpFwBs00bukEWr`
5. Get the OK API application token, and specify it as the OK_TOKEN environment variable. For example: `OK_TOKEN=tkn1YWGSDgjsdhjlUDasdgmk5sdGJndth0vE9O0eVJ8M0ZZR8LmgvwBO4zYmPtunD2daZ2Ie1`
6. Get the public and secret keys for OK, and specify them as environment variables:
  - `OK_PUBLIC_KEY`. For example: `OK_PUBLIC_KEY=ASDFJKDGJSDJTDSJRSDGTSDGSDG`
  - `OK_SECRET_KEY`. For example: `OK_SECRET_KEY=44p4j4kKFMSDFKsdm4sdg`
7. Get the Google Sheets ID, and specify it as the GOOGLE_EXCEL_ID environment variable. For example: `GOOGLE_EXCEL_ID=2-gdfgfSEg-GSDgWEKMd6`

## Launch

```python google_sheets_watcher.py```

## Result

Iterates over rows in Google Sheets.
Checks if the current date and time match the scheduled publication date and time in the table.
If a match is found:
- Retrieves the post text from the Google Docs document.
- Uploads any attached photo.
- Creates a post on VK, if VK social network is enabled and the post has not yet been published.
- Creates a post on Telegram, if the Telegram social network is enabled and the post has not yet been published.
- Records details of the publication and status in the Google Sheets document.
- Adds the message ID to the list of messages for deletion, if the scheduled deletion date is in the future.
The process will continue indefinitely until the script is stopped.

## Python Version

We used Python 3.8.3, but it should work on any newer version.

## Project Goals

The code is written for educational purposes as part of an online course for web developers at dvmn.org.

## Authors

(2023) Zaitsev Vladimir, Alexej Zikunow
