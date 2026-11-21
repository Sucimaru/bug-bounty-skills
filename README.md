# Bug Bounty Skills

A collection of bug bounty and security-audit playbooks (skills) for AI coding agents.
Each skill is a self-contained folder with a `SKILL.md` playbook plus its
`references/` and `scripts/` where applicable. Copy the skills you need into
your agent — no build step, no install.

These playbooks were written from real hunting experience: web2 and web3
audits, triage and validation, report writing, and submission-gate vetting.
They are generic on purpose — no personal accounts, wallets, or program
details are included.

## Skills

| Skill | What it does |
|---|---|
| `bug-bounty` | Master workflow: recon → learn → hunt → validate → report. Vuln checklists (IDOR, SSRF, XSS, auth bypass, race conditions, SQLi, GraphQL, CI/CD, LLM/agent security), A→B bug chaining, tool catalogue. |
| `bb-methodology` | Hunting methodology and mindset: the 5-phase non-linear workflow, developer-psychology framework, session discipline, wide/deep route selection, tool routing by phase. Start here. |
| `web2-recon` | Web2 recon pipeline: subdomain enumeration, live-host discovery, URL crawling, JS analysis (secrets, endpoints), directory fuzzing, continuous monitoring setup. |
| `web2-vuln-classes` | 26 web2 bug classes in depth: SSRF, race conditions, SQLi, XSS, IDOR/BOLA, auth/OAuth, cache poisoning, request smuggling, LLM prompt injection, and more — each with detection, bypass tables, and PoC patterns. |
| `web3-audit` | Smart contract audit: 10 DeFi bug classes (accounting desync, access control, oracle, ERC4626, reentrancy, flash loan, signature replay, proxy), pre-dive kill signals, Foundry PoC template, grep patterns. |
| `bsc-contract-audit` | Evidence-based due-diligence audit for BNB Smart Chain token contracts, NFT mints, and deposit-refund escrows. 100-point scoring rubric with a GO / CAUTION / BLOCK verdict. Includes RPC probe scripts. |
| `launch-curve-audit` | Audit for token launch curves on BSC (bonding curve / tranche IEO / escrowed pre-launch sale): price-path modelling, lifecycle invariants, adversarial order book, graduation and LP custody. Includes curve-math and snapshot scripts. |
| `meme-coin-audit` | Meme coin and token security audit: rug-pull detection (honeypot, hidden mint, fee manipulation, LP lock bypass), Solana SPL / Token-2022 authority risks, DEX liquidity-pool attacks. |
| `amm_pool_price_valuation` | Value a token holding from AMM pair reserves: verify both token decimals on-chain before dividing, cross-check against an executable swap quote and DexScreener. Prevents 1000x-style decimal misreads. |
| `security-arsenal` | Payload and bypass cheat-sheet: SSRF, SQLi, IDOR, JWT, OAuth, NoSQLi, XSS, and cloud-metadata techniques in one reference file. |
| `triage-validation` | Finding validation before writing any report: the 7-Question Gate, 4 pre-submission gates, never-submit list, CVSS 3.1 quick reference, severity decision guide. Run this before every report. |
| `free_bug_bounty_vetting` | Vet a bug bounty submission gate before a deep audit: submission fee, KYC/verification step, payout rule, live-panel check, not-a-bug list, and duplicate screen — so time goes only to submittable findings. |
| `report-writing` | Bug bounty report writing for HackerOne / Bugcrowd / Intigriti / Immunefi: templates, impact-first writing, CVSS 3.1 and 4.0 scoring, title formula, severity guide, downgrade counters, pre-submit checklist. |

## How to install

Each skill is one folder. Copy the folder(s) you want into your agent's
skills directory, then restart/reload the agent if it requires it.

```bash
git clone https://github.com/Sucimaru/bug-bounty-skills.git
# example: Claude Code
cp -r bug-bounty-skills/bug-bounty ~/.claude/skills/
cp -r bug-bounty-skills/web3-audit ~/.claude/skills/
# other agents: copy into whatever directory your agent loads skills from
```

A suggested starter set for a full hunt: `bb-methodology`, `bug-bounty`,
`web2-recon`, `web2-vuln-classes`, `triage-validation`, `report-writing`
(web2) — plus `web3-audit` and `bsc-contract-audit` for smart contracts.

## Notes

- Some skills reference a local `bughunter/tools/` helper toolset and a few
  slash-commands (`/recon`, `/validate`, `/report`) that are **not** included
  in this repo. The skills still work standalone as playbooks — the tool
  references are optional conveniences, not requirements.
- `bsc-contract-audit` and `launch-curve-audit` were originally written as
  community skills for the Binance skills hub and are not affiliated with or
  endorsed by Binance or Anthropic.
- The skills contain public, well-known contract addresses (e.g. PancakeSwap
  factory/router, WBNB) and example payloads only. No credentials, private
  keys, personal accounts, or program-specific data are included.

## License

MIT — see [LICENSE](LICENSE).
