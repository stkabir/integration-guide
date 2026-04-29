# Project Context: Integration Guide

## Project Overview

**Name**: Guía de Instalación - OpenCode + MiniMax.io + Slack + Google Calendar/Sheets
**Type**: Astro Web Application
**Language**: Spanish (es)
**Location**: `C:\laragon\www\integration-guide`

## Purpose

A step-by-step installation guide (14 steps) that walks users through setting up:
- Windows Terminal & PowerShell
- Node.js, pnpm
- OpenCode AI CLI
- MiniMax.io as AI provider
- Slack App with Socket Mode
- Google Cloud Platform (Calendar + Sheets APIs)
- MCP servers (Model Context Protocol)
- Global configuration files (opencode.jsonc, AGENTS.md)

## Tech Stack

- **Framework**: Astro 6.1.9
- **Styling**: Tailwind CSS 4.2.4
- **Package Manager**: pnpm
- **Node Version**: >= 22.12.0

## Project Structure

```
/
├── src/
│   ├── pages/
│   │   └── index.astro          # Main page with navigation, footer, step content
│   ├── components/
│   │   └── Steps.astro          # 14-step content data (embedded JS)
│   ├── layouts/
│   │   └── Layout.astro        # HTML layout with theme init, Inter font
│   └── styles/
│       └── global.css           # Tailwind imports, custom scrollbar, theme
├── public/
│   ├── favicon.svg
│   └── favicon.ico
├── dist/                        # Built output
├── astro.config.mjs             # Astro + Tailwind Vite plugin config
├── package.json
├── tsconfig.json
└── README.md
```

## Key Features

1. **Theme Toggle**: Dark/light mode with localStorage persistence and system preference detection
2. **Step Navigation**: Previous/Next buttons + step jump modal
3. **Progress Persistence**: localStorage key `integration-guide-progress` stores current step and completed steps
4. **Keyboard Navigation**: Arrow keys (left/right) to navigate, Escape to close modal
5. **WhatsApp Help**: Fixed link in navbar to contact support
6. **Responsive Design**: Mobile-friendly with Tailwind breakpoints

## Commands

| Command | Action |
|---------|--------|
| `pnpm install` | Install dependencies |
| `pnpm dev` | Start dev server at localhost:4321 |
| `pnpm build` | Build production site to `./dist/` |
| `pnpm preview` | Preview built site locally |
| `pnpm astro ...` | Run Astro CLI commands |

## Steps Content (14 total)

1. Instalar Windows Terminal y PowerShell
2. Instalar Node.js
3. Instalar pnpm
4. Instalar OpenCode
5. Conectar MiniMax.io como proveedor
6. Configurar credenciales globales en Windows
7. Crear Slack App
8. Configurar GCP Project
9. Configurar Google Calendar MCP
10. Configurar Google Sheets MCP
11. Crear opencode.jsonc global
12. Configurar AGENTS.md
13. Verificación final
14. Scripts de verificación

## LocalStorage Keys

- `theme`: 'dark' | 'light' - UI theme preference
- `integration-guide-progress`: JSON object with `currentStep` and `completedSteps` array

## Important Notes

- The Steps.astro component embeds all 14 steps as data (stepsData array) and renders them via client-side JavaScript
- Theme initialization runs in `<script is:inline>` before page render to prevent flash
- The step jump modal is dynamically populated from step data
- Step content includes info boxes (blue), warnings (amber), and code blocks (dark slate)
