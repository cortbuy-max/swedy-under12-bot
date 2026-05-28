# Discord Budget Bot 💰

Ein Discord to Telegram Bot, der nur Produkte unter **$12** von Discord zu Telegram postet.

## Features ✨

- 🎯 **Automatische Preis-Filterung**: Postet nur Produkte unter $12
- 🖼️ **Intelligente Bild-Deduplication**: Verhindert doppelte Produktbilder
- 📱 **Discord zu Telegram**: Automatisierte Nachrichtenweiterleitung
- 🔗 **Shopping-Agent Links**: Integriert CSSBuy, Litbuy, Hipobuy und mehr
- 💬 **Formatierte Nachrichten**: Schöne HTML-formatierte Telegram-Posts

## Setup 🚀

### 1. Voraussetzungen

- Node.js >= 16.0.0
- Discord Bot Token
- Telegram Bot Token
- Discord Channel ID
- Telegram Chat ID

### 2. Installation

```bash
# Abhängigkeiten installieren
npm install

# Oder mit Yarn
yarn install
```

### 3. Environment Variablen

Erstelle eine `.env` Datei im Projektroot:

```env
DISCORD_TOKEN=dein_discord_token_hier
TELEGRAM_TOKEN=dein_telegram_token_hier
DISCORD_CHANNEL_ID=dein_discord_channel_id
TELEGRAM_CHAT_ID=dein_telegram_chat_id
POST_DELAY_SECONDS=30
PORT=3000
```

### 4. Bot starten

```bash
# Production
npm start

# Development (mit auto-reload)
npm run dev
```

## Konfiguration ⚙️

### Preis-Filter

Der Bot filtert automatisch nur Produkte unter $12. Der Filter kann in `index.js` angepasst werden:

```javascript
const MAX_PRICE = 12; // Ändere diesen Wert für einen anderen Preis-Limit
```

### Shopping Agents

Folgende Agents werden unterstützt:
- Litbuy
- Hipobuy
- KakoBuy
- Lovegobuy
- CSSBuy
- MuleBuy

### Discord Channel

Der Bot überwacht einen spezifischen Discord Channel. Alle Produkt-Nachrichten aus diesem Channel mit Preis unter $12 werden zu Telegram gepostet.

## Umgebung

### Umgebungsvariablen

| Variable | Beschreibung | Pflicht |
|----------|-------------|---------|
| `DISCORD_TOKEN` | Discord Bot Token | ✅ |
| `TELEGRAM_TOKEN` | Telegram Bot Token | ✅ |
| `DISCORD_CHANNEL_ID` | Discord Channel zum Überwachen | ✅ |
| `TELEGRAM_CHAT_ID` | Telegram Chat/Channel zum Posten | ✅ |
| `POST_DELAY_SECONDS` | Verzögerung zwischen Posts (Sek) | ❌ (Standard: 30) |
| `PORT` | Port für Web Server | ❌ (Standard: 3000) |

## Discord Bot Setup 🤖

1. Gehe zu https://discord.com/developers/applications
2. Erstelle eine neue Application
3. Gehe zu "Bot" und klicke "Add Bot"
4. Kopiere den Token in `DISCORD_TOKEN`
5. Aktiviere "Message Content Intent" in den Privileged Gateway Intents
6. Gehe zu "OAuth2" → "URL Generator"
7. Wähle Scopes: `bot`
8. Wähle Permissions: `Read Message History`, `Read Messages/View Channels`, `Send Messages`
9. Öffne die generierte URL und lade den Bot in deinen Server

## Telegram Bot Setup 📱

1. Schreibe mit [@BotFather](https://t.me/botfather) auf Telegram
2. Sende `/newbot` und folge den Anweisungen
3. Kopiere den Token in `TELEGRAM_TOKEN`
4. Schreibe `/setprivacy` und wähle deinen Bot
5. Setze Privacy auf "Disabled"

## Logs 📋

Der Bot gibt detaillierte Logs aus:
- Gefundene Produktbilder
- Erkannte Preise und Produktnamen
- Entfernte Duplikate
- Telegram API Errors
- Rate Limiting

## Troubleshooting 🔧

### Bot postet nichts
- Überprüfe, ob die Channel IDs korrekt sind
- Stelle sicher, dass der Bot die richtige Permission hat
- Überprüfe die Logs auf Error-Messages

### Doppelte Bilder
- Der Bot nutzt intelligente ID-basierte Deduplication
- Wenn trotzdem Duplikate auftreten, überprüfe die Discord-Nachricht selbst

### Telegram Errors
- Überprüfe dein Telegram Token
- Stelle sicher, dass die Chat ID korrekt ist
- Rate Limiting: Der Bot wartet automatisch bei zu vielen Requests

## API Health Check ✅

Der Bot stellt einen Health Check Endpoint bereit:

```
GET http://localhost:3000/health
```

Antwortet mit `OK` wenn der Bot läuft.

## Lizenz

MIT

## Support

Bei Fragen oder Issues, erstelle einen Issue auf GitHub oder kontaktiere den Maintainer.

---

Made with ❤️ for Budget Shopping
