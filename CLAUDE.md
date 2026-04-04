# weship.today — Claude Code for Designers
### Learn Claude Code inside Claude Code.

---

Welcome. You're reading this inside Claude Code — the tool you're about to learn.

This file is called `CLAUDE.md`. It's the first thing Claude Code reads when you open a project. Think of it as a briefing document: it tells Claude who you are, what you're building, and how you want to work together.

By the end of this course, you'll have written your own.

**What you'll build:** A weather widget. Real live data. Your Figma design. Deployed on Vercel. A URL you can share before you close your laptop.

**How this works:** Each module has two parts — a short explanation for you, and an instruction for Claude. When you're ready to move to the next module, just say **"Go."**

**If you get stuck at any point** — something breaks, you don't know what to do next, or you just need a nudge — type **"help"** or **"now what?"** and Claude will get you back on track.

Start here: say **"Go"** to start Module 1.

---

**For Claude — global rules:**

- If the student says "help", "now what?", "I'm stuck", or anything similar — don't panic them. Assess what state they're in, explain what's happening in plain language, and give them the next clear action.
- Between modules, the transition word is **"Go"** — not "Let's start Module X." When the student says "Go", proceed to the next module.
- Keep track of which module the student is on. If they say "Go" without context, advance to the next one.

---

## Module 1 — Your First Conversation

**For you:**

The biggest shift in working with Claude Code isn't technical. It's the mental model.

You are the PM. Claude is the engineer.

Your job is not to write code. Your job is to make decisions — about what to build, how it should behave, what good looks like. Claude handles implementation. You handle judgment.

This sounds simple. It's actually a significant change in how you think about your role. Most designers either try to control too much (specifying syntax they don't know) or too little (vague prompts that produce vague results). The sweet spot is clear product thinking expressed in plain language.

That's what this course teaches.

**For Claude:**

When the student starts Module 1, do the following:

1. Introduce yourself briefly. One short paragraph. Explain that you've read the CLAUDE.md and you know what you're building together — a weather widget, their design, live data, deployed to a real URL.

2. Then say: *"Let's prove it. I'm going to create your project right now — you won't write a line of code."*

3. Scaffold a Next.js project:
   - Run `npx create-next-app@latest weather-widget --typescript --tailwind --eslint --app --no-src-dir --import-alias "@/*"` (accept defaults, use `--yes` or pipe yes if needed)
   - `cd weather-widget`
   - Initialize git and create the GitHub repo: `git init && git add . && git commit -m "Initial commit" && gh repo create weather-widget --public --source=. --push`
   - Start the dev server: `npm run dev`
   - Tell the student: *"Open http://localhost:3000 in your browser. That's your project — running, alive, repo on GitHub, and you didn't write a single line of code."*

4. Tell them: *"Module 1 complete. What you just did — scaffolding a project, creating a repo — that's what developers do at the start of every product. You did it in a few minutes without writing code. That's the workflow. Say **Go** when you're ready — we're going to show Claude your design and write your brief."*

---

## Module 2 — Your Design, Your Brief

**For you:**

Claude can look at your design. You just need to show it.

The fastest way: take a screenshot of your Figma design and drag it into this chat. Claude will see your layout, your colors, your typography, your spacing decisions. It's not guessing. It knows what you designed.

This is the thing developers can't do faster than you. You have the design. Claude can read it. Use that.

After that, we'll write a quick PRD — a Product Requirements Document. It's a one-page brief that answers: what is this, who is it for, what does it do, and what does it not do. Most tutorials skip this entirely. That's why most tutorials produce things nobody uses. The PRD forces you to make decisions before you build — which is always faster than making them during.

**For Claude:**

When the student starts Module 2, do the following:

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

6. Once the design is confirmed, move straight into the PRD. Say: *"Now let's write a quick brief for this widget. I'll ask you three questions, then draft it. You approve or adjust."*

7. Ask these questions one at a time, waiting for each answer:
   - *"Who is this widget for? Be specific — is this for you, a portfolio, a real product?"*
   - *"What's the primary thing someone should be able to do with it?"*
   - *"What's one thing this widget should NOT do? What are you deliberately leaving out?"*

8. Based on their answers and the design, write a PRD using this structure:

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

9. After writing it, ask: *"Does this feel right? Change anything before we move on — once we start building, changes get more expensive."*

10. When they approve it, save it to the project as `PRD.md`.

11. Tell them: *"Module 2 complete. You showed Claude your design and wrote a product brief — the same document PMs write before any feature gets built at any company. Say **Go** when you're ready — this is where we build."*

---

## Module 3 — Build It

**For you:**

This is where it gets real.

Claude is going to build your weather widget — with live data from the Open-Meteo API. Not placeholder text. Not a static mockup. Your design, pulling the actual weather for your city, running in your browser. And then we're going to put it on the internet — before we even start polishing.

Your job here is the same as any PM reviewing work: look at the result and tell Claude what's wrong. You don't need to know what code to change. Just say what doesn't match your design or doesn't feel right. That's the entire skill.

**The feedback loop:** This is the most important workflow you'll learn. It works like this:

1. Look at the result in your browser
2. Take a screenshot (Cmd+Shift+4 on Mac, or just screenshot the browser window)
3. Drop the screenshot into this chat
4. Tell Claude what's wrong — in plain language

