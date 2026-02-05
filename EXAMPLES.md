# Usage Examples

## Basic Usage

### Quick Start with NPX
```bash
# Create a new directory for your household agents
mkdir my-household
cd my-household

# Run the bootstrap script
npx familia-moderna

# View the generated structure
ls -la agents/
```

### Local Installation
```bash
# Clone the repository
git clone https://github.com/gaperton/familia-moderna.git
cd familia-moderna

# Run the bootstrap script
npm run bootstrap

# Or use node directly
node bin/bootstrap.js
```

## What You'll Get

After running the script, you'll have a complete agent configuration:

```
agents/
├── BOOTSTRAP.md          # One-time setup guide
├── USER.md              # Family profile template
├── scheduler/           # 📅 Family Scheduler
├── chores/             # 🧹 Household Chores Agent
├── groceries/          # 🛒 Groceries & Shopping Agent
├── schoolwork/         # 📚 Schoolwork Agent
├── smarthome/          # 🏠 Smart Home Agent
└── finance/            # 💰 Finance & Bills Agent
```

## Customization Examples

### Example 1: Customizing Agent Personality

Edit `agents/scheduler/SOUL.md` to change the scheduler's personality:

```markdown
## Persona
You are extremely organized, detail-oriented, and love creating color-coded schedules.
Always suggest optimal times based on family energy levels and preferences.
```

### Example 2: Adding Family Members

Edit `agents/USER.md` to add your family:

```markdown
## Family Members

### Mom - Sarah
- Preferred name: Sarah
- Communication style: Direct and concise
- Best contact time: 9am-5pm weekdays
- Priority level: High

### Dad - John
- Preferred name: John
- Communication style: Detailed with context
- Best contact time: 6pm-9pm
- Priority level: High

### Kids - Emma & Lucas
- Emma (age 12): Homework reminders at 4pm
- Lucas (age 9): Simplified messages, emoji encouraged
```

### Example 3: Configuring the Chores Agent

Edit `agents/chores/AGENTS.md` to set up a weekly rotation:

```markdown
## Weekly Rotation Schedule

### Week 1
- Emma: Dishes, Room cleanup
- Lucas: Trash, Pet feeding
- Parents: Laundry, Grocery shopping

### Week 2
- Emma: Trash, Pet feeding
- Lucas: Dishes, Room cleanup
- Parents: Yard work, Deep cleaning
```

### Example 4: Setting Up Smart Home Integration

Edit `agents/smarthome/TOOLS.md` to configure devices:

```markdown
## Connected Devices

### Living Room
- Smart lights (Philips Hue)
- Smart thermostat (Nest)
- Smart TV (Samsung)

### Bedroom
- Smart lights (LIFX)
- Smart blinds (Somfy)

### Security
- Ring doorbell
- Motion sensors
- Smart locks
```

## Integration with OpenClawd

### Step 1: Install OpenClawd
```bash
# Follow OpenClawd installation guide
curl -fsSL https://openclawd.ai/install.sh | bash
```

### Step 2: Generate Agent Configurations
```bash
npx familia-moderna
```

### Step 3: Point OpenClawd to Your Agents
```bash
# Configure OpenClawd to use the generated agents
openclawd config set agents-dir ./agents

# Or use environment variable
export OPENCLAWD_AGENTS_DIR=./agents
```

### Step 4: Start Your Agents
```bash
# Start all agents
openclawd start --all

# Or start individual agents
openclawd start scheduler
openclawd start chores
openclawd start groceries
openclawd start schoolwork
openclawd start smarthome
openclawd start finance
```

## Communication Channels

### WhatsApp Integration
```bash
# Connect to WhatsApp
openclawd connect whatsapp

# Assign agents to WhatsApp
openclawd assign scheduler --channel whatsapp
openclawd assign chores --channel whatsapp
```

### Telegram Integration
```bash
# Connect to Telegram
openclawd connect telegram --bot-token YOUR_BOT_TOKEN

# Assign agents
openclawd assign groceries --channel telegram
openclawd assign finance --channel telegram
```

### Discord Integration
```bash
# Connect to Discord
openclawd connect discord --token YOUR_DISCORD_TOKEN

# Create family server with agent channels
openclawd discord setup-family-server
```

## Advanced Usage

### Creating Custom Agent Workflows

Create a workflow file `workflows/morning-routine.yaml`:

```yaml
name: Morning Routine
triggers:
  - time: "07:00"
    days: ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"]

actions:
  - agent: scheduler
    action: send_daily_agenda
  
  - agent: chores
    action: remind_morning_tasks
  
  - agent: smarthome
    action: morning_scene
    params:
      lights: on
      temperature: 72
      blinds: open
```

### Setting Up Agent Collaboration

Configure agents to work together in `agents/collaboration.md`:

```markdown
## Inter-Agent Workflows

### Grocery Shopping Workflow
1. Groceries Agent detects low inventory
2. Notifies Finance Agent to check budget
3. Finance Agent approves spending
4. Groceries Agent creates shopping list
5. Scheduler Agent suggests shopping time
6. Chores Agent assigns shopping task

### Bill Payment Workflow
1. Finance Agent detects upcoming bill
2. Notifies Scheduler Agent of due date
3. Scheduler Agent adds reminder
4. Finance Agent requests payment approval
5. Upon approval, Finance Agent processes payment
```

## Troubleshooting

### Issue: Agents directory not created
```bash
# Make sure you're in the right directory
pwd

# Run with explicit path
node /path/to/familia-moderna/bin/bootstrap.js
```

### Issue: Permission denied
```bash
# Make the script executable
chmod +x bin/bootstrap.js

# Then run it
./bin/bootstrap.js
```

### Issue: Node.js not found
```bash
# Check Node.js installation
node --version

# Install Node.js if needed (using nvm)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install node
```

## Tips and Best Practices

1. **Start Simple**: Begin with 2-3 agents and gradually add more as needed
2. **Regular Updates**: Review and update agent configurations monthly
3. **Privacy First**: Keep sensitive information in local files, not in agent memories
4. **Test Individually**: Test each agent separately before enabling collaboration
5. **Backup Configs**: Regularly backup your customized agent configurations
6. **Family Input**: Involve all family members in customizing agent personalities
7. **Gradual Automation**: Start with reminders, then move to automated actions

## Next Steps

After bootstrapping your agents:

1. ✅ Customize each agent's configuration files
2. ✅ Set up your OpenClawd installation
3. ✅ Configure communication channels
4. ✅ Add family member profiles
5. ✅ Test each agent individually
6. ✅ Enable agent collaboration
7. ✅ Set up automation workflows
8. ✅ Monitor and adjust based on family feedback

Happy automating! 🏡
