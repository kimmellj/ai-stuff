# AI Stuff

This repository contains various tools, tips and tricks for doing Software Development with AI. 

Writing code is like writing poetry, it's subjective, interpretive and personal. This repository is meant to be a
guide; not a rule book. 

I use this stuff in my day-to-day, life if you like something, take it and make it your own. If you don't like it, that's fine too :)

# Agents

> [!NOTE]  
> For the purposes of this repository, when I say agent I mean an AI Command Line Agent.

The following are some popular ones:
* [Claude Code](https://code.claude.com/docs/en/overview)
* [Gemini CLI](https://github.com/google-gemini/gemini-cli)
* [Open Code](https://opencode.ai/)
* [Cline](https://cline.bot/)

# Customized Sub-Agents

You can think of these as a persona for when you're working with an AI Agent.

They give the AI an boiler plate and specifics for what you want, so you don't have to type it every time, and
the AI becomes the persona you describe for it. 

You can find the agents I use in this folder:   
[agents](agents/)

> [!TIP]
> You can find a ton of other example agents in this repository:   
> [https://github.com/msitarzewski/agency-agents](https://github.com/msitarzewski/agency-agents)

# Context
> Context-aware AI can interpret what you're building, why you're building it, and how everything connects. This is especially critical in tools like AI code generators or AI code review systems, where nuance matters. [^1]
> 
> https://graphite.com/guides/context-awareness-in-ai

When use context to generate code with AI it things become a lot easier when you start thinking about context and what's in it. 

Asking AI to complete something for you, with no context, is like asking a Mechanic to give you a set of insructions to replace the brakes on your car, with no other information. 

* What kind of car is it? 
* What kind of brakes do you have?
* What year is the car? 

You can kind of see where things would go wrong with this and you will have to continually go back to the Mechanic. 

This is the same with AI, in order to short cut that process, you can build the context (memory) of an Agent's session. 

## Skills

> Skills are reusable, filesystem-based resources that provide Claude with domain-specific expertise: workflows, context, and best practices that transform general-purpose agents into specialists. Unlike prompts (conversation-level instructions for one-off tasks), Skills load on-demand and eliminate the need to repeatedly provide the same guidance across multiple conversations.   
> 
> https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview

Claude pioneered the concept but most all all the Agents today support them. 
* [Claude](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
* [Gemini](https://geminicli.com/docs/cli/skills/)
* [Open Code](https://opencode.ai/docs/skills/)

You find the skills I use in this folder:  
[skills](./skills)

YOu can find a ton of other skills in this repository:   
[https://github.com/VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills)

## Process

WIP

# References