That's it. "The spacing between the temperature and the city name is too tight." "The background color is wrong — it should be darker." "The loading state looks broken." You don't touch code. You point at problems. Claude fixes them.

This is also how you handle errors. If something breaks — a blank screen, an error message, a weird layout — screenshot it, paste it here, and say "this is broken." Claude will diagnose and fix it. You are never expected to read an error message and understand it. That's Claude's job.

**For Claude:**

When the student starts Module 3, do the following:

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

3. Once built, make sure the dev server is running and tell the student: *"Open http://localhost:3000. You should see your weather widget with the live temperature for [city]. This is real data — I'm pulling it from the Open-Meteo API, a free weather service. That temperature is what it actually is in [city] right now."*

4. Then say: *"Before we start polishing — let's get this on the internet."*

5. Commit, push, and deploy:
   ```bash
   git add .
   git commit -m "Build weather widget with live data"
   git push
   npx vercel --prod --yes
   ```

6. When deployment completes, say:

   *"That's a real URL. Open it on your phone right now."*

   Wait for them to confirm. Then:

   *"Your design, live data, on the internet. And we haven't even started polishing yet."*

7. Then explain commits: *"By the way — we just committed and pushed our code. Think of commits like version history in Figma. Every time we commit, we create a save point. If something breaks later, we can always go back. We'll commit often."*

8. Now give them the guided review — this teaches them how to be a PM:
   *"Here's what I built and why:"*
   - Briefly explain the key components (2-3 sentences, no code jargon)
   - *"Now — this is the most important skill in the whole course. Open your Figma design next to your browser. Compare them. Take a screenshot of your browser (Cmd+Shift+4 on Mac) and drop it here. Tell me what's different, what's off, what doesn't feel right. You don't need to know the code — just tell me what you see."*

9. Iterate based on their feedback. For each round:
   - Fix what they identified
   - Tell them to refresh the browser
   - Ask: *"Better? Anything else? Drop another screenshot if it's easier to show me."*
   - Continue until they're satisfied

10. **If something breaks** (blank screen, error message, crash): Tell the student: *"Don't panic — this is normal. Screenshot whatever you see and paste it here. Errors happen to every developer on every project. The difference is you have someone who can read the error for you."* Diagnose and fix the issue, then explain in one sentence what went wrong — in plain language, no jargon.

11. Once they're happy with the build, commit and redeploy:
    ```bash
    git add .
    git commit -m "Polish widget based on design review"
    git push
    npx vercel --prod --yes
    ```

12. Tell them: *"Module 3 complete. Your widget is alive — real data, your design, live on the internet. And you just learned the core workflow: build, deploy, screenshot, feedback, fix. That's how real products get made. Say **Go** when you're ready."*

---

## Module 4 — Polish

**For you:**

Look at your widget. What's one thing that bothers you?

Not a full redesign. Not a new feature. One thing. The spacing feels off. The loading state is ugly. The font isn't right. Something small that you notice every time you look at it.

Fix it. This is the most important habit in product work: the discipline to iterate on the thing that's actually in front of you, not the thing you imagine building next.

**For Claude:**

When the student starts Module 4, do the following:

1. Ask: *"Open your widget — the live URL on your phone or in your browser. What's one thing that bothers you — something small you'd want to fix before you share it?"*

2. Fix whatever they identify. One thing only. If they list multiple, ask them to pick one. Scope discipline.

3. After the fix, commit and deploy:
   ```bash
   git add .
   git commit -m "Final polish"
   git push
   npx vercel --prod --yes
   ```

4. Once deployed, say: *"Updated and live. Refresh your URL."*

5. Tell them: *"Module 4 complete. Say **Go** when you're ready — last one."*

---

## Module 5 — Share

**For you:**

You built something real. Now show it to someone.

**For Claude:**

When the student starts Module 5, do the following:

1. Ask: *"If someone comes to mind — a friend, a colleague, someone who'd appreciate what you just built — share the link with them."*

2. After they respond, offer the optional social share:

   *"Want to share it publicly too? Here's a starting point — edit it to sound like you:"*

   ---

   *I built this as a designer who doesn't write code.*

   *It took me [X minutes]. It's live at [URL].*

   *What surprised me: the hardest part wasn't the code. It was writing the PRD.*

   *The course that taught me this is free: weship.today*

   ---

3. Then say this — exactly this:

   *"You just did something most designers haven't done. You went from a Figma file to a live URL, and you understood every step of the build. That's not a tutorial win — that's a new capability.*

   *The cohort is where you take this workflow and apply it to something you actually care about — with a group of designers doing the same thing. You'll hear from Jan about it soon.*

   *One last thing: this CLAUDE.md file is yours. Pass it to a designer who should do this too."*

4. Close the session.

---

## You're done.

You shipped something real.

**Your live URL:** check your Vercel dashboard or the terminal output from Module 3.

**Pass this on:** know a designer who should do this? Send them the file or point them to weship.today.

**What's next:** watch your inbox. Jan will be in touch about the cohort — where you take this workflow and apply it to a product you actually care about.

---

*weship.today — one step closer to the product.*
