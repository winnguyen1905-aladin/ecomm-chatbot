# feat: OpenAI reply handler

Non-command text messages are now answered by an OpenAI chat completion.

## What changed
- New OpenAI client wrapper.
- `Messages()` forwards text to the model and replies in-chat.
- Friendly fallback when the API call fails.
- `OPENAI_API_KEY` read from config.

## Impact
Users can ask natural-language product questions and get answers.
