---
title: "CMD on Autopilot:"
seoTitle: "AI commad line decoder"
seoDescription: "decode english text to command line using AI"
datePublished: Sat Jul 27 2024 11:49:26 GMT+0000 (Coordinated Universal Time)
cuid: clz42jlst00150al403n0edrn
slug: cmd-on-autopilot
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1722080819159/e7e017ab-e2d1-41a4-881d-29a0b6c8873b.png
tags: hackathon, ai, python, google, aifortomorrow

---

**About:**

If you often forget command line commands, then this might interest you.

Presenting CMD on autopilot. Perform tasks in the command line just by using simple English text. The program targets the Git Bash command line to convert natural language into Git Bash commands. Utilizing the power of the Gemini API and caching, it boosts your productivity.

Learn Git Bash commands along with automation. It saves your command line history, which persists even after the program has exited, so you can revisit them in the future.

The caching technique helps you reduce the load on the Gemini API for similar commands, thereby saving resources and time.

**GitHub:**

[GitHub repo](https://github.com/Kaku-g/cmd-decoder/tree/main) for reference.

How to run the program:

* Clone the file to your local system using `git clone`.
    
* Install Python and other dependencies using `pip install -q -U google-generativeai`.
    
* Generate your API key from Gemini.
    
* Run `python gemini.py` to start the program.
    

**Additional Commands:**

Use `exit` to terminate the program.

Use `history` to view command line history.

**Demo:**

%[https://youtu.be/I_QOvxgINxU] 

**Features:**

* Uses caching if the command is already generated.
    
* History to view all previous commands.
    
* Lightweight Python file.
    

**License:**

The codebase is open-sourced under the MIT license. All contributions are welcome. Raise PRs for existing bugs or new functionality.

*Part of Hashnode's AI for Tomorrow Hackathon.*