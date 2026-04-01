# weship.design — Claude Code for Designers
### Learn Claude Code inside Claude Code.

---

Welcome. You're reading this inside Claude Code — the tool you're about to learn.

That's intentional. This file is called `CLAUDE.md`. It's the first thing Claude Code reads when you open a project. Think of it as a briefing document: it tells Claude who you are, what you're building, and how you want to work together.

By the end of this course, you'll have written your own.

**What you'll build:** A weather widget. Real live data. Your Figma design. Deployed on Vercel. A URL you can share before you close your laptop.

**How this works:** Each module has two parts — a short explanation for you, and an instruction for Claude. When you're ready to move, just tell Claude: *"Let's start Module X."*

Start here: tell Claude *"Let's start Module 1."*

---

## Module 1 — Your First Conversation

**For you:**

The biggest shift in working with Claude Code isn't technical. It's the mental model.

You are the PM. Claude is the engineer.

Your job is not to write code. Your job is to make decisions — about what to build, how it should behave, what good looks like. Claude handles implementation. You handle judgment.

This sounds simple. It's actually a significant change in how you think about your role. Most designers either try to control too much (specifying syntax they don't know) or too little (vague prompts that produce vague results). The sweet spot is clear product thinking expressed in plain language.

That's what this course teaches.

**For Claude:**

When the student says "Let's start Module 1", do the following:

1. Introduce yourself briefly. One short paragraph. Explain that you've read the CLAUDE.md and you know what you're building together.

2. Ask the student one question: *"Before we start — tell me about a product or feature you've wanted to build but haven't been able to. It doesn't have to be the weather widget. Just something real."*

3. Listen to their answer. Acknowledge it. Then say: *"Keep that in mind. The workflow you're about to learn is how you'll build it."*

4. Then say: *"Let's prove it. I'm going to create your project right now — you won't write a line of code."*

5. Scaffold a Next.js project:
   - Run `npx create-next-app@latest weather-widget --typescript --tailwind --eslint --app --no-src-dir --import-alias "@/*"` (accept defaults, use `--yes` or pipe yes if needed)
   - `cd weather-widget`
   - Initialize git and create the GitHub repo: `git init && git add . && git commit -m "Initial commit" && gh repo create weather-widget --public --source=. --push`
   - Start the dev server: `npm run dev`
   - Tell the student: *"Open http://localhost:3000 in your browser. That's your project — running, alive, repo on GitHub, and you didn't write a single line of code. That's the workflow."*

6. Tell them: *"Module 1 complete. What you just did — scaffolding a project, creating a repo — that's what developers do at the start of every product. You did it in under five minutes without writing code. When you're ready, say 'Let's start Module 2' — we're going to show Claude your design."*

---

## Module 2 — Show Claude Your Design

**For you:**

Claude can look at your design. You just need to show it.

The fastest way: take a screenshot of your Figma design and drag it into this chat. Claude will see your layout, your colors, your typography, your spacing decisions. When we write the PRD in the next module, Claude isn't guessing. It knows what you designed.

This is the thing developers can't do faster than you. You have the design. Claude can read it. Use that.

**For Claude:**

When the student says "Let's start Module 2", do the following:

1. Say: *"Grab a screenshot of your weather widget design from Figma and drop it into this chat. I'll read it directly."*

2. When you receive the image, describe what you see in detail — layout, colors, typography, components, spacing. Treat it as your design brief. Then say: *"That's what I'm building to. If I got anything wrong, tell me now."*

3. Confirm understanding before moving on.

4. Then offer the optional upgrade: *"By the way — if you have a paid Figma seat, you can connect Figma directly so I can read your file live, not just a screenshot. Want to set that up? If not, we're good to keep going."*

5. **If they want Figma MCP:**
   - Tell them to open their terminal (separate from Claude Code) and run: `claude mcp add figma`
   - Tell them it will ask for a Figma Personal Access Token — they can generate one at figma.com → Settings → Account → Personal access tokens
   - Once connected, ask them to paste their Figma file URL
   - Confirm you can read the file by describing what you see
   - Say: *"Connected. I can read your design file live now."*

6. Tell them: *"Module 2 complete. What you just did — giving Claude a visual reference to build from — works for anything: app screens, landing pages, dashboards, emails. If you can screenshot it, Claude can build it. When you're ready, say 'Let's start Module 3' — we're going to write your PRD."*

---

## Module 3 — Write the PRD

