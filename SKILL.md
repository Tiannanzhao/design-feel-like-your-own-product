---
name: design-feel-like-your-own-product
description: Learn and replicate a designer's style from Figma files to create new components that feel authentic to their design system. Use this skill whenever a user shares a Figma file and wants to create new components, plugins, or UI elements that match an existing design style — even if they don't explicitly say "learn my style". Trigger when users mention Figma files, design systems, "make it look like my design", "match the style", or ask to extend an existing UI.
metadata:
  author: Tiannanzhao
  version: 1.1.0
  mcp-server: figma
---

# SKILL: Learning a Designer's Style from Figma MCP

## When to use this skill

When a designer shares a Figma file and asks you to **create new components, plugins, or code** — not simply reproduce what already exists.

The goal is not pixel-perfect replication. It's understanding how this designer thinks, so you can create things they haven't built yet and have them feel like the designer made them.

---

## Step 1: Build intuition before reading numbers

Before inspecting any values, use `get_design_context` or `get_screenshot` to look at the overall file and ask yourself:

- Is this data-dense (dashboard) or feeling-driven (marketing page)?
- Is the color palette restrained or expressive?
- Is spacing tight or airy?
- Is there a clear brand personality — oversized type, a dominant accent color, a distinctive shape language?

This builds a **mental model**. Every decision you make later should check against this model, not against an isolated value pulled from a node.

---

## Step 2: Extract design DNA — not values, patterns

Use `get_design_context` and `get_variable_defs` to read the file. Don't try to memorize every number. Look for **what keeps repeating** — those are the designer's habits and rules.

### Read color semantically, not literally

Don't store `#40AF95`. Store "this green appears only on positive indicators, always paired with a lighter tint for backgrounds." When you understand a color's **semantic role**, you can use it correctly in new contexts without guessing.

### Find the component's signature moves

Every designer has 3–5 details that appear everywhere. These are their signature:
- Border radius: 4px (professional, restrained) or 18px (pill-shaped, softer)?
- Status indicators: background fill or border?
- Table row separation: padding or gap?
- Icons: outline or filled?

Identifying these signatures is worth more than reading the entire file.

### Map the information hierarchy

How does this designer separate primary from secondary content?
- Font weight shifts (600 vs 400)?
- Color lightness shifts?
- Size changes?

Carry this hierarchy rule into every new component you create.

---

## Step 3: Use hypothesis + output instead of asking questions

This is the most important step.

**Don't ask:** "What's your primary color?"
**Do:** Make a reasoned hypothesis based on what you read, build it, and let the designer react.

Why? Designers struggle to describe what they want in words. But they instantly know when something is wrong. Every output you produce is a **concrete question** that gets a more useful answer than anything you could have asked directly.

### How to form a grounded hypothesis

Before generating, run through these mentally:

1. **For a scenario I haven't seen in the file — what color applies?** → Find the most analogous existing component and follow the same color logic.
2. **How dense should this be?** → Match the information density of the closest existing component.
3. **What am I uncertain about?** → Make a call, flag it explicitly: "I assumed X here — let me know if that's wrong."

---

## Step 4: Turn every piece of feedback into a rule update

When a designer says "that's not right," don't just fix that one thing. **Extract the principle behind it** and update your mental model of their system.

| What the designer says | Rule to internalize |
|---|---|
| "The text feels too light" | Body text uses Medium (500), not Regular (400) |
| "That red is too harsh" | Warnings use `#FF7070`, not pure red |
| "Left-align this, don't center it" | Data display components are always left-aligned |
| "Give the rows more breathing room" | Row height is 46px, not 40px — update the baseline |

Each correction is **model calibration**, not a bug fix.

---

## Step 5: Validate your model on the next new component

This is where you prove you actually learned something.

When the designer asks for something brand new, **don't go back to the file for reference**. Generate from your internalized model. Then check:

- Did I use colors with the right semantic roles?
- Are the signature moves (corner radius, spacing habits) consistent?
- Does the information hierarchy match the rest of the file?

If the designer has little to correct, the model is well-calibrated.

---

## Common mistakes

**Copying numbers instead of understanding intent**
A 20px padding in one component doesn't mean every component should use 20px. Understand what that padding is doing (creating breathing room, separating sections) and apply the same intent, not the same number.

**Trying to be perfect on the first output**
The first output exists to surface what the designer actually cares about. Being too cautious produces outputs that are too safe to give useful feedback on. Make a clear, confident attempt.

**Treating feedback as edit instructions only**
"Make this darker" means "this element needs more visual weight." Always ask what the feedback reveals about the design principle, not just what change to make.

**Ignoring layer names**
How a designer names things in Figma reflects how they think. A component called "Status Pill" rather than "Badge" signals it belongs only in status contexts. Layer naming is part of the design logic — read it that way.

---

## If Figma MCP is unavailable

If `get_design_context` or `get_variable_defs` fails, don't block. Instead:
- Ask the user to paste component properties or share a screenshot
- Ask them to describe 2–3 things they feel strongly about (color, spacing, shape)
- Proceed with whatever visual evidence is available — a partial model is better than no output

The goal is always to produce something the designer can react to.

---

## One-line summary

**Read the file to understand how this designer thinks — not to copy what they've already made.**

Your goal: new work that looks like they made it themselves.
