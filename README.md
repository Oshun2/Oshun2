# Omani Reed

**Cloud security engineer — Azure, infrastructure as code, and policy that runs in CI.**

I build Azure environments where the security properties are asserted by code rather than
described in a document. Private-only network boundaries, managed identities instead of
secrets, and custom policy checks that fail the build when a change reopens something that
was supposed to stay closed.

Most of what I know about securing Azure came from configuring it, breaking it, and then
writing the check that catches the break next time.

---

## Featured work

### 🔐 [sentinel-secure-ingestion](https://github.com/Oshun2/sentinel-secure-ingestion)
[![verify](https://github.com/Oshun2/sentinel-secure-ingestion/actions/workflows/verify.yml/badge.svg)](https://github.com/Oshun2/sentinel-secure-ingestion/actions/workflows/verify.yml)

A private-only log ingestion pipeline for Microsoft Sentinel, written in Terraform. Event
Hubs behind a private endpoint with SAS auth disabled, a VNet-integrated function consuming
the stream with a system-assigned managed identity, and delivery to Log Analytics over
Azure Monitor Private Link. **No component is reachable from the internet and no credential
exists anywhere in the configuration.**

Seven custom Checkov policies assert those properties on every commit, so a change that
reopens the boundary fails CI instead of shipping. Where a built-in check conflicts with a
deliberate decision, the exception is suppressed inline with a written reason — including
one case where satisfying the check would have required reintroducing a storage account key
to audit an account that is already audited without one.

`Terraform` · `Checkov` · `Private Link` · `Managed Identity` · `KQL` · `GitHub Actions`

> Clone it and run the policy suite yourself — no Azure subscription or credentials needed.

### 📋 [cmmc-to-az104](https://github.com/Oshun2/cmmc-to-az104) · [browse the site →](https://oshun2.github.io/cmmc-to-az104/)

All 125 CMMC 2.0 practices (15 at Level 1, 110 at Level 2) mapped to the Azure resources
that implement them, the evidence that proves each one is met, and the Azure CLI to
configure it. Built for three audiences at once: assessors get a fillable tracker and POA&M
template, GRC teams get evidence requirements per control, and administrators get the
commands.

A CI validator enforces the practice counts, rejects malformed IDs, requires a NIST SP
800-171 reference for every entry, and fails if the assessment tracker drifts out of sync
with the source CSVs.

`CMMC 2.0` · `NIST SP 800-171` · `Azure Policy` · `Python` · `DoD / CUI`

---

## Also here

| Repository | What it is |
|---|---|
| [Azure-Cloud-SOC](https://github.com/Oshun2/Azure-Cloud-SOC) | A guided honeynet lab (2023) — Sentinel attack telemetry measured before and after hardening. Clearly labeled as a walkthrough, kept because the before/after numbers are real. |
| [serverless-resume-api](https://github.com/Oshun2/serverless-resume-api) | A fork of `madebygps/serverless-resume-api`, deployed to my own domain with added Static Web Apps CI, routing, and DNS work. |

---

## Working with

**Cloud** Azure · Entra ID · Sentinel · Log Analytics · Key Vault · Private Link · Azure Functions
**IaC & policy** Terraform · Checkov · Azure Policy · GitHub Actions
**Security** Threat modeling · detection engineering (KQL) · CMMC 2.0 · NIST SP 800-171
**Languages** Python · HCL · PowerShell · Bash

---

## Currently

- Deepening Azure detection engineering — writing analytics rules against real ingestion pipelines rather than sample data
- Building out the CMMC → Azure mapping toward Level 3 / NIST SP 800-172

---

📫 [LinkedIn](https://www.linkedin.com/in/omaireed/)
