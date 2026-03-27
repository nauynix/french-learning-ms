# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static GitHub Pages site for building Anki flashcards to learn common French words. Based on the Fluent Forever method. All-in-one page that shows translation, pronunciation, example sentences, and AI images inline.

Live site: https://nauynix.github.io/french-learning-ms/Multisearch-French.html

## Architecture

- **Multisearch-French.html** — Single-page app with inline CSS and JavaScript. No framework, no build step. All logic is in a single `<script>` block.
- **basic.css** — Third-party minimal CSS framework (Basic.css, MIT license) with dark mode support.
- **my-docs/** — Personal French learning resources.

## APIs (all called client-side, no backend)

- **Lingva Translate** (`lingva.ml/api/v1/`) — Translation (en↔fr), sentence TTS audio (`/audio/fr/`). Free, no key.
- **Wiktionary API** (`en.wiktionary.org/w/api.php`) — Multiple translations with glosses (from `[data-gloss]` translation tables), IPA, pronunciation audio (from `#French` section). Parsed HTML uses `div.mw-heading2` for section boundaries.
- **Tatoeba API** (`api.tatoeba.org/unstable/sentences`) — French example sentences. Search with quoted phrases, `sort=random`, filter for 4+ words.
- **Hugging Face Inference API** — AI image generation (Stable Diffusion XL). Requires user's HF token stored in localStorage.

## Key patterns

- Audio: prefer mp3 over ogg for iOS compatibility. Convert Wikimedia ogg URLs to transcoded mp3 equivalents.
- Two input modes: English (translates → French) and French (word lookup or sentence TTS).
- French sentences detected by presence of spaces in French mode input.
- Translation selection: clickable buttons that re-fetch pronunciation and examples for the chosen word.

## Development

No build step, package manager, or test suite. Serve locally with `python3 -m http.server` and test in browser. Deploy by pushing to `main` (GitHub Pages).
