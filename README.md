# Easy Design MD

Claude Code skill for importing and managing design system documentation from multiple sources.

## Features

- **Dual-Track Selection**: Choose between brand mode or manual mode for design system selection
- **Smart Recommendations**: AI-powered design system recommendations based on your needs
- **59+ Design Systems**: Support for major design systems including Material, Ant Design, Chakra, Mantine, and more
- **Configurable Download Directory**: Save design documentation to your preferred location

## Installation

```bash
# Install from local path
/claude-skills install /path/to/easy-design-md

# Or use the skills CLI directly
agent-skills-cli install /path/to/easy-design-md
```

## Usage

After installation, use the skill in Claude Code:

```
/easy-design-md
```

Follow the interactive prompts to:
1. Select a design system (brand mode with smart recommendations or manual mode)
2. Choose your preferred download directory
3. Import design documentation

## Project Structure

```
easy-design-md/
├── skills/easy-design-md/     # Skill package
│   ├── SKILL.md               # Main skill definition
│   ├── README.md              # Skill documentation
│   └── *.png                  # Slide screenshots
└── .gitignore                 # Git ignore rules
```

## Tech Stack

- Claude Code skill framework
- HTML/CSS for presentation slides
- Python for page generation

## License

MIT