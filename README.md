# Swedy Under-12 Bot

Same Discord-to-Telegram bot, but with a price filter.

It only posts products where price < MAX_PRICE.

With MAX_PRICE=12:
- $11.99 posts
- €11.99 posts
- $12.00 is skipped
- €12.00 is skipped

## Railway Variables

DISCORD_TOKEN
TELEGRAM_TOKEN
DISCORD_CHANNEL_ID
TELEGRAM_CHAT_ID
POST_DELAY_SECONDS
MAX_PRICE

## Start Command

npm start