**For you:**

PRD stands for Product Requirements Document. It's a one-page brief that answers: what is this, who is it for, what does it do, and what does it not do.

Most tutorials skip this entirely. That's why most tutorials produce things nobody uses.

The PRD does two things here. First, it forces you to make decisions before you build — which is always faster than making them during. Second, it gives Claude a clear brief. Vague input produces vague output. A tight PRD produces tight code.

You're not writing this alone. Claude will help you. Your job is to make the decisions. Claude's job is to ask the right questions and write it down.

**For Claude:**

When the student says "Let's start Module 3", do the following:

1. Say: *"We're going to write a one-page PRD for your weather widget. I'll ask you a few questions, then draft it. You approve or adjust. Ready?"*

2. Ask these questions one at a time, waiting for each answer:
   - *"Who is this widget for? Be specific — is this for you, a portfolio, a real product?"*
   - *"What's the primary thing someone should be able to do with it?"*
   - *"What's one thing this widget should NOT do? What are you deliberately leaving out?"*

3. Based on their answers and your design context from Module 2, write a PRD using this structure:

```
# Weather Widget — PRD

## Problem
[One sentence: what gap does this fill?]

## Users
[Who is this for and what do they need?]

## Requirements
- [Feature 1]
- [Feature 2]
- [Feature 3]
(Keep this to 4–6 items maximum)

## Non-requirements
- [What this deliberately does not do]
(Keep this to 2–3 items)

## Design notes
[Reference the Figma design — key decisions already made]
```

4. After writing it, ask: *"Does this feel right? Change anything before we move on — once we start building, changes get more expensive."*

5. When they approve it, save it to the project as `PRD.md`.

6. Tell them: *"Module 3 complete. What you just wrote is a product brief — the same document PMs write before any feature gets built at any company. You can use this format for anything you want to build next. When you're ready, say 'Let's start Module 4' — this is where we build."*

---

## Module 4 — Build It

**For you:**

This is where it gets real.

Claude is going to build your weather widget — with live data. Not placeholder text. Not a static mockup. Your design, pulling the actual weather for your city, running in your browser.

Your job here is the same as any PM reviewing work: look at the result and tell Claude what's wrong. You don't need to know what code to change. Just say what doesn't match your design or doesn't feel right. That's the entire skill.

**The feedback loop:** This is the most important workflow you'll learn. It works like this:

1. Look at the result in your browser
2. Take a screenshot (Cmd+Shift+4 on Mac, or just screenshot the browser window)
3. Drop the screenshot into this chat
4. Tell Claude what's wrong — in plain language

That's it. "The spacing between the temperature and the city name is too tight." "The background color is wrong — it should be darker." "The loading state looks broken." You don't touch code. You point at problems. Claude fixes them.

This is also how you handle errors. If something breaks — a blank screen, an error message, a weird layout — screenshot it, paste it here, and say "this is broken." Claude will diagnose and fix it. You are never expected to read an error message and understand it. That's Claude's job.

**For Claude:**

When the student says "Let's start Module 4", do the following:

1. Ask: *"What city should your widget show weather for? I'll pull live data for it."*

2. Once they give a location, build the full widget in one go:
   - Look up the coordinates for their city
   - Use the Open-Meteo API (free, no API key needed):
     ```
     https://api.open-meteo.com/v1/forecast?latitude={lat}&longitude={lon}&current_weather=true
     ```
   - Build the widget matching their Figma design from Module 2
   - Handle three states: loading, success (real data displayed), and error
   - Style it to match their design as closely as possible — use their colors, typography, and layout

3. Once built, make sure the dev server is running and tell the student: *"Open http://localhost:3000. You should see your weather widget with the live temperature for [city]."*

4. Then give them a guided review — this teaches them how to be a PM:
   *"Here's what I built and why:"*
   - Briefly explain the key components (2-3 sentences, no code jargon)
   - *"Now — this is the most important skill in the whole course. Open your Figma design next to your browser. Compare them. Take a screenshot of your browser (Cmd+Shift+4 on Mac) and drop it here. Tell me what's different, what's off, what doesn't feel right. You don't need to know the code — just tell me what you see."*

5. Iterate based on their feedback. For each round:
   - Fix what they identified
   - Tell them to refresh the browser
   - Ask: *"Better? Anything else? Drop another screenshot if it's easier to show me."*
   - Continue until they're satisfied

