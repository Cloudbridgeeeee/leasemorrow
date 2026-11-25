# LeaseMorrow — proposed AWS architecture

LeaseMorrow uses AWS to read complex legal documents, extract obligations accurately and keep every portfolio secure and auditable.

## Request flow

1. Leases
2. Amazon S3
3. Textract
4. Bedrock
5. Administrator review
6. DynamoDB
7. Reminders & reports

## Services

### Amazon Textract

**Role:** Read lease documents

Extracts text, tables and layout from leases, amendments and scanned side letters, including rent tables and schedules.

### Amazon Bedrock

**Role:** Find terms and obligations

Identifies rent, escalations, service charges, breaks and renewal options with the exact clause reference, and drafts portfolio summaries for review.

### Amazon S3

**Role:** Archive leases

Stores every lease and amendment encrypted and versioned, preserving the original documents behind each abstract.

### Amazon DynamoDB

**Role:** Hold abstracts and schedules

Keeps lease abstracts, rent schedules, obligations, reminders and review decisions for fast portfolio queries.

### AWS Lambda

**Role:** Calculate and remind

Builds rent schedules from confirmed terms, compares them with billing data and sends reminders as dates approach.

## Principles

- **Clause-linked** — Every term points to its clause and page.
- **Confirmed before used** — Only reviewed terms drive reminders and reports.
- **Portfolio privacy** — Each client’s leases are isolated and encrypted.

## Safeguards

- **Administrators confirm** — Extracted terms are drafts until a person confirms them against the clause.
- **Not legal advice** — LeaseMorrow organises lease information. Interpretation stays with your lawyers.
- **Always referenced** — Every term and date links to the source page.
- **Confidential terms** — Rents and tenant data are encrypted and access-controlled.

## MVP scope

Upload the leases for one property or a small portfolio. We extract the key terms, your team reviews them, and you get rent schedules, an obligation calendar and reminders from day one.

- Lease and amendment upload
- Term extraction with clause links
- Human review workflow
- Obligation calendar
- Rent schedule and portfolio report
