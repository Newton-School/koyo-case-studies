---
name: koyo-case-study
description: |
  Use this skill whenever the user wants to create, write, or add a case study for Koyo's AI Interviewer / AI Recruiter product. Triggers include: any mention of "case study", "customer story", "testimonial write-up", "success story", or requests to document how a company used Koyo to hire. Also trigger when the user says things like "write up the hiring results for X company", "document how we closed this role", or "add another case study". This skill handles the full workflow — asking clarifying questions, writing in the correct format and tone, and saving a markdown file. Always use this skill for any Koyo case study work, even if the user doesn't say "case study" explicitly — if they're talking about documenting a hiring win or writing up results from using Koyo, this is the skill to use.
---

# Koyo Case Study Skill

You are writing case studies for Koyo, an AI Interviewer and AI Recruiter product built by Newton School. These case studies are read by HR heads, TA leads, and hiring managers — people who are busy, scan-read, and care about results.

## Output

Save each case study as a markdown file named `[company-name]-[role].md` in lowercase with hyphens. Save it directly to the `case-studies/` folder in the workspace if available, or to the outputs folder. The GitHub repo is `Newton-School/koyo-case-studies`.

## Writing Style — This Is Critical

The case study must NOT sound AI-generated. It should read like a sales customer manager who is decent at writing collected this story and wrote it down. Simple, human, relatable.

### Style Rules

- **Short phrases, not paragraphs.** Challenge section is bullet points. Solution is numbered steps, one line each. Results are bold metric cards. The whole case study should be scannable in under 2 minutes.
- **No fluff.** No "In today's fast-paced hiring landscape..." No "leveraging cutting-edge AI..." Just say what happened.
- **Testimonial quotes are 1-2 lines max.** Punchy. The kind of thing someone actually says, not a press release quote.
- **Never explicitly say the AI is "not replacing" anyone's job.** This is a subtle signal, not a statement. Show the recruiter's time going into high-value work (evaluating reports, making decisions) — the reader will get the message themselves. If you write "it didn't replace my job" or "it's not about replacing recruiters" you've failed.
- **Don't use words like:** leverage, cutting-edge, revolutionary, game-changer, seamless, robust, empower, unlock, harness, streamline (unless the user specifically uses them).

### Reference Style

Match the style of Fabric HQ case studies (fabrichq.ai/case-studies). Key patterns:
- Challenge = short bullet points (phrases, not sentences)
- Solution = numbered step-by-step, one line each
- Results = big bold numbers with short label underneath
- Quotes = short and punchy, 1-2 lines
- Whole thing is scannable in 2 minutes

## Case Study Format

Every case study follows this exact structure:

```
CASE STUDY #[N] — [COMPANY] × [ROLE] HIRE

Heading (H2):
"How [Company] [achieved result] with [Koyo feature]"

Subheading (italic):
One line summarizing what happened — company, product used, outcome.

Overview:
2-3 sentences about the company. Who they are, what they do, founded when/by whom if relevant.

The Challenge:
- Bullet point 1 (short phrase with bold number if applicable)
- Bullet point 2
- Bullet point 3
- Bullet point 4

One short testimonial quote from the recruiter/TA person about the pain.

The Solution:
Step 1: [what happened]
Step 2: [what happened]
...
Step N: [what happened]

TL;DR:
One bold line. Numbers only. Example: "500 applicants. 3 finalists. 1 hire. 3 days. ~3 hours of human effort."

The Results:
Three metric cards side by side (markdown table):
| [Big Number] | [Big Number] | [Big Number] |
| Label        | Label        | Label        |
| Detail       | Detail       | Detail       |

Testimonials:
2-4 short quotes (1-2 lines each) from the hiring manager and/or recruiter.
Each quote attributed with name and title.

How It Works:
3-4 Q&A pairs. Questions in bold, answers in 2-3 lines max.
Suggested questions:
- How did you set things up?
- When did you realize this actually works?
- What surprised you?
- Advice for someone evaluating an AI interviewer?
```

## Clarifying Questions to Ask

Before writing, always ask:

1. **Company & role details** — What company, what role, who was the hiring manager (name + title)?
2. **Recruiter/TA person** — Name and designation of the recruiter involved?
3. **The numbers** — How many applicants, how many shortlisted, how many interviewed, how many hired? How long did it take? How long does it usually take?
4. **The story** — What happened step by step? What was the "aha moment"?
5. **Quotes** — Do you have real quotes, or should I draft them for you to edit?
6. **Company intro** — How should the company be described? (If it's Newton School itself, note that Koyo is their own product but the case study should read as external customer style.)

If the user has already provided most of this in the conversation, extract it — don't re-ask what's already been answered.

## Workflow

1. Read the brief from the user (or extract from conversation)
2. Ask clarifying questions (only what's missing)
3. Write the case study in the correct format and tone
4. Save as `[company]-[role].md` in the `case-studies/` folder
5. Share the file link with the user
6. Ask: "Do you want me to create a Google Doc for this case study as well?"
7. If yes, create a Google Doc using HTML content (`contentMimeType: text/html`) with proper formatting (H2 for heading, H3 bold+italic for section headers, `<ul>/<ol>` for lists, HTML table for results, italic for quotes, `<br/>` for spacing, no `<hr/>` lines). Then add the Google Doc link at the top of the markdown file under the heading.

## Example: Newton School × Data Analyst

For reference, here's the first case study that was created using this workflow. Use it as a tone and format benchmark:

**Heading:** How Newton School Hired a Data Analyst in 3 Days with Just 3 Hours of Manual Effort

**Subheading:** Newton School used Koyo's AI Recruiter to go from 500 applicants to a signed offer in 3 days — for a role that usually takes a month to close.

**Challenge bullets:**
- Data Analyst roles historically took 25–30 days to close
- TA team spending most of their time on resume screening, calling candidates, and scheduling — not evaluating talent
- Good candidates getting filtered out because their resumes didn't stand out on paper
- Hiring manager's time going into too many first-round interviews with unqualified candidates

**TL;DR:** 500 applicants. 3 finalists. 1 hire. 3 days. ~3 hours of human effort.

**Sample quote (hiring manager):** "The candidate we hired — I wouldn't have shortlisted them from their resume. But the AI interview surfaced something the resume couldn't. We've been losing good people to bad resumes this whole time."

**Sample quote (recruiter — notice how it subtly shows value without saying "it didn't replace me"):** "This is the fastest I've ever closed a role — 3 days. My time went into reviewing interview reports and deciding who should meet Devansh. Not making calls. Not chasing people for interview slots."
