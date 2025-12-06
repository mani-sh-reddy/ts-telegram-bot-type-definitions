# @mani-sh-reddy/ts-telegram-bot-type-definitions

Complete, production-ready TypeScript type definitions for the **Telegram Bot API 9.2**.

[![npm version](https://img.shields.io/npm/v/%40mani-sh-reddy%2Fts-telegram-bot-type-definitions.svg)](https://www.npmjs.com/package/@mani-sh-reddy/ts-telegram-bot-type-definitions)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## Features

✅ **200+ complete type definitions** - All core types from Telegram Bot API 9.2
✅ **Well-organized** - Grouped into logical sections (Messages, Media, Users/Chats, Keyboards, etc.)
✅ **Type-safe discriminated unions** - `MessageOrigin`, `ChatMember`, `BackgroundType`, etc.
✅ **Zero dependencies** - Pure TypeScript types, no runtime code
✅ **Full inline documentation** - JSDoc comments throughout
✅ **All new features** - Business accounts, paid media, gifts, boosts, stories, and more

## Installation

```bash
npm install @mani-sh-reddy/ts-telegram-bot-type-definitions
```

## Quick Start

```typescript
import { 
  Update, 
  Message, 
  User, 
  Chat,
  CallbackQuery 
} from '@mani-sh-reddy/ts-telegram-bot-type-definitions';

function handleUpdate(update: Update) {
  if (update.message) {
    const msg: Message = update.message;
    const sender: User | undefined = msg.from;
    const chat: Chat = msg.chat;
    const text: string | undefined = msg.text;
    
    console.log(`Message from ${sender?.first_name}: ${text}`);
  }
  
  if (update.callback_query) {
    const query: CallbackQuery = update.callback_query;
    const data: string | undefined = query.data;
  }
}
```

## Type Categories

### Core Types
- `Update` - Incoming update from Telegram
- `User` - Telegram user
- `Chat` - Chat (private, group, supergroup, channel)
- `Message` - Message in chat
- `WebhookInfo` - Webhook status

### Message Content
- `MessageEntity` - Special entities (mention, hashtag, URL, etc.)
- `TextQuote` - Quoted message parts
- `ExternalReplyInfo` - Replies from other chats
- `ReplyParameters` - Reply message references

### Media Types
- `PhotoSize`, `Animation`, `Audio`, `Document`
- `Video`, `VideoNote`, `Voice`
- `Sticker`, `Game`
- `Contact`, `Location`, `Venue`
- `PaidMediaInfo` - Paid media content
- `Poll`, `Checklist` - Polls and checklists

### User & Chat
- `ChatMember` - Chat membership status (creator, admin, member, restricted, left, kicked)
- `ChatMemberUpdated` - Changes to membership
- `ChatPermissions` - Default permissions
- `ChatLocation` - Chat location
- `ChatPhoto`, `Birthdate`, `BusinessIntro`, `BusinessLocation`

### Reactions & Messages
- `ReactionType` - Emoji, custom emoji, or paid reactions
- `MessageReactionUpdated` - Reaction changes
- `ChatBoost` - Chat boost information
- `Gift`, `UniqueGift` - Gift objects

### Keyboard & Buttons
- `ReplyKeyboardMarkup`, `ReplyKeyboardRemove`
- `InlineKeyboardMarkup`, `InlineKeyboardButton`
- `KeyboardButton` with request options
- `LoginUrl`, `WebAppInfo`

### Inline Queries
- `InlineQuery` - Inline query
- `ChosenInlineResult` - Selected inline result
- `InlineQueryResult` - 20+ different result types
- `InputMessageContent` - Input message variations

### Payments
- `Invoice`, `ShippingOption`, `LabeledPrice`
- `SuccessfulPayment`, `RefundedPayment`
- `ShippingQuery`, `PreCheckoutQuery`

### Business Features
- `BusinessConnection`, `BusinessMessagesDeleted`
- `SuggestedPostInfo`, `SuggestedPostApproved/Declined/Paid`
- `DirectMessagePriceChanged`

### Callback & Commands
- `CallbackQuery` - Callback button pressed
- `BotCommand`, `BotCommandScope`
- `MenuButton`

### Misc
- `PassportData` - Telegram Passport data
- `StarTransaction`, `StarTransactions` - Telegram Star payments
- `TransactionPartner` - Payment sources/recipients

## API Response Wrapper

All API responses can be typed with:

```typescript
import { TelegramApiResponse } from '@mani-sh-reddy/ts-telegram-bot-type-definitions';

const response: TelegramApiResponse<{ ok: boolean }> = {
  ok: true,
  result: { ok: true }
};

if (response.ok && response.result) {
  // Use result safely
}
```

## Version History

### 1.0.0 (Current)
- Initial release with full Telegram Bot API 9.2 support
- 200+ type definitions
- All core features included

## Contributing

Found a bug or want to add more types? Contributions are welcome!

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

MIT - See [LICENSE](LICENSE) file for details

## Support

For issues or questions:
- GitHub Issues: [ts-telegram-bot-type-definitions/issues](https://github.com/mani-sh-reddy/ts-telegram-bot-type-definitions/issues)
- Check [Telegram Bot API Docs](https://core.telegram.org/bots/api)

