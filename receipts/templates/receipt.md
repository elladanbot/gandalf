# Gandalf Receipt Template

This receipt must follow the schema defined in:
`receipts/schema/receipt.schema.json`

Example receipt:

```json
{
  "id": "0001-bootstrap",
  "actor": "Gandalf",
  "requested_by": "Elladan",
  "timestamp": "2026-02-21T11:30:00Z",
  "status": "success",
  "intent": "Initialize repository and receipt system",
  "plan": [
    "Create repo",
    "Configure git identity",
    "Add template"
  ],
  "artifacts": {
    "commit": "d206bd8..."
  }
}

