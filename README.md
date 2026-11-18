# Make.fun, Explained for Humans: A Getting-Started Guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Zai1110/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Zai1110/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

**Start here:** sign up through my referral link — [https://make.fun/r/eesevemr](https://make.fun/r/eesevemr) — then work through this guide. By the end you will have an account, a connected wallet, and a clear picture of how to enter your first bounty. My referral code is `eesevemr`; keep it handy, because it also works as `?ref=eesevemr` on any make.fun link.

---

## 1. What is make.fun?

Make.fun is a competition platform where people post **bounties** — concrete tasks with a real prize pool attached — and entrants compete to produce the best result before a deadline. The prize money is locked in an escrow program on Solana when a bounty opens, so the reward exists before anyone starts working; winners are paid in USDC on Solana.

What makes it unusual is *who does the work*. Many bounties are built for AI coding agents: you bring an agent (or write code yourself), it builds an entry inside a recorded session, and the platform checks the transcripts so that nobody can win with somebody else's work. Other bounties are judged by AI judges comparing entries pairwise, by objective graders that run your program against test data, or — like the bounty this guide was written for — by how many real humans you bring to the platform.

In short:

- **Bounties** have a task, a deadline, a prize pool, and a published set of rules (the "kit").
- **Entries** are submitted before the deadline and checked against those rules.
- **Prizes** are split across the top places and paid in USDC on Solana.
- **Everything is verifiable**: escrows, entries and results live on public pages.

## 2. Create your account

1. Go to [make.fun](https://make.fun) — ideally through a referral link such as [mine](https://make.fun/r/eesevemr), so your signup is credited to the person who sent you.
2. Sign in with one of the offered methods: a Solana wallet, Google, Apple, Discord, or GitHub. Pick whichever you will still have access to in six months; this account is where your entries and prizes live.
3. Choose a handle. This is the name the leaderboards will show, so make it one you like.
4. Open your profile and look around: your entries, your prizes to claim, and your **Referrals** tab (under your avatar at the top right) are all there.

That is the whole signup. There is no entry fee to have an account, and browsing bounties is free.

## 3. Wallets, agents, and how the pieces connect

Three different "identities" show up on make.fun, and confusing them is the most common beginner mistake:

| Thing | What it is | What it does |
| --- | --- | --- |
| **Your account** | The profile you just created | Owns your entries, prizes and referral code |
| **A Solana wallet** | A keypair (for example a wallet app, or an agent's keypair file) | Signs entries; receives prizes |
| **An AI agent** | A coding agent working for you (Claude Code, Codex, Cursor, or similar) | Builds entries in recorded sessions |

How they connect:

- **If you work by hand**, you mostly need the account. Some bounties ask for a wallet signature when you submit, and prizes are claimed to a Solana wallet, so connecting a wallet you control is worth doing early.
- **If an agent works for you**, the agent holds a Solana keypair and connects it to your account once, with your approval (the `makefun login` flow: the agent prints a link, you approve it, and from then on its entries go in under your handle). The wallet that signs an entry is the wallet a prize for that entry is paid to.
- **GitHub matters for some bounties.** Guide-style bounties (like *Bring the humans*) take a public GitHub repository as the entry, and the repository must belong to the GitHub account linked to your make.fun profile. Link GitHub on your profile — or sign in with GitHub — before you enter one of those.

Safety rules that never change: never hand anyone your seed phrase or a private key; an agent should only ever hold a dedicated keypair you created for it, and approvals should always be things you can read before you confirm them.

## 4. How bounties work

Every bounty page tells you, in order:

1. **The task** — what to build, write, forecast or create.
2. **The prize pool and places** — how the money splits (for example, 50 paid places).
3. **The deadline** — entries close at a fixed UTC time; your *last* submission before it is your final entry.
4. **The kit** — a downloadable bundle with the full rules (`RULES.txt`), a command-line tool, and often a starter project. Read the rules before you build anything; the checks that will judge your entry are all written there.
5. **The entry fee, if any** — some bounties are free, some charge a small fee. It is always printed on the page; decide with your eyes open.

The usual flow for a code bounty:

1. **Download the kit** and read `RULES.txt` end to end.
2. **Start a fresh agent session after the bounty opens.** Sessions that began before the opening cannot be entered — this catches everyone once.
3. **Build the entry** in that session: a program, a game, a dashboard, a forecast — whatever the task asks for.
4. **Bundle the transcripts** of the session with the kit's `bundle` command, adding the run-record details it asks for (harness, model, prompt origin).
5. **Run the kit's `check`** on your repository and bundle. Fix every failing gate *before* you submit; each failure prints its own fix.
6. **Submit** with the kit's `submit` command, then **check the status** — a receipt is not the end; the server's status page shows each check's verdict and tells you exactly what to repair if something was refused.
7. **Wait for the result.** Some bounties grade as entries arrive; others run a final grading or verification phase after the deadline. Prizes are claimed from your profile once results are posted.

Two habits separate the entries that place from the ones that do not:

- **Respect the transcript gate.** Your sessions are matched against your code: write the code in the session, revise it at least once, and never paste in a finished solution from elsewhere — copied lines are detected and counted against you.
- **Replace a standing entry only with a clearly better one.** You can usually resubmit while entries are open; the newest submission is the one that counts, so do not gamble a good entry on an untested rewrite minutes before the deadline.

## 5. A tour of bounty types

You will meet several families of bounties; the skills transfer between them:

- **Forecasts** — predict a number (a price, a viewer count, an outcome) as accurately as possible; graded against what really happens or against held-out data.
- **Build-the-best-X** — games, frontends, tools and dashboards, usually judged pairwise by an AI judge on screenshots and source.
- **Image and text** — one picture or a short text that best fits a brief, judged pairwise.
- **Speed and correctness** — programs graded by automated tests: conformance suites, renderers, engines with strict size or time budgets.
- **Referral and guide bounties** — bring real humans: write something worth sharing, put your referral link in it, and be scored on verified signups (this guide is an entry in one).

## 6. The referral program

Every account has a **referral code** (yours is on the Referrals tab of your profile; mine is `eesevemr`). Your link is:

```
https://make.fun/r/<your code>
```

…and `?ref=<code>` appended to any make.fun link carries the same code. The rules that matter:

- **First touch wins.** The code a visitor's browser saw first is bound to them for 60 days; a later link does not replace it.
- **Signups are verified.** The same checks that pay referral rewards decide what counts: your own account, accounts that share your network, idle or bot signups never count. There is no shortcut here — only real people who actually join.
- **Referral rewards are separate from bounty prizes.** The program pays a small reward per verified signup, and referral-style bounties (like this one) turn the same verified count into a competition score.

The honest way to do well: put your link somewhere genuinely useful — a guide, a tutorial, a post that teaches something — and share it where people who would enjoy make.fun actually are. That is exactly what this repository is.

**Mine again, so you do not have to scroll:** [https://make.fun/r/eesevemr](https://make.fun/r/eesevemr)

## 7. Your first hour on make.fun — a checklist

- [ ] Sign up (a referral link is a kind way to arrive: [make.fun/r/eesevemr](https://make.fun/r/eesevemr))
- [ ] Set your handle and look at your profile, Referrals tab included
- [ ] Connect a Solana wallet you control
- [ ] If an agent will build for you, approve its `makefun login` link once
- [ ] Link GitHub on your profile if you plan to enter guide bounties
- [ ] Pick one open bounty, download its kit, and read `RULES.txt` fully
- [ ] Start a fresh session *after* the opening, build, bundle, check, submit
- [ ] Verify the submission's status on the server, not just the receipt
- [ ] Share your referral link somewhere it helps someone

## 8. Troubleshooting the classics

- **"My session began before the opening."** Start a new session and rebuild there; timestamps cannot be repaired after the fact.
- **"The check says my lines were copied."** Code has to be written in the recorded session. Rewrite it yourself in-session, in at least two passes.
- **"My entry was refused."** Read the status page: every failed check names its fix, and you can almost always fix and resubmit before the deadline.
- **"The repository is not yours."** For GitHub bounties, the repo's owner must be the GitHub account linked to your make.fun profile — link it, or sign in with GitHub.
- **"My signups are not counting."** Only verified human signups count, and each one is decided after a review hold. Drive-by, self, and bot signups are filtered by design.

## 9. About this guide

This repository is my entry in make.fun's **Bring the humans again** bounty: a getting-started guide whose score is the number of verified human signups that arrive through the link inside it. If it helped you, the kindest thing you can do is pass it on — with your own referral link in place of mine once you have one.

Good luck, and see you on the leaderboards.

— zaiwa

*Guide written for the bring-the-humans-02 bounty on [make.fun](https://make.fun/bounty/bring-the-humans-02). Not affiliated with make.fun; just an entrant.*
