# Free Bug Bounty Vetting

## Check the submission gate first

- Read the program page and the platform submission rules before you read any contract code.

- Record the join rule, the submission fee or credit cost, the verification step, the payout rule and the deadline in your notes.

- Treat a program as blocked when joining needs KYC that is not done or when submission needs paid credits that the user has not approved.

- Park a blocked program and move to the next program instead of starting a deep audit on it.

- Verify the logged-in program panel before you start a deep audit and treat the panel as authoritative when it differs from the public program page.

- Ask the user for a screenshot of the program panel when the panel needs a login you do not have, and record the fee, the reputation requirement, the program status and the deadline exactly as the panel shows them.

- Recheck the gate after a profile change because a reputation update can take time to appear in the panel.

## Check the account gate before a deep audit

- Check the account status on the platform before you audit, including any risk flag, verification state and credit balance.

- Treat an account level block as a program block, even when the program page itself looks open.

- Ask the user before you buy credits, pay a fee, create a paid account or complete KYC for a submission.

- Record the date you checked the account gate beside the program name so a later audit can see that the check is fresh.

## Audit only what can be submitted

- Audit a program only after its submission gate and its account gate both pass or after the user has approved the cost to clear them.

- Check the scope, the known issue list and the duplicate rule before you spend time on a finding.

- Stop the audit when a finding falls outside scope or matches a known acknowledged issue and record why it cannot be submitted.

- Keep a proof of concept only for a finding that passes the scope check and the gate check together.

## Run the pre-submit check on each finding

- Read the program not-a-bug list and its SECURITY.md for each finding before you draft its submission, record that it matches no entry or quote the entry it matches, and stop the submission when it matches.

- Screen the finding against findings already submitted and against the public findings list before you draft its submission, and treat the finding as a duplicate when the screen leaves doubt.

- Check the live panel again at submission time because a program can close or add a fee after the audit.

## Report the gate result with the finding

- Report the gate check, the scope check and the finding together so the user can see that the finding has a live submission route.

- Name the submission route in the report, such as a free platform form, a free email address or a paid platform that needs approval.

- State the fee, the KYC step and the deadline for the chosen route in the same report.

- Say plainly when a finding is real but unsubmittable and what would need to change before it could be submitted.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Websites

- [Immunefi](https://immunefi.com/) for program scope and submission rules. Carry the program name into the lookup and verify the fee, the verification step and the account status before you audit.

- [Cantina](https://cantina.xyz/) for program scope and join rules. Carry the program name into the lookup and verify whether joining needs KYC before you audit.

- [HackenProof](https://hackenproof.com/) for program scope and submission rules. Carry the program name into the lookup and verify the fee and the KYC step before you audit.

## Alternatives for better results

- Prefer a free submission route such as a free platform form or a direct email route when the same scope is open on more than one platform.

- Reuse a gate check from the same day for the same platform instead of repeating the full check for every program on that platform.

- Recheck a parked program only after the user approves the cost or after the platform changes its gate, and record the new check date when you do.
