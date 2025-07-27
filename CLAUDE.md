# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

VamSurEnglish is a web-based English learning survival game that combines vocabulary acquisition with action gameplay. Players collect alphabet letters to complete English words while surviving waves of monsters, featuring progressive difficulty levels and upgrade systems.

## How to Run

This is a standalone HTML5 game with no build process required:

1. Open `index.html` directly in any modern web browser
2. No server setup needed - runs completely client-side
3. Works on both desktop and mobile devices

## Development Commands

Since this is a pure HTML/CSS/JavaScript project:
- **Local development**: Simply open `index.html` in browser and refresh after changes
- **No build tools**: Direct file editing, no compilation step required
- **No package manager**: No npm/yarn dependencies

## Architecture

### Single-File Structure
- **index.html**: Contains the entire application (HTML, CSS, JavaScript) in a single 2700+ line file
- **english_words_complete.json**: Word database with 19 difficulty levels containing ~1500 English words
- **assets/**: Audio files (death.mp3, hit.mp3, levelup.mp3)

### Core Game Systems (All in index.html)

**Game State Management (lines ~1400-1500)**:
- Game states: menu, playing, paused, gameOver, levelUp
- Player stats: level, experience, health, score
- Upgrade system with 6 categories

**Rendering Engine (lines ~1800-2200)**:
- Canvas-based 2D graphics with particle systems
- Real-time UI overlays and animations
- Mobile-responsive touch controls

**Word Learning System (lines ~440-1400)**:
- 19 progressive difficulty levels
- Missing letter completion mechanic
- Korean translations and pronunciation features
- TTS (Text-to-Speech) integration

**Game Mechanics (lines ~1500-1800)**:
- Player movement (WASD/touch/mouse)
- Monster spawning and AI
- Collision detection
- Experience and leveling system

### Data Structure
- **wordSets**: Embedded word database organized by difficulty levels (1단계 through 19단계)
- **Word objects**: `{word, display, missing, meaning}` format
- **Game objects**: Player, monsters, particles, upgrades stored in global arrays

## Key Features

- **Multilingual**: Korean UI with English word learning
- **Progressive Difficulty**: 19 levels with increasing word complexity
- **Audio Integration**: Sound effects and text-to-speech
- **Mobile Support**: Touch controls and responsive design
- **Particle Effects**: Visual feedback for actions and achievements

## Code Patterns

- **Global variables**: Extensive use of global state for game objects
- **Canvas API**: Direct 2D context manipulation for rendering
- **Event-driven**: Mouse, touch, and keyboard event handlers
- **Embedded data**: Word database and game logic in single file
- **No frameworks**: Vanilla JavaScript with HTML5 Canvas

## Word Database

The `english_words_complete.json` contains structured vocabulary data:
- 19 difficulty levels (1단계 to 19단계)
- Each word has: complete word, display pattern with missing letter, target letter, Korean meaning
- Progression from basic words (a, I, go) to complex vocabulary (international, collaboration)