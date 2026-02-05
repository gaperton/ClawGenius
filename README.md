# familia-moderna 🏡
The family of OpenClawd agents running your household

## Overview
Familia Moderna is an NPX-executable bootstrap script that configures OpenClawd with a preset of 6 specialized agents designed for modern household management.

## The 6 Agents

1. **📅 Family Scheduler** - Coordinates all calendar appointments, school pickups, and family events
2. **🧹 Household Chores Agent** - Rotates and reminds each family member of their weekly tasks
3. **🛒 Groceries & Shopping Agent** - Tracks pantry inventory and automates weekly grocery orders
4. **📚 Schoolwork Agent** - Helps children manage homework deadlines and school communications
5. **🏠 Smart Home Agent** - Controls lights, thermostats, and checks security status
6. **💰 Finance & Bills Agent** - Monitors bill due dates and sends prompts for payments

## Quick Start

### Run with NPX (Recommended)
```bash
npx familia-moderna
```

### Or Clone and Run Locally
```bash
git clone https://github.com/gaperton/familia-moderna.git
cd familia-moderna
npm run bootstrap
```

## What Gets Created

The bootstrap script creates an `agents/` directory with:

```
agents/
├── BOOTSTRAP.md          # Initial setup guide (auto-deleted after first run)
├── USER.md              # Family profile and preferences
├── scheduler/           # Family Scheduler agent
│   ├── AGENTS.md
│   ├── SOUL.md
│   ├── IDENTITY.md
│   └── TOOLS.md
├── chores/             # Household Chores agent
│   ├── AGENTS.md
│   ├── SOUL.md
│   ├── IDENTITY.md
│   └── TOOLS.md
├── groceries/          # Groceries & Shopping agent
│   ├── AGENTS.md
│   ├── SOUL.md
│   ├── IDENTITY.md
│   └── TOOLS.md
├── schoolwork/         # Schoolwork agent
│   ├── AGENTS.md
│   ├── SOUL.md
│   ├── IDENTITY.md
│   └── TOOLS.md
├── smarthome/          # Smart Home agent
│   ├── AGENTS.md
│   ├── SOUL.md
│   ├── IDENTITY.md
│   └── TOOLS.md
└── finance/            # Finance & Bills agent
    ├── AGENTS.md
    ├── SOUL.md
    ├── IDENTITY.md
    └── TOOLS.md
```

## Configuration Files Explained

Each agent has four configuration files:

- **AGENTS.md** - Operating instructions, responsibilities, and coordination guidelines
- **SOUL.md** - Persona, values, boundaries, and emotional intelligence
- **IDENTITY.md** - Basic identity information (name, role, icon)
- **TOOLS.md** - Available tools and usage guidelines

## Next Steps After Bootstrap

1. Review and customize each agent's configuration files
2. Configure your OpenClawd installation to use these agents
3. Set up communication channels (WhatsApp, Telegram, Discord, etc.)
4. Add family member profiles to `agents/USER.md`
5. Test each agent individually
6. Enable agent collaboration features

## Requirements

- Node.js 12 or higher
- OpenClawd installation (see [openclawd.ai](https://openclawd.ai))

## Customization

All configuration files are in Markdown and can be edited to match your family's specific needs:

- Adjust agent personalities and communication styles
- Add or remove skills and capabilities
- Configure family member profiles
- Set notification preferences
- Define household rules and boundaries

## Learn More

- [OpenClawd Documentation](https://openclawd.ai/docs)
- [OpenClawd Club - Skills & Agents](https://openclawd.club)
- [Agent Configuration Guide](https://openclawd.ai/docs/concepts/agent)

## License

MIT
