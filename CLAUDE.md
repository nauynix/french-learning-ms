# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static GitHub Pages site for French language learning. The main feature is a multisearch tool that opens three browser tabs simultaneously to look up a French word across Linguee (translations), French Wiktionary (pronunciation), and Google Images (visual flashcard material). The approach is based on the Fluent Forever method.

Live site: https://nauynix.github.io/french-learning-ms/Multisearch-French.html

## Architecture

- **Multisearch-French.html** — Single-page app with inline JavaScript. Listens for Enter key on the search input, then opens three tabs with the search term URL-encoded into Linguee, Google Translate (wrapping Google Images FR), and Google Translate (wrapping French Wiktionary).
- **basic.css** — Third-party minimal CSS framework (Basic.css, MIT license) with dark mode support. Shared stylesheet, not project-specific.
- **my-docs/** — Personal French learning resources: learning plan, conversation questions, and a CSV learning log.

## Development

No build step, package manager, or test suite. To develop locally, open `Multisearch-French.html` directly in a browser or serve with any static file server.
