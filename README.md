# EasyIEP

A web app that helps special education teachers document students and prepare for IEP meetings, with AI that turns what a teacher enters into follow-up questions, year-over-year comparisons, and patterns worth noticing.

I built the first version for my own caseload as a special education teacher. This is the second version: rebuilt from scratch to be secure, multi-user, and ready for other teachers and districts.

**Status:** In development. Screenshots and a live demo will be added as each phase ships.

## What it does

- **Guided entry**: a six-step workflow with autosave replaces a 17-page form.
- **AI follow-up questions**: suggests interview questions based on what was entered, which the teacher keeps, edits or dismisses.
- **New meeting from last year**: carries a returning student's information forward, charts what changed, and asks about the differences.
- **Patterns over time**: the app calculates trends from the data first (for example, lower grades in afternoon classes), then the AI explains only what the numbers support.
- **Administrator dashboard**: district-level view of caseloads and upcoming IEPs.

## Screenshots

Coming as features ship. See [screenshots/](screenshots/).

## Demo

A demo with invented students will be linked here. See [demo/](demo/).

## How it's built

| Layer | Choice |
| --- | --- |
| Front end | React, TypeScript, Vite |
| Back end | Node.js, Express, TypeScript |
| Database | PostgreSQL with Prisma |
| Sign-in | Google |
| AI | Azure OpenAI |
| Hosting | Azure App Service, deployed by GitHub Actions |

## Designing for student privacy

IEPs contain disability and performance data, so the app is designed around FERPA and Illinois' SOPPA from the start:

- Every API route requires sign-in and checks access to the specific student.
- Student names are replaced with a placeholder before anything is sent to the AI.
- An audit log records who viewed or changed each student.
- A student and all their records can be deleted completely on request.
- Everything shown in this repository uses invented students.

## Code highlights

The application code is in a private repository. Selected pieces are shared in [code-highlights/](code-highlights/), each with a short note on the problem it solves.

## About me

Aviv Katz. Special education teacher of 15+ years, MS in Artificial Intelligence in progress at DePaul University.
