# Autonomous Compliance & Security Command Center

**Product 2** — orchestrates existing engines; does not rebuild them.

## Connected systems

| Engine | Integration |
|--------|-------------|
| DPP Autopilot API | `POST/GET /api/v1/dpp/*` — passports, readiness, evidence, suppliers |
| Security Control Center | HQ SCC + `ComplianceReport` kind `security_control_center` |
| Amber Autonomous API | `GET /api/v1/autonomous/jobs` — open jobs / authorized resolution tasks |

## Production

- Pricing: https://hq.amberoneai.com/pricing
- Command Center API: `https://hq.amberoneai.com/api/v1/compliance/command-center`
- HQ UI: `https://hq.amberoneai.com/dashboard/compliance-command`
- DPP product: https://github.com/scubamike124/dpp-autopilot-api
- Autonomous product: https://github.com/scubamike124/amber-autonomous-api

## Live pricing (Stripe)

| Bundle | Price | What you get |
|--------|-------|----------------|
| **DPP Autopilot (CC)** (`cc_dpp`) | **$299/mo** | Command Center + DPP (5,000 passports/mo). **No** cybersecurity rollup. |
| **DPP + Cybersecurity** (`cc_dpp_cyber`) | **$599/mo** | Everything in CC DPP + cybersecurity score in Command Center (10,000 passports/mo). |
| **Complete Autonomous Compliance** (`cc_complete`) | **$799/mo** | DPP + cyber + Amber Autonomous quota (25,000 passports/mo). |
| **Enterprise** | Custom | SSO, multi-tenant, dedicated support — contact sales. |

**Differentiation vs API-only:** `$99` / `$299` DPP Autopilot plans are API-only (no Command Center). Command Center starts at `$299` with the dashboard.

## Primary action

```bash
curl -X POST https://hq.amberoneai.com/api/v1/compliance/command-center \
  -H "Authorization: Bearer $AMBER_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"action":"resolve","products":[{"productId":"SKU-1","productCategory":"generic.preparatory","connectedData":{"name":"Widget","manufacturer":"Co"}}]}'
```

Resolves **deterministic** gaps from authorized connected data only. Never invents regulatory evidence.

## Legal

Health / readiness scores are **not** a formal legal compliance determination.

## Official EU DPP Registry

Not claimed complete. Official operator credentials required for live registry submission.
