# ⚠️ Disclaimer & Liability Limitation

**Use at your own risk.** The code, workflows, and scripts in this repository (`n8n-hubspot-owner-deactivation-lead-reassignment-sentinel`) are provided for educational and architectural demonstration purposes.

## No Liability

The author and dhRobin Systems accept no responsibility or liability for any direct, indirect, incidental, or consequential damages that result from using, misusing, or deploying these scripts. That includes, without limitation:

- deals, contacts or tasks reassigned to the wrong owner, reassigned too early or too late, or not reassigned at all;
- lost or delayed revenue, missed follow-ups, customer dissatisfaction or commission disputes arising from record ownership changes;
- owner deactivations that were misdetected, including accidental, temporary or bulk deactivations;
- record ownership changes that could not be reversed, or reversed only in part;
- employee or customer data exposed in Slack, webhooks or n8n execution data;
- API quota consumption, rate limiting or account restrictions imposed by HubSpot or Slack.

## No Warranty

All software, n8n JSON blueprints, JavaScript modules and prompts are provided "AS IS", without warranty of any kind, express or implied. This includes, but is not limited to, warranties of merchantability, fitness for a particular purpose, and non-infringement.

The deactivation signal, open-record filters, routing rules, grace period and mass-deactivation guard are heuristics. They don't replace an agreed hand-over process. HubSpot API responses, endpoints, fields, scopes and settings URLs change over time, and I make no warranty that they match what this workflow expects.

## Production Testing Required

Always test thoroughly in an isolated staging environment, such as a HubSpot developer test account or sandbox, with `SANDBOX_MODE=true`, `DRY_RUN=true`, `REASSIGNMENT_ENABLED=false` and `SEND_SLACK_ALERTS=false` enabled, before you connect live HubSpot or Slack credentials.

Before enabling writes:

- agree the coverage mapping, team pools, fallback owner and exclusions with sales leadership;
- review a dry run against your real deactivated owners and confirm every planned target;
- create the previous-owner property if you plan to use it, and test rollback on a few records;
- start with a low `MAX_REASSIGNMENTS_PER_RUN`;
- unpin every node you expect to run live.

Treat the coverage mapping as a business decision that a person owns, and every automatic reassignment as a change that a person may need to review.

## Third-Party APIs & Compliance

You alone are responsible for complying with the terms of service, rate limits, data privacy regulations (GDPR/CCPA), and security policies of HubSpot, Slack and any connected services. That includes:

- handling employee deactivation data in line with HR, works council and privacy policies;
- confirming that receiving reps are entitled to the customer data in the records they're given, including regional and data residency rules;
- checking that HubSpot permissions let receiving reps work the reassigned records;
- securing every access token and webhook URL;
- keeping the run summaries as an audit trail as your change-management policy requires;
- reviewing every automatically reassigned record.

## License

Released under the MIT License. Copyright (c) 2026 DH Robin (dhRobin Systems). See [LICENSE](LICENSE).

---

Full text: DISCLAIMER.md · Licensed under the MIT License. License: MIT © 2026 dhRobin Systems · Provided as-is, see the disclaimer.
