# Terminal Holo Deck

A Claude Code plugin that lets users enter virtual rooms and converse with groups of historical figures.

## Project Structure

- `plugin.json` - Plugin manifest
- `commands/` - Slash commands (/holodeck, /enter-room)
- `rooms/` - Room definitions, each containing a `room.md` and `agents/` directory
- `skills/` - Shared skills (research-and-cache)
- `cache/` - Local research cache (gitignored)
- `confidence-tiers.md` - Methodology for agent confidence levels

## Key Concepts

- **Confidence Tiers**: Agents are classified Tier 1 (extensive primary sources) or Tier 2 (substantial but less direct records)
- **Agent Prompts**: Each agent has a detailed system prompt based on documented writings, speeches, and historical records
- **Research Caching**: Agents can use web browsing to verify facts and cache findings locally

## Rooms

1. Renaissance Workshop - da Vinci, Michelangelo, Galileo
2. Enlightenment Salon - Franklin, Voltaire, Adam Smith
3. Scientific Minds - Einstein, Feynman, Curie
4. Ancient Agora - Socrates, Marcus Aurelius, Sun Tzu
5. Writers' Parlor - Twain, Wilde, Austen
6. Podcast Studio - Peterson, Rogan, Fridman
7. Founders' Table - Jefferson, Hamilton, Franklin
8. Tech Visionaries - Jobs, Tesla, Lovelace
9. War Room - Churchill, Napoleon, Sun Tzu
10. Musicians' Green Room - Cohen, Bowie, Mercury
11. Existentialist Cafe - Nietzsche, Camus, de Beauvoir
