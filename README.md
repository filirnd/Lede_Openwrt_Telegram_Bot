# Lede_Openwrt_Telegram_Bot
Telegram bot for router with firmware Lede/Openwrt.

## Implemented functions (Commands via Telegram message)
  - /reboot : Reboot router;
  - /connected_clients : Return list of connected clients;

## Prerequisites
Telegram bot run under Lede or Openwrt firmware than the first prerequisite is to have Lede/Openwrt installed.
Second prerequisite is to have ```curl``` package installed. You can do this with command ```opkg update ; opkg install curl```.

## Installation Steps

### Step one:
- Get your chat_id of Telegram. If you don't know what is your chat_id you can use bot @GiveChatId_bot ([Thanks to Helias](https://github.com/Helias/ "Helias github repo home")). Send him /chatid command and get your chat_id;
- Get a bot token and start your bot. If you don't know how get it you can use bot @BotFather. Send him /newbot command , name of your new bot and a username. Get the returned string "Use this token to access the HTTP API:" like this:

  `11334455:ArFodzmHLuasd7LY33rtfhyy4yn8qLIRt5e`

### Step two:
Copy the files of this repo under ```/root/``` directory of your Lede/Openwrt system.
Set files as executable with commands:
```sh
cd /root/
chmod +x -R telegrambot restart_telegram_bot telegram_bot functions/*
``` 
Copy ```telegrambot``` file under ```/etc/init.d/``` directory and enable it with command 
```sh
cd /root/
cp telegrambot /etc/init.d/
/etc/inid.d/telegrambot enable
```
### Step three:
Set your variables (bot token and chat id) in ```variables``` file under ```/root/``` dir.

Enjoy your bot!

