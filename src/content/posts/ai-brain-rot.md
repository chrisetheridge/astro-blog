---
title: "Testing"
description: "Test"
date: 2026-04-30
---

Like many engineers, I've been using AI a lot more in my day-to-day engineering work. Writing code, debugging issues, learning new concepts, exploring new features. AI has become an integral part of my toolkit.

AI is genuinely useful (at least to me), it is probably the biggest shift in productivity I've experienced in a long time.

However, my increased usage of AI tooling started to bother me.

# AI for coding

I didn't start feeling uncomfortable because of coding. Coding has never been the difficult part of engineering. Once you've learned 2-3 languages, then actually writing code becomes pretty straightforward.

AI has almost completely removed the need to handwrite code (in my opinion). I'm completely comfortable with this, and with strict guidance, I'm complete comfortable with the outputs.

# System design

What really concerned me was outsourcing the part of my job that only I can really do - system design and architecture. Understanding a problem, defining the flows involved, reasoning through tradeoffs, and designing a scalable solution. These practices are what separates an engineer from a coder.

I also find these parts of engineering genuinely fun. It is extremely satisfying to take a problem, explore options, decide on a solution, and see it work. This is where I get all of my engineering-dopamine from.

Unfortunately, AI makes it easy to jump straight to a solution. Without being intentional about designing solutions, you start accepting agent solutions without doing any critical thinking of your own.

Currently I'm calling this "AI brainrot". If you don't stress your system design muscles they will slowly erode.

# Brain rot

Brain rot sounds very dramatic but I think it fits:

You have a problem. You ask the model to help with the problem. It gives you a reasonable solution. You skim it, maybe tweak 1-2 lines, and move on.

You're still productive, and for some people you're still getting dopamine of shipping a feature. But you've skipped essential parts in designing technical solutions:
- Problem definition - turning vague requirements into clear system requirements
- Identifying key constraints
- Breaking systems into their components with clear boundaries
- Reasoning through tradeoffs
- Understanding and catering for failure modes
- Estimating how the system could evolve over time

Working through these points are integral in designing systems that are reliable and easy to maintain.

# "Just turn the AI off"

The obvious reaction to all of this is to just turn off AI tooling. I don't want to do that, and I don't think its realistic either. AI is already very useful, and its going to continue to improve.

I want the agent to do the stuff I find boring - handwriting code. I still want to do the exciting stuff - solving problems, designing solutions.

Instead of turning the AI off, I started thinking about a different approach. **What if the tool forced me to think before helping me?**

# Adding friction in the right place

I ended up building an extension for the Pi agent, as well as a skill for other harnesses. It forces the user to work through designing a solution before writing any code. You do not get to skip the design phase.

When I issue a task like "build an email system" (intentionally vague, my prompts are often more detailed), the agent does not immediately start grepping code and writing functions. It stops the flow of work, and starts asking me questions.

First, through socratic questioning, it asks me to define:
- The problem
- The core flow
- Constraints involved
- Components involved
- Possibly areas of uncertainty or difficulty

Once I've answered all of the questions, the model then critiques my plan. This forces me to iterate on an approach before any code is written.

Only after all of this, does the model give me 2-3 approaches. I can also provide my own if I'm not satisfied the the approaches it provided. Once I accept an approach only then does the agent get to start writing code.

# Why this works for me

I was falling into the trap of ask -> receive -> accept. At times I would put very little effort into thinking about the problem. I wasn't being challenged enough.

Now, I have to put in effort when asking for an implementation. I have to engage my brain and really work through the request before I get the output. I feel this is much healthier for both me and the codebase.

I've essentially baked in system design reps into my daily workflow. This doesn't replace learning system design via books or courses, but it does force me to practice it daily.

# Still work to do

I don't think I've nailed this problem yet, and its entirely possible I never will. Too much friction and I may just turn the extension off. Too little friction and it doesn't change anything.

This may be a valid case where [we should just slow down](https://mariozechner.at/posts/2026-03-25-thoughts-on-slowing-the-fuck-down/), and I'd be pretty okay with that too.