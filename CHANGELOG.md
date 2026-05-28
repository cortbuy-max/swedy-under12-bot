# Changelog

All notable changes to this project will be documented in this file.

## [1.0.0] - 2024

### Added
- Initial release of Discord Budget Bot
- Automatic price filtering for products under $12
- Discord to Telegram message forwarding
- Intelligent image deduplication system
- Support for multiple shopping agents (CSSBuy, Litbuy, Hipobuy, KakoBuy, Lovegobuy, MuleBuy)
- HTML-formatted Telegram messages
- Product name truncation to single line
- Health check endpoint
- Comprehensive error handling and logging
- Rate limiting support for Telegram API

### Features
- 🎯 Filters products by maximum price ($12)
- 🖼️ Removes duplicate product images
- 📱 Seamless Discord to Telegram integration
- 🔗 Direct shopping links for agents
- 💬 Beautiful formatted messages
- ⚡ Fast processing with configurable delays
- 🔄 Automatic reconnection handling
- 📊 Detailed logging for debugging

### Configuration
- Environment variable support
- Configurable POST delay
- Configurable maximum product price
- Support for multiple shopping agents
