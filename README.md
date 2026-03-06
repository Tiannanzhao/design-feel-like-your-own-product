# 🎨 design-feel-like-your-own-product — Claude Skill

A Claude skill that learns a designer's style from Figma files and creates new components that feel authentic to their design system.

> **"Read the file to understand how this designer thinks — not to copy what they've already made."**

---

## What it does

Most AI tools try to pixel-perfectly replicate what's already in a Figma file. This skill does something different: it builds a **mental model of how the designer thinks**, so it can create brand-new components that feel like the designer made them.

It learns:
- Color semantics (not just hex values)
- Signature design moves (border radius, status indicators, spacing habits)
- Information hierarchy rules
- How feedback maps to design principles

---

## How to install

### Claude.ai (web/mobile)

1. Download this repository as a **ZIP file** (keep the folder structure intact)
2. Go to **Settings → Capabilities** and enable **Code execution and file creation**
3. Go to **Customize → Skills → "+" → Upload a skill**
4. Upload the ZIP file
5. Toggle the skill **ON**

### Claude Code (terminal)

```bash
# Personal (available across all projects)
cp -r design-feel-like-your-own-product ~/.claude/skills/design-feel-like-your-own-product

# Or project-specific
cp -r design-feel-like-your-own-product .claude/skills/design-feel-like-your-own-product
```

---

## How to use

Once installed, the skill triggers automatically when you:

- Share a Figma file and ask to create new components
- Say things like "make it look like my design" or "match the style"
- Ask to extend an existing design system

**Example prompts:**
- *"Here's my Figma file. Create a new notification component that matches my style."*
- *"Build a data table that feels like the rest of my dashboard."*
- *"Extend my design system with an onboarding flow."*

---

## Skill structure

```
design-style-learning/
└── SKILL.md        # Main skill instructions
```

---

## License

This skill is licensed under **CC BY-NC 4.0**.

✅ You may use, share, and adapt this skill freely  
✅ You must credit the original author  
❌ You may **not** use it for commercial purposes  

See [LICENSE](./LICENSE) for full terms.

---

## Author

Created by **Tiannan Zhao**  
GitHub: [@Tiannanzhao](https://github.com/Tiannanzhao)
