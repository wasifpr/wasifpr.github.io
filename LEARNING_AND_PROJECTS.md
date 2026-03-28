# Mohammed Wasif — Learning Roadmap & Project Specs

---

## PART 1: LEARN THE TECH BEHIND THIS PORTFOLIO

Everything used to build wasifpr.github.io, where to learn each, and how long it takes.

---

### 1. HTML (HyperText Markup Language)
**What it does in this project:** Structure of every section — headings, paragraphs, images, forms, navigation, semantic tags.
**Time to learn:** 1-2 weeks
**Free resources:**
- [MDN Web Docs — HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics) — the gold standard reference
- [freeCodeCamp — Responsive Web Design](https://www.freecodecamp.org/learn/2022/responsive-web-design/) — hands-on exercises
- [W3Schools HTML Tutorial](https://www.w3schools.com/html/) — quick reference with live editor

**What to focus on:**
- Semantic elements: `<header>`, `<nav>`, `<section>`, `<article>`, `<footer>`
- Forms: `<form>`, `<input>`, `<textarea>`, `<label>`, `<button>`
- Images: `<img>`, `alt` attributes, `srcset` for responsive
- Links: `<a>`, anchor links (`#section-id`)
- Meta tags: `<meta>` for SEO and Open Graph

---

### 2. CSS (Cascading Style Sheets)
**What it does in this project:** All visual styling — colours, layout, typography, animations, dark mode, responsive breakpoints, the hero reveal mask.
**Time to learn:** 2-4 weeks
**Free resources:**
- [MDN CSS — First Steps](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)
- [CSS Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Tricks — A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Kevin Powell YouTube](https://www.youtube.com/@KevinPowell) — best CSS teacher on the internet
- [freeCodeCamp CSS course](https://www.freecodecamp.org/learn/2022/responsive-web-design/)

**What to focus on (used in this portfolio):**
- **Flexbox** — used for nav, hero layout, skill rows, footer
- **CSS Grid** — used for about gallery, cert cards, contact form
- **CSS Custom Properties (variables)** — `--clr-dark`, `--clr-light`, etc.
- **`clamp()`** — responsive font sizing without media queries
- **Media queries** — `@media (max-width: 640px)` for mobile
- **Transitions & animations** — `transition`, `@keyframes`, `animation`
- **`mask-image`** — the hero B&W → colour reveal effect
- **`backdrop-filter: blur()`** — the frosted glass sticky header
- **BEM naming** — `.block__element--modifier` pattern used throughout

---

### 3. JavaScript (Vanilla JS)
**What it does in this project:** Hero cursor reveal (canvas + mask), gallery slider, scroll animations, form AJAX submission, sticky header show/hide.
**Time to learn:** 3-6 weeks
**Free resources:**
- [JavaScript.info](https://javascript.info/) — the most complete free JS course
- [freeCodeCamp — JavaScript Algorithms](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/)
- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [Wes Bos — JavaScript30](https://javascript30.com/) — 30 free projects in 30 days (highly recommended)
- [Traversy Media YouTube](https://www.youtube.com/@TraversyMedia)

**What to focus on (used in this portfolio):**
- **DOM manipulation** — `getElementById`, `querySelector`, `classList`
- **Event listeners** — `click`, `pointermove`, `pointerenter`, `scroll`, `submit`
- **Canvas API** — `getContext('2d')`, `createRadialGradient`, `toDataURL()`
- **IntersectionObserver** — scroll-triggered animations
- **Fetch API** — AJAX form submission (`fetch()` with `FormData`)
- **localStorage** — saving user preferences (dark mode)
- **requestAnimationFrame** — smooth animation loops
- **IIFE pattern** — `(function() { ... })()` to avoid global scope pollution

---

### 4. Git & GitHub
**What it does in this project:** Version control, hosting via GitHub Pages.
**Time to learn:** 1 week
**Free resources:**
- [Git Handbook — GitHub Docs](https://docs.github.com/en/get-started/using-git/about-git)
- [freeCodeCamp — Git for Beginners](https://www.freecodecamp.org/news/git-and-github-for-beginners/)
- [Learn Git Branching](https://learngitbranching.js.org/) — interactive visual tutorial

**Commands used in this project:**
```
git init                    # Start a repo
git add -A                  # Stage all files
git commit -m "message"     # Save a snapshot
git remote add origin URL   # Connect to GitHub
git push -u origin main     # Upload to GitHub
git pull origin main        # Download latest changes
```

---

### 5. Google Fonts
**What it does:** Loads Bebas Neue (headings) and Inter (body) fonts.
**Learn:** [Google Fonts — Getting Started](https://developers.google.com/fonts/docs/getting_started)
**Time:** 30 minutes

---

### 6. SVG (Scalable Vector Graphics)
**What it does:** The circular rotating text around the portrait.
**Learn:** [MDN SVG Tutorial](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial)
**Focus on:** `<svg>`, `<path>`, `<text>`, `<textPath>`
**Time:** 1-2 hours

---

### 7. Formspree
**What it does:** Receives form submissions and emails them to you.
**Learn:** [Formspree Docs](https://formspree.io/docs/)
**Time:** 15 minutes

---

### Recommended Learning Order
1. HTML (week 1-2)
2. CSS (week 2-4) — do Flexbox and Grid first
3. JavaScript (week 4-8) — start with DOM, then events, then Canvas
4. Git & GitHub (can learn in parallel any time)
5. Build a small project after each topic to practice

---

## PART 2: THE 4 GITHUB PROJECTS (Detailed Specs)

These are the projects from your Career Action Plan. Each one is designed to demonstrate real skills to hiring managers.

---

### PROJECT 1: AI-Powered FAQ Bot
**Repo name:** `ai-faq-bot`
**Goal:** Show you can integrate LLMs into a real product workflow.
**Time:** 1-2 weeks

#### What it does
A chatbot that answers questions about a product (or company) using OpenAI's API and a knowledge base you provide. Users type a question, the bot searches your knowledge base, and returns an AI-generated answer.

#### Tech stack
- **Python 3.10+**
- **OpenAI API** (or Google Gemini API — your choice)
- **Streamlit** — for the web UI (simple, no frontend needed)
- **A text file or JSON** — your knowledge base (product docs, FAQs, etc.)

#### File structure
```
ai-faq-bot/
├── app.py              # Main Streamlit app
├── knowledge_base.json # Your FAQ data (questions + answers)
├── bot.py              # OpenAI API logic — takes question, searches KB, returns answer
├── requirements.txt    # Python dependencies
├── .env.example        # Template for API key (never commit real keys)
├── README.md           # Project docs
└── screenshots/        # Screenshots for README
    └── demo.png
```

#### How app.py works (pseudocode)
```
1. Load knowledge base from JSON
2. Show a text input: "Ask me anything about [Product]"
3. When user submits a question:
   a. Search knowledge base for relevant entries
   b. Send the question + relevant context to OpenAI API
   c. Display the AI-generated answer
4. Show conversation history
```

#### README should include
- **Problem:** "Support teams answer the same 50 questions repeatedly"
- **Solution:** "AI bot trained on product docs that handles L1 queries instantly"
- **How to run:** Step-by-step setup instructions
- **Screenshot:** The working app in a browser
- **Architecture:** Simple diagram showing: User → Streamlit UI → Python → OpenAI API → Response
- **What I learned:** Brief reflection

#### Knowledge base example (knowledge_base.json)
```json
[
  {
    "question": "What are your working hours?",
    "answer": "Our offices are open Sunday to Thursday, 9 AM to 6 PM GST."
  },
  {
    "question": "How do I reset my password?",
    "answer": "Go to Settings > Security > Reset Password. You'll receive an email with a reset link."
  },
  {
    "question": "How do I submit a support ticket?",
    "answer": "Email support@company.com or use the Help Desk portal at helpdesk.company.com."
  }
]
```

---

### PROJECT 2: Smart Dashboard with AI Insights
**Repo name:** `ai-dashboard`
**Goal:** Show data + AI + product thinking. Directly maps to your JCDecaux dashboard work.
**Time:** 1-2 weeks

#### What it does
A dashboard that connects to a database (SQLite for demo), shows KPIs with charts, and uses AI to generate written summaries of trends — like a human analyst would.

#### Tech stack
- **Python 3.10+**
- **Streamlit** or **Dash** (by Plotly) — for the dashboard UI
- **SQLite** — lightweight database (no server needed)
- **Pandas** — data manipulation
- **Plotly** — interactive charts
- **OpenAI API** — to generate trend summaries in plain English

#### File structure
```
ai-dashboard/
├── app.py              # Main dashboard app
├── data/
│   ├── seed_data.py    # Script to generate sample data
│   └── sample.db       # SQLite database with demo data
├── ai_insights.py      # OpenAI-powered trend analysis
├── requirements.txt
├── .env.example
├── README.md
└── screenshots/
    ├── dashboard.png
    └── ai-insight.png
```

#### Sample data schema
```sql
CREATE TABLE sales (
    id INTEGER PRIMARY KEY,
    date DATE,
    region TEXT,          -- 'UAE', 'KSA', 'Egypt', etc.
    product TEXT,         -- 'Digital Billboard', 'Bus Shelter', etc.
    revenue REAL,
    units_sold INTEGER
);
```

#### Dashboard sections
1. **KPI cards** at the top: Total Revenue, Units Sold, Top Region, Growth %
2. **Line chart:** Revenue over time (monthly)
3. **Bar chart:** Revenue by region
4. **Pie chart:** Revenue by product type
5. **AI Insight box:** "Based on the data, [region] showed a 23% increase in Q4, driven primarily by [product]. Consider allocating more inventory to this market."

#### README should include
- **Before vs After:** "Before: team spent 3 hours creating manual Excel reports. After: real-time dashboard with AI-written summaries"
- **Screenshot:** The dashboard with charts and AI insight
- **How to run:** `pip install -r requirements.txt && python app.py`
- **Sample data included** so anyone can run it immediately

---

### PROJECT 3: Prompt Engineering Playbook
**Repo name:** `prompt-engineering-playbook`
**Goal:** Show practical AI expertise through documented, tested prompts. No deep coding needed — PMs and AI leads love this.
**Time:** 1 week

#### What it does
A curated, documented collection of prompts you've engineered for real work scenarios. Each prompt includes the use case, the prompt template, example input/output, and tips.

#### File structure
```
prompt-engineering-playbook/
├── README.md                    # Overview + table of contents
├── prompts/
│   ├── customer-support/
│   │   ├── ticket-categorizer.md
│   │   ├── response-generator.md
│   │   └── escalation-detector.md
│   ├── data-analysis/
│   │   ├── sql-generator.md
│   │   ├── report-summarizer.md
│   │   └── anomaly-explainer.md
│   ├── product-management/
│   │   ├── prd-writer.md
│   │   ├── user-story-generator.md
│   │   └── feature-prioritizer.md
│   └── training/
│       ├── quiz-generator.md
│       ├── guide-writer.md
│       └── onboarding-checklist.md
└── templates/
    └── prompt-template.md       # Blank template for adding new prompts
```

#### Prompt document format (each .md file)
```markdown
# Ticket Categorizer

## Use Case
Automatically categorize incoming support tickets into: Bug, Feature Request, How-To, or Billing.

## Prompt Template
"""
You are a support ticket classifier. Categorize the following ticket into exactly one category: Bug, Feature Request, How-To, or Billing.

Ticket: {{ticket_text}}

Respond with only the category name.
"""

## Example Input
"I can't log into the dashboard since the update yesterday. It shows a 500 error."

## Example Output
"Bug"

## Tips
- Add "Respond with only the category name" to prevent verbose answers
- For multi-label classification, change to "one or more categories"
- Works with GPT-4, GPT-3.5, and Gemini Pro
```

#### README should include
- Total number of prompts
- Categories with brief descriptions
- "How to use" — copy the prompt, replace {{variables}}, paste into your AI tool
- "How to contribute" — template for adding new prompts

---

### PROJECT 4: AI-Assisted PRD Template
**Repo name:** `ai-prd-template`
**Goal:** Show you think like a Product Manager. Includes a real PRD template + a Python script that auto-generates PRD sections from a brief description.
**Time:** 1 week

#### What it does
1. A Markdown PRD template with all standard PM sections
2. 1-2 filled examples based on real work (anonymized)
3. A Python script that takes a one-line product idea and generates a draft PRD using AI

#### File structure
```
ai-prd-template/
├── README.md
├── templates/
│   └── prd-template.md          # Blank PRD template
├── examples/
│   ├── dashboard-prd.md         # Filled example: internal dashboard tool
│   └── training-platform-prd.md # Filled example: training platform
├── generator/
│   ├── generate_prd.py          # Python script — AI-powered PRD writer
│   └── requirements.txt
└── screenshots/
    └── generated-prd.png
```

#### PRD template sections
```markdown
# Product Requirements Document

## 1. Problem Statement
What problem are we solving? Who has this problem? How painful is it?

## 2. Target Users
Primary users, secondary users, personas.

## 3. Goals & Success Metrics
What does success look like? KPIs to measure.

## 4. Proposed Solution
High-level description of what we're building.

## 5. Features & Requirements
### Must-have (P0)
### Should-have (P1)
### Nice-to-have (P2)

## 6. AI / Automation Components
Where does AI add value? What model/API? Fallback if AI fails?

## 7. Technical Considerations
Dependencies, integrations, data requirements.

## 8. Timeline & Milestones
Phase 1, Phase 2, etc.

## 9. Risks & Mitigations
What could go wrong? How do we handle it?

## 10. Open Questions
Things still to be decided.
```

#### Generator script (generate_prd.py) pseudocode
```
1. Ask user: "Describe your product idea in one sentence"
2. Send to OpenAI: "Generate a detailed PRD using this template: [template] for this idea: [user input]"
3. Save output as a new .md file
4. Print: "PRD saved to output/my-prd.md"
```

#### README should include
- What a PRD is and why it matters
- The template (linked)
- Filled examples (linked)
- How to run the generator
- Screenshot of a generated PRD

---

## PART 3: RECOMMENDED LEARNING PATH (Combined)

### Month 1: Foundations
- Week 1-2: HTML + CSS basics (freeCodeCamp)
- Week 3-4: JavaScript basics (JavaScript.info + Wes Bos JS30)
- Parallel: Git basics (Learn Git Branching)

### Month 2: Build & Apply
- Week 5: Build Project 3 (Prompt Engineering Playbook) — easiest, no coding
- Week 6: Learn Python basics if needed ([Automate the Boring Stuff](https://automatetheboringstuff.com/) — free)
- Week 7-8: Build Project 1 (AI FAQ Bot)

### Month 3: Level Up
- Week 9-10: Build Project 2 (AI Dashboard)
- Week 11: Build Project 4 (PRD Template)
- Week 12: Polish all READMEs, add screenshots, publish

### Ongoing
- Google PM Certificate on Coursera (do 30 min/day alongside everything else)
- DeepLearning.AI "AI for Everyone" (finish in 1 weekend)

---

*Follow this roadmap and in 3 months you'll have a portfolio site, 4 GitHub projects, 
and the knowledge to talk about all of it confidently in any interview.*
