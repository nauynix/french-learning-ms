# French Flashcard Builder

A static site to help English speakers build [Anki](https://apps.ankiweb.net/) flashcards for learning common French words, based on the [Fluent Forever](https://home.fluent-forever.com/) method.

**Live site:** [nauynix.github.io/french-learning-ms/Multisearch-French.html](https://nauynix.github.io/french-learning-ms/Multisearch-French.html)

## What it does

Type an English word and get everything you need for a flashcard in one screen:

- **French translation** with multiple options from Wiktionary (with meaning glosses so you can pick the right one)
- **IPA pronunciation** and audio from Wiktionary, auto-downloaded as mp3
- **Example sentences** from Tatoeba (a language learning corpus) with English translations
- **Listen and download** buttons on each sentence using text-to-speech
- **AI-generated images** for each example sentence via Hugging Face Stable Diffusion

### French mode

Toggle to French mode to:
- Look up a **French word** directly for pronunciation, examples, and reverse translation
- Type a **French sentence** to hear it spoken and download the audio as mp3

## Setup

No build step required. The site runs entirely in the browser with free, public APIs.

**For AI-generated images:** paste a free Hugging Face token in the Settings panel on the page. Get one at [huggingface.co/settings/tokens](https://huggingface.co/settings/tokens). The token is stored in your browser's localStorage only and is never sent anywhere except Hugging Face.

## APIs used

All APIs are free, CORS-enabled, and require no API keys (except Hugging Face for images):

| Feature | Source |
|---------|--------|
| Translation | [Lingva Translate](https://lingva.ml) (Google Translate proxy) |
| Multiple translations with glosses | [English Wiktionary API](https://en.wiktionary.org) |
| IPA and word audio | [English Wiktionary API](https://en.wiktionary.org) |
| Example sentences | [Tatoeba API](https://tatoeba.org) |
| Sentence translation | [Lingva Translate](https://lingva.ml) |
| Sentence audio (TTS) | [Lingva Translate](https://lingva.ml) |
| AI images | [Hugging Face Inference API](https://huggingface.co) (free tier, token required) |

## Learning resources

The `my-docs/` folder contains personal French learning resources:
- `French-learning-plan.md` — learning plan based on Fluent Forever
- `conversation-questions.md` — conversation practice questions
- `Language-Learning-Log-French.csv` — learning progress log
