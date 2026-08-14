# Autonomous Compliance & Security Command Center

**Product 2** — orchestrates existing engines; does not rebuild them.

## Connected systems

| Engine | Integration |
|--------|-------------|
| DPP Autopilot API | `POST/GET /api/v1/dpp/*` — passports, readiness, evidence, suppliers |
| Security Control Center | HQ SCC + `ComplianceReport` kind `security_control_center` |
| Amber Autonomous API | `GET /api/v1/autonomous/jobs` — open jobs / authorized resolution tasks |

## Production

- Command Center API: `https://hq.amberoneai.com/api/v1/compliance/command-center`
- HQ UI: `https://hq.amberoneai.com/dashboard/compliance-command`
- DPP product: https://github.com/scubamike124/dpp-autopilot-api
- Autonomous product: https://github.com/scubamike124/amber-autonomous-api

## Primary action

```bash
curl -X POST https://hq.amberoneai.com/api/v1/compliance/command-center \
  -H "Authorization: Bearer $AMBER_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"action":"resolve","products":[{"productId":"SKU-1","productCategory":"generic.preparatory","connectedData":{"name":"Widget","manufacturer":"Co"}}]}'
```

Resolves **deterministic** gaps from authorized connected data only. Never invents regulatory evidence.

## Bundle pricing (recommended)

| Bundle | Price |
|--------|-------|
| DPP Autopilot | $299/mo |
| DPP + Cybersecurity | $599/mo |
| Complete Autonomous Compliance | $799/mo |
| Enterprise | $1,499–$4,999+/mo |

Live Stripe bundle SKUs require owner activation (do not break existing AmberOne products).

## Legal

Health / readiness scores are **not** a formal legal compliance determination.
