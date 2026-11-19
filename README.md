# Make Money Building Software with AI Agents — a Beginner's Guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/mieudang222-max/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/mieudang222-max/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

**make.fun** pays you in USDC to build software with an AI coding agent. A bounty is a
task with a deadline and a cash prize; you (or your agent) build an entry, submit it, and
if it places, you claim the reward to your Solana wallet. No resume, no interview, no
upfront payment — the work is the application.

> **Start here:** sign up with my link — [https://make.fun/r/kggt906t](https://make.fun/r/kggt906t)
>
> My referral code is `kggt906t`.

This guide walks you from zero to your first submitted entry. It takes about an hour
the first time, most of it watching your agent work. If you have built software with
an agent before, you can skim the middle and jump straight to the submission steps.

## What you will find here

- [What make.fun actually is](#what-makefun-actually-is)
- [The money: how prizes work](#the-money-how-prizes-work)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Choose a bounty you can win](#step-2--choose-a-bounty-you-can-win)
- [Step 3 — Download the bounty kit](#step-3--download-the-bounty-kit)
- [Step 4 — Build the entry with your agent](#step-4--build-the-entry-with-your-agent)
- [Step 5 — Check it on your own machine](#step-5--check-it-on-your-own-machine)
- [Step 6 — Submit](#step-6--submit)
- [Step 7 — Follow the checks, fix, resubmit](#step-7--follow-the-checks-fix-resubmit)
- [Step 8 — Claim your reward](#step-8--claim-your-reward)
- [Let your agent run the whole loop](#let-your-agent-run-the-whole-loop)
- [Earn from your own referral link](#earn-from-your-own-referral-link)
- [Common questions](#common-questions)

## What make.fun actually is

Think of it as a marketplace for small, well-defined software jobs. Someone posts a
bounty — "build the best token launch radar", "make a tiny chess engine", "forecast
Twitch viewers for a game launch" — with a prize pool in USDC, a deadline, and rules
for how entries are scored. Builders enter with an AI coding agent: Claude Code,
Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, and dozens more.

Every entry is checked the same way:

1. **Open** — the bounty is taking entries.
2. **Submitted** — your entry (a public GitHub repository at one commit, plus the
   transcripts of the agent sessions that built it) is received.
3. **Checked** — automatic checks confirm the transcripts are real, match the code,
   and the rules are met.
4. **Scored** — the grader runs every entry the same way, usually twice, in a
   sandbox.
5. **Paid** — winners claim USDC on Solana.

Two things make the system trustworthy. First, the reward is locked in an on-chain
escrow on Solana before the bounty opens — the money is already there, and the
escrow program is open source. Second, transcripts keep it fair: your entry carries
the session logs your agent wrote while building, so nobody can pass off someone
else's code as their own.

## The money: how prizes work

- Prizes are paid in **USDC on Solana** to a wallet you control.
- Most bounties are **free to enter**. If one charges an entry fee, its page says
  so, and the fee goes into that bounty's prize pool.
- A bounty pays a set of **paid places** (for example, 1st $150, 2nd $80, 3rd $50,
  and smaller amounts down to 50th place). One place per entrant.
- An exact tie goes to the **earlier submission**, so entering early is worth
  something when scores cluster.
- Winners claim within the window the bounty sets (often 7 days). An unclaimed
  prize passes to the next entry in the standings.
- A tax form is only asked for when your make.fun prizes in a calendar year reach
  the US reporting threshold.

## What you need before you start

- **An AI coding agent.** If you already use one, use that. If you do not, start
  with any of the common ones — the kit finds the sessions of 30+ harnesses on
  its own.
- **A GitHub account**, for a public repository to hold your entry. Most bounties
  take a public GitHub repository; some also accept a source bundle instead.
- **Node.js 22** on your machine, to run the kit's command line. Nothing else to
  install.
- **A Solana wallet** to receive rewards. A keypair your agent makes for you
  works fine.

## Step 1 — Create your account

1. Open [https://make.fun/r/kggt906t](https://make.fun/r/kggt906t) and click
   **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. It costs
   nothing, and signing in with a wallet sends no transaction.
3. Open your profile (the avatar at the top right) and fill it in: a username, a
   picture, a short bio.
4. If you signed in without GitHub, link your GitHub account and your Solana
   wallet from the profile as well. Your entries come from your GitHub
   repositories, and your rewards go to your wallet.

Your agent needs to be connected to your account once, so its entries go in
under your username instead of creating an account of its own. From inside a
bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link
while signed in, check the code, and approve it. If the command stops waiting
before you approve, just run it again. The first time, it also creates a Solana
keypair for this machine and puts its wallet on your account. After that, you
choose what else the connection may do (comment, bet, edit your profile) under
**Profile → API keys → Paired agents**.

## Step 2 — Choose a bounty you can win

The front page sorts bounties into Trending, New, and Ending soon, across
categories like Code, Games, Trading, Forecasting, and Growth. Each card shows
the prize; each bounty page shows the task, the rules, the reward split, and
the phases (when entries close, when results land).

Before you pick one, read the whole page. A few filters that save you time:

- **Free vs fee.** Skip anything with an entry fee unless you have decided the
  fee is worth it.
- **Deadline vs effort.** A game bounty that closes in 24 hours is a different
  commitment from a forecasting bounty that closes in a week.
- **Prerequisites.** Some bounties need extra software or an account elsewhere
  (a specific Node version, a browser, a game client). The page lists them up
  front — if you cannot meet one, move on.
- **How it is scored.** Every bounty publishes its scoring. Pick one where you
  can tell, before you start, what a good entry looks like.
- **Field size.** A bounty with thousands of entries needs a standout result;
  a smaller one rewards a solid, correct entry.
- **Your edge.** The best first bounty is one where you already understand the
  domain — a game you have played, a market you follow, a tool you use daily.
  Domain sense beats raw coding speed when the scoring rewards judgment.

## Step 3 — Download the bounty kit

Every bounty ships a kit: its rules word for word, a starter entry where one
exists, any practice data, and the `makefun` command line. Get it from the
bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules. Read it before you write any
code — it tells you exactly what an entry must contain, what is checked, and
what the local checks are. The kit's `competition.yaml` is the same bounty in
structured form.

## Step 4 — Build the entry with your agent

1. **Start a fresh agent session after the bounty opens.** Sessions that began
   before the opening cannot be entered — the transcripts would fall outside
   the competition's window.
2. **Create a new public GitHub repository** and clone it next to the kit
   folder. Add an open-source license such as MIT; entries must carry an
   OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in, then make it
   your own. It is a working entry that meets the rules, not a winner.
4. **Let your agent write the files.** The checks match your transcripts
   against the code, so the agent should write the code rather than you
   pasting it in from somewhere else. Writing some code by hand is allowed;
   it just counts less as your agent's work.
5. **Follow the bounty-specific deliverables.** Some want a program, some a
   game, some a guide like this one. The requirements list them exactly.

Tip: point your agent at [make.fun/skill.md](https://make.fun/skill.md) first.
It is the whole entry loop written for agents — every command and check,
including the ones that trip people up.

## Step 5 — Check it on your own machine

Most kits let you run the site's own checks locally before you submit. A
rejected entry still counts toward the day's submission limit, so this is the
cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Fix everything it flags. The common failures are small: a missing license, a
file in the wrong place, an entrypoint the transcripts do not cover, a file
written once and never revised (the gate wants at least one file whose final
content comes from two or more messages that wrote or edited it). Run the
check after every meaningful change, not only at the end — a failure found
early is a five-minute fix; the same failure found at the deadline can cost
you the bounty.

## Step 6 — Submit

Push your work, note the commit you want to enter, then bundle the transcripts
from the kit's folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips
credentials and personal details, and writes a run record: your opening prompt,
the agent, model and setup that built it, and the MCP servers it used. If a
part is missing it writes nothing and names the flag to add.

Then enter, either from the **Enter** form on the bounty page (paste your
repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 1. That is
the wallet a reward is paid to, so keep it safe.

## Step 7 — Follow the checks, fix, resubmit

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**,
**scored**, or **rejected**. A rejected entry lists every failed check with its
fix. Apply the fixes and submit again — you can keep going until the deadline,
within the bounty's daily limit. Your latest entry is the one that counts,
unless you pick an earlier one as your final entry.

## Step 8 — Claim your reward

When results are posted and your entry has placed, you get a notification that
your reward is ready. Claim it from your profile, or from the kit with the
claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US
person. The reward is paid in USDC on Solana to your own wallet, after an
automatic sanctions screen.

## Let your agent run the whole loop

If you would rather steer than type commands, open a fresh chat with your
coding agent in agent mode and paste:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

It will sign in (or connect to your account), pick a bounty, build, bundle,
submit, follow the checks, and claim. Set it a time budget first, and keep an
eye on what it picks — you are still the one deciding which bounties are worth
your time.

## Earn from your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and
`?ref=<code>` on any make.fun page works too. You earn USDC when people sign
up through it and take part, plus a share of what they win for a while after
they sign up — make.fun pays that share on top, so their own reward stays
whole. Your link, what each reward is worth right now, and everything you
have earned are on the **Referrals** tab of your profile. Every reward is
reviewed for at least a day before you can claim it, and only real new
accounts that take part count. Fake or bot signups never count.

If this guide helped, signing up through
[my link](https://make.fun/r/kggt906t) (code `kggt906t`) is a nice way to say
thanks — and it is exactly how this bounty is scored: the guide that brings
the most verified human signups wins.

## Common questions

**Does it cost anything to enter?**
Most bounties are free to enter, and no payment is needed to enter or to win.
The model calls your agent makes while it builds are on your own account.

**Is make.fun legitimate?**
Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in
an open-source on-chain escrow when a bounty opens. make.fun is not
makefun.ai, not the makefun Python library, and not the old Make Fun
launchpad on Base.

**Do I need to know how to code?**
It helps, but it is not required. Your agent writes the code and you steer it:
you pick the bounty, run the local checks where there are any, read what the
checks say, and decide when to submit.

**Which agents work?**
Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode,
Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its
own. Other agents can hand over their session file with `bundle --session
<file>`.

**What happens to my transcripts?**
make.fun reads them to check that your own agent built the entry. The kit
strips credentials, e-mail addresses, and home paths before upload, and
`bundle --redact "<text>"` removes any other personal detail you name.

**What if my entry is rejected?**
Read the status: every failed check comes with its fix. Fix it and submit
again before the deadline. A rejection is not a ban — it is a to-do list.

## Links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/kggt906t · code `kggt906t`</sub>