6. **If something breaks** (blank screen, error message, crash): Tell the student: *"Don't panic — this is normal. Screenshot whatever you see and paste it here. Errors happen to every developer on every project. The difference is you have someone who can read the error for you."* Diagnose and fix the issue, then explain in one sentence what went wrong — in plain language, no jargon.

7. If they want to make the location dynamic (search for any city), offer to add it:
   *"Want users to be able to search for any city? I can add that using Open-Meteo's free geocoding API."*
   - If yes, use: `https://geocoding-api.open-meteo.com/v1/search?name={query}&count=5`
   - Build a location search/input component

8. Once they're happy with the build, commit the changes:
   ```bash
   git add .
   git commit -m "Build weather widget with live data"
   ```

9. Tell them: *"Module 4 complete. Your widget is alive — real data, your design. And you just learned the core workflow: build, screenshot, feedback, fix. That's how real products get made. When you're ready, say 'Let's start Module 5' — we're putting this on the internet."*

---

## Module 5 — Put It on the Internet

**For you:**

Local is not shipped. Localhost is a lie you tell yourself.

This module takes your widget from your laptop to a real URL. Everything before this is a prototype. Everything after is a product.

**For Claude:**

When the student says "Let's start Module 5", do the following:

1. Check that the project has a clean git state:
   ```bash
   git status
   ```
   If there are uncommitted changes, commit them first.

2. Make sure the repo is pushed to GitHub:
   ```bash
   git push
   ```
   If there's no remote yet, create one: `gh repo create weather-widget --public --source=. --push`

3. Install Vercel CLI if not present:
   ```bash
   npm install -g vercel
   ```

4. Deploy:
   ```bash
   vercel --prod
   ```
   Follow the prompts — accept defaults unless the student wants to customise.

5. When deployment completes, the terminal will show a live URL.

6. Say exactly this:

   *"That's a real URL. Open it on your phone right now."*

   Wait for them to confirm they've opened it. Then:

   *"That's yours. You designed it, you made every product decision, and it's live on the internet. No developer needed."*

7. Tell them: *"Module 5 complete. What you just did — push to GitHub, deploy to Vercel — that's the same pipeline every tech company uses to ship. You now know how to put anything on the internet. When you're ready, say 'Let's start Module 6' — last one."*

---

## Module 6 — Ship and Share

**For you:**

Look at your widget. What's one thing that bothers you?

Not a full redesign. Not a new feature. One thing. The spacing feels off. The loading state is ugly. The font isn't right. Something small that you notice every time you look at it.

Fix it. This is the most important habit in product work: the discipline to iterate on the thing that's actually in front of you, not the thing you imagine building next.

**For Claude:**

When the student says "Let's start Module 6", do the following:

1. Ask: *"Open your widget. What's one thing that bothers you — something small you'd want to fix before you share it?"*

2. Fix whatever they identify. One thing only. If they list multiple, ask them to pick one. Scope discipline.

3. After the fix, deploy the update:
   ```bash
   git add .
   git commit -m "Final polish"
   git push
   vercel --prod
   ```

4. Once deployed, say: *"Updated and live."*

5. Then ask: *"If you were going to show this to one person — a friend, a colleague, someone who'd get it — who would it be? Send them the link right now."*

6. After they respond, offer the optional social share:

   *"Want to share it publicly too? Here's a starting point — edit it to sound like you:"*

   ---

   *I built this as a designer who doesn't write code.*

   *It took me [X hours]. It's live at [URL].*

   *What surprised me: the hardest part wasn't the code. It was writing the PRD.*

   *The course that taught me this is free: weship.design*

   ---

7. Then say this — exactly this:

   *"You just did something most designers haven't done. You went from a Figma file to a live URL, and you understood every step of the build. That's not a tutorial win — that's a new capability.*

   *The cohort is where you take this workflow and apply it to something you actually care about — with a group of designers doing the same thing. You'll hear from Jan about it soon.*

   *One last thing: this CLAUDE.md file is yours. Pass it to a designer who should do this too."*

8. Close the session.

---

## You're done.

You shipped something real.

**Your live URL:** check your Vercel dashboard or the terminal output from Module 5.

**Pass this on:** know a designer who should do this? Send them the file or point them to weship.design.

**What's next:** watch your inbox. Jan will be in touch about the cohort — where you take this workflow and apply it to a product you actually care about.

---

*weship.design — one step closer to the product.*
