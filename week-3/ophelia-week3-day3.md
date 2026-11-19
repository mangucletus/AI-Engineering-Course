# Ophelia: Week 3, Day 3

## Tokenizer

Tokenizer is the code that maps between Text and Tokens for a particular model.

Tokenizer is the code that maps between natural language and numbers.

Translates between text, Tokens and Token IDs with encode() and decode() methods.

The starting point is a sentence comprising of letters, numbers, etc.
The tokenizer then turns the sentence into a bunch of words (chunks).

Token - fragments of words (chunks).
Token ID - the number that represent the token (number).

Token has a dictionary.

Special token - Token contains a vocab that can include Special tokens to signal information to the LLM, like start of a prompt.

## The Tokenizers For Key Models

We will experiment with tokenizers for a variety of open source models:

1. Llama 3.1 - Meta led the way
2. Phi 4 - Microsoft's entrant
3. Deepseek 3.1 - From Deepseek AI
4. Qwen 2.5 Coder - Leading open source coding model

## Vectors

Vectors are important properties of things.
Vectors are not tokenizers.
Tokens are usually inputs fed into models which may produce vectors.
