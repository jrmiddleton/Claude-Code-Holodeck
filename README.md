# Claude Code Holodeck

![Claude Code Holodeck](banner.png)

A Claude Code plugin that lets you step into virtual rooms and have conversations with groups of history's most fascinating minds.

Inspired by Star Trek's holodeck, each room gathers historical figures who share intellectual connections. Every agent is backed by a carefully researched system prompt drawn from their actual writings, letters, speeches, and documented philosophy.

## What Makes This Different

Most AI "talk to historical figures" experiences are shallow roleplay. Claude Code Holodeck takes a different approach:

**Confidence Tiers** - We only include people where there's enough historical data to genuinely replicate their voice. Each figure is classified into tiers based on the depth of available primary sources:

- **Tier 1 (High Confidence)**: Extensive primary sources - books they wrote, letters they sent, speeches they gave, interviews on record
- **Tier 2 (Good Confidence)**: Substantial records but less direct voice - works attributed to them, accounts by contemporaries, limited surviving correspondence

This honesty about source quality means you know how authentic each conversation really is.

## Available Rooms

### Renaissance Workshop
*A sunlit Florentine workshop with drawing tables, marble blocks, and mechanical models*

- **Leonardo da Vinci** (Tier 1) - Polymath, painter, inventor
- **Michelangelo** (Tier 2) - Sculptor, painter, architect, poet
- **Galileo** (Tier 2) - Astronomer, physicist, "father of modern science"

### Enlightenment Salon
*An elegant 18th-century Parisian salon with candlelight and fine wine*

- **Benjamin Franklin** (Tier 1) - Founding Father, scientist, diplomat
- **Voltaire** (Tier 1) - Writer, philosopher, champion of civil liberties
- **Adam Smith** (Tier 2) - Economist, moral philosopher

### Scientific Minds
*A university office with chalkboards covered in equations*

- **Albert Einstein** (Tier 1) - Theoretical physicist, relativity
- **Richard Feynman** (Tier 1) - Theoretical physicist, teacher, raconteur
- **Marie Curie** (Tier 2) - Physicist, chemist, two-time Nobel laureate

### Ancient Agora
*An open-air Athenian marketplace with marble columns and olive trees*

- **Socrates** (Tier 2) - Philosopher, originator of the Socratic method
- **Marcus Aurelius** (Tier 1) - Roman Emperor, Stoic philosopher
- **Sun Tzu** (Tier 2) - Military strategist, philosopher

### Writers' Parlor
*A Victorian-era London drawing room with overstuffed armchairs and brandy*

- **Mark Twain** (Tier 1) - Novelist, humorist, lecturer
- **Oscar Wilde** (Tier 1) - Playwright, poet, wit
- **Jane Austen** (Tier 2) - Novelist, social commentator

### The Podcast Studio
*A professional studio with boom mics, mixing boards, and whiskey*

- **Jordan Peterson** (Tier 1) - Clinical psychologist, cultural commentator
- **Joe Rogan** (Tier 1) - Comedian, UFC commentator, podcaster
- **Lex Fridman** (Tier 1) - AI researcher, MIT lecturer, podcaster

### The Founders' Table
*A candlelit Philadelphia tavern in the 1780s*

- **Thomas Jefferson** (Tier 1) - Third President, author of the Declaration
- **Alexander Hamilton** (Tier 1) - First Secretary of the Treasury
- **Benjamin Franklin** (Tier 1) - Founding Father, scientist, diplomat

### Tech Visionaries
*A room shifting between Tesla's lab, Apple's workbench, and Babbage's Engine*

- **Steve Jobs** (Tier 1) - Co-founder of Apple, design visionary
- **Nikola Tesla** (Tier 2) - Inventor, electrical engineer, futurist
- **Ada Lovelace** (Tier 2) - Mathematician, first computer programmer

### The War Room
*A bunker with strategic maps spanning centuries*

- **Winston Churchill** (Tier 1) - Prime Minister, statesman, author
- **Napoleon Bonaparte** (Tier 1) - Emperor of France, military commander
- **Sun Tzu** (Tier 2) - Military strategist, philosopher

### Musicians' Green Room
*Backstage with velvet couches, a battered piano, and the roar of a crowd*

- **Leonard Cohen** (Tier 1) - Poet, singer-songwriter, Zen monk
- **David Bowie** (Tier 1) - Musician, actor, cultural chameleon
- **Freddie Mercury** (Tier 2) - Singer, frontman of Queen

### The Existentialist Cafe
*A smoky Left Bank Parisian cafe in the rain*

- **Friedrich Nietzsche** (Tier 1) - Philosopher, cultural critic
- **Albert Camus** (Tier 1) - Author, philosopher, Nobel laureate
- **Simone de Beauvoir** (Tier 1) - Philosopher, feminist theorist

## Installation

Add the GitHub repo as a marketplace and install:

```bash
claude plugin marketplace add github:your-username/claude-code-holodeck
claude plugin install claude-code-holodeck
```

This persists across sessions and supports updates via `claude plugin update claude-code-holodeck`.

### Development / Testing

If you've cloned the repo locally, you can load it for a single session:

```bash
claude --plugin-dir ./claude-code-holodeck
```

## Usage

### Browse Available Rooms
```
/holodeck
```

### Enter a Room
```
/enter-room renaissance_workshop
```

Once inside a room, simply start talking. Use `@` to address specific figures (e.g., `@Einstein what do you think?`) or just speak to the room and everyone responds.

### How It Works

Each historical figure runs as an **independent Claude Code agent** with its own system prompt, personality, and tool access. An orchestrator manages the conversation:

1. Your message is sent to each figure's agent in parallel
2. Each agent responds in character, using web search to verify facts when needed
3. The orchestrator presents their responses and a brief room summary
4. Figures never loop endlessly -- one round per message, then back to you

### Agent Capabilities

Each figure can:
- **Search the web** to verify quotes, dates, and facts about their own works
- **Read and write files** to cache research findings locally in `cache/`
- **Stay grounded** in documented primary sources for their confidence tier

## How Agent Prompts Work

Each historical figure has a dedicated agent file containing:

- **Voice & Personality**: Documented speech patterns, wit style, known traits
- **Knowledge & Expertise**: Areas of deep knowledge, major works, key beliefs
- **Worldview**: Philosophical positions, values, documented opinions
- **Relationships**: Historical connections to other figures in the room
- **Behavioral Guidelines**: Stay in character, cite real works, acknowledge knowledge limits

## Contributing

Want to add a new room or historical figure? See `confidence-tiers.md` for the methodology. New figures should have sufficient primary source material to justify their confidence tier.

## License

MIT
