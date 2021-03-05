---
layout: default
title: Automated Feedback
parent: Technical Details
---

# Automated Feedback
{: .no_toc }
## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview
Project repositories include two “code bots” that give immediate and actionable feedback to students. One checks for logic and output formatting errors, and the other checks for style and syntax errors. This happens automatically each time a student submits their program. 

The bots interact with the students in the **Feedback** conversation that is automatically generated in the **pull requests** tab. They don’t just inform the student there are errors, they walk them though how to fix them. Learn more in this video:

- <iframe width="373" height="210" src="https://www.youtube.com/embed/gdc-SYhRFCM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Syntax/Style Bot

The **Syntax/Style bot** is an app that is uploaded to Heroku and installed as a webhook in the CS-1400 GitHub Organization. The bot's GitHub account is also added as a collaborator to the organization. 
- In the **webhooks** section  of the **settings** tab oin CS-1400 GitHub organization is where all the hook details are. You can open and inspect the <a href='https://github.com/organizations/CS-1030/settings/hooks/282625978'  target="_blank">webhook management page</a> if you are an admin on the organization. 

## Logic/Output Bot

The **Logic/Output bot** is created in the automation code stored on each repository (`.github/workflows/workflow.yml`). This bot requires no installation or additional accounts in the organization.

## Bot Independence

Each bot works independently of the other. You can remove the Logic/Output Bot from an assignment if needed:
1. Open `.github/workflows/workflow.yml` file in the assignment template
2. Find and delete these these lines of code from the file:
  - <script src="https://gist.github.com/RuizTheRuler/a2573326c4568a091399681f0ddfc1d3.js"></script>
