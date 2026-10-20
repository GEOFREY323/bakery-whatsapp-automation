# WhatsApp Order Automation for Bakeries

An end-to-end automation that reads incoming WhatsApp orders, confirms them instantly, logs them to Google Sheets, and sends the owner a daily summary.

## Architecture

WhatsApp Trigger → Set (normalise) → Dedup → IF (is order?) → AI Parse (Gemini) → Validate → IF (valid?) → Google Sheets → WhatsApp Confirmation

## Tools Used

- n8n (workflow orchestration)
- Google Gemini (AI parsing)
- WhatsApp Business API (planned — currently manual trigger for testing)
- Google Sheets (order log)

## How to Import

1. Import `workflows/main-flow.json` into n8n
2. Set credentials: Google Gemini, Google Sheets
3. Configure the "Config" node with your spreadsheet ID and owner number
4. Activate the workflow

## Known Limitations

- WhatsApp nodes are placeholders (TODO nodes) until Meta API access is approved
- Voice notes are not parsed
- Error Handler workflow is built but not yet linked (known n8n bug)
- No payment integration

## Status

- Core workflow: ✅ Working
- Daily summary: ✅ Working
- Hostile-data tests: ✅ Passed
- Error handler: ⚠️ Built but not linked
- WhatsApp integration: ⏸️ Pending Meta approval