# What I Learned: APIs & Keys

Phase 00: Setup & Tooling · Lesson 04

Source: [APIs & Keys](../../../phases/00-setup-and-tooling/04-apis-and-keys/docs/en.md)

Completion: Reported complete by me; recorded on 2026-10-26.
This summary draws on the lesson and my two saved Python examples. Successful
API responses, quiz scores, and error-handling exercise results have not been
recorded yet.

## What I learned

- An API request needs an endpoint, authentication, and a request body. The
  server returns a response that my program can inspect.
- I can read API keys from environment variables rather than hardcoding them.
  My examples use `ANTHROPIC_API_KEY`. A `.env` file must be loaded into the
  environment before these scripts can use its values; neither script loads it.
- An SDK provides convenient methods and response objects. Raw HTTP exposes
  the URL, headers, JSON serialization, and response parsing directly.
- A message request specifies a model, an output token limit, and messages
  containing roles and text. `max_tokens` limits output tokens, not words.
- `LLM_MODEL` lets me select a model without changing the code.
- JSON responses use dictionaries and lists after decoding in Python, while
  the SDK exposes response fields through objects.

## My examples

| Original file | Saved example | What it demonstrates |
| --- | --- | --- |
| `solution/practice/ex0.py` | [anthropic_sdk_example.py](anthropic_sdk_example.py) | Creates an SDK client, calls `messages.create`, and prints the first text block. |
| `solution/practice/ex1.py` | [anthropic_raw_http_example.py](anthropic_raw_http_example.py) | Builds a POST request with headers and encoded JSON, then decodes the response. |

Both examples ask: “What is a neural network in one sentence?” They read the
model from `LLM_MODEL`, with different fallback values in the original files.
Set the same accessible model in `LLM_MODEL` when comparing them; those fallback
model names have not been checked for current availability.

## Running my examples

From the repository root, with `ANTHROPIC_API_KEY` and `LLM_MODEL` already set:

```bash
python3 solution/00-setup-and-tooling/04-apis-and-keys/anthropic_sdk_example.py
python3 solution/00-setup-and-tooling/04-apis-and-keys/anthropic_raw_http_example.py
```

The SDK example requires the `anthropic` package in the active environment.
The raw HTTP example uses only Python's standard library. Both commands make
live API requests when run.

## Verification and next practice

- Both saved examples passed Python syntax parsing without sending requests.
- Their contents were preserved during the move and rename.
- Live API execution and returned text have not been verified in this session.
- Compare the full SDK response and decoded HTTP JSON, including content,
  usage, and stop reason.
- Review authentication errors versus rate limits, and add explicit error
  handling and a network timeout as a future improvement. My current examples
  do not yet implement these.
