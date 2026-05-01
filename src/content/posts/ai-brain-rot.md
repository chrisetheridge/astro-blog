---
title: "AI and brain rot"
description: "A reflection on using AI without outsourcing the parts of engineering that matter the most."
date: 2026-04-30
---

Like many engineers, I've been using AI a lot more in my day-to-day engineering work: writing code, debugging issues, learning new concepts, and exploring new features. AI has become an integral part of my toolkit.

AI is genuinely useful, at least to me. It is probably the biggest shift in productivity I've experienced in a long time.

However, my increased usage of AI tooling started to bother me.

By "AI brain rot", I mean the gradual erosion of engineering judgment through underuse.

# AI for coding

I didn't start feeling uncomfortable because of coding. For me, coding has rarely been the hardest part of engineering. Once you've learned two or three languages, actually writing code becomes pretty straightforward.

In my workflow, AI has removed a lot of the need to handwrite code from scratch. I'm completely comfortable with that. With strict guidance and careful review, I'm also comfortable with the outputs.

# System design

What really concerned me was outsourcing the part of my job that only I can really do: system design and architecture.

Understanding a problem, defining the flows involved, reasoning through tradeoffs, and designing a scalable solution are what separates an engineer from a coder.

I also find these parts of engineering genuinely fun. It is extremely satisfying to take a problem, explore options, decide on a solution, and see it work. This is where I get all of my engineering dopamine from.

Unfortunately, AI makes it easy to jump straight to a solution. Without being intentional about designing solutions, you start accepting agent outputs without doing any critical thinking of your own.

Currently, I'm calling this "AI brain rot". If you don't stress your system design muscles, they slowly erode.

# Brain rot

Brain rot sounds very dramatic, but I think it fits.

You have a problem. You ask the model to help with the problem. It gives you a reasonable solution. You skim it, maybe tweak one or two lines, and move on.

You're still productive, and for some people, you're still getting dopamine from shipping a feature. But you've skipped essential parts of designing technical solutions:

- Problem definition: turning vague requirements into clear system requirements
- Identifying key constraints
- Breaking systems into their components with clear boundaries
- Reasoning through tradeoffs
- Understanding and catering for failure modes
- Estimating how the system could evolve over time

Working through these points is integral to designing systems that are reliable, scalable, and easy to maintain.

# "Just turn the AI off"

The obvious reaction to all of this is to just turn off AI tooling. I don't want to do that, and I don't think it's realistic either. AI is already very useful, and it's going to continue to improve.

I want the agent to do the stuff I find boring: handwriting code. I still want to do the exciting stuff: solving problems and designing solutions.

Instead of turning the AI off, I started thinking about a different approach.

**What if the tool forced me to think before helping me?**

# Adding friction in the right place

I ended up building an extension for the Pi agent, as well as a skill for other harnesses. It forces the user to work through designing a solution before writing any code. You do not get to skip the design phase.

When I issue a task like "build an email system", which is intentionally vague because my prompts are often more detailed, the agent does not immediately start grepping code and writing functions. It interrupts the flow of work and starts asking me questions.

First, through Socratic questioning, it asks me to define:

- The problem
- The core flow
- The constraints involved
- The components involved
- Areas of uncertainty or difficulty

For example, with "build an email system", it might ask:

- Who sends the emails?
- Are they transactional, bulk, or both?
- What delivery guarantees matter?
- What should happen if the provider is down?
- Do we need auditing, retries, templates, rate limits, unsubscribe handling, or dead-lettering?
- What parts of the system need to be observable?
- How should this evolve if volume increases by 10x?

Once I've answered all of the questions, the model critiques my plan. This forces me to iterate on an approach before any code is written.

Only after all of this does the model give me two or three approaches. I can also provide my own if I'm not satisfied with the approaches it provides. Only once I accept an approach does the agent get to start writing code.

# Why this works for me

I was falling into the trap of ask -> receive -> accept. At times, I would put very little effort into thinking about the problem. I wasn't being challenged enough.

Now, I have to put in effort when asking for an implementation. I have to engage my brain and really work through the request before I get the output. I feel this is much healthier for both me and the codebase.

I've essentially baked system design reps into my daily workflow. This doesn't replace learning system design through books or courses, but it does force me to practice it daily.

# Still work to do

I don't think I've nailed this problem yet, and it's entirely possible I never will. Too much friction and I may just turn the extension off. Too little friction and it doesn't change anything.

The goal is not less AI. The goal is to preserve the part of engineering I actually want to keep practicing.

This may be a valid case where [we should just slow down](https://mariozechner.at/posts/2026-03-25-thoughts-on-slowing-the-fuck-down/), and I'd be pretty okay with that too.