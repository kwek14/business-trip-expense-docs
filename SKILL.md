---
name: business-trip-expense-docs
description: Prepare Korean business trip expense reimbursement documents and evidence packages for research projects, universities, industry-academic cooperation offices, or corporate settlement. Use when the user needs 출장비 정산 서류, 국외출장 경비 정산, 국내출장 경비 정산, 개인카드 선결제 정산, 숙박비/항공료/학회등록비/현지교통비/관광세 증빙, Agoda/Booking.com/hotel/airline/card receipt evidence, or PPT/PDF reimbursement materials that distinguish actual expenses from deposits, preauthorizations, refunds, and pending charges.
---

# 출장비 정산 서류

Use this skill to produce settlement-ready evidence packages for business trip expenses. The output should read as an administrative reimbursement document for a reviewer, not as an explanation to the user.

## Core Rules

- Do not fabricate receipts, invoices, bookings, card approvals, refund evidence, or institutional approvals.
- Separate `정산 요청 금액` from `정산 제외`, `환불대기`, `가승인/보증금`, and `추가 확인 필요`.
- Treat a hotel deposit, card preauthorization, or security hold as non-reimbursable until a final receipt, folio, settled charge, or non-refund evidence shows that the amount became an actual expense.
- Treat tourist tax, city tax, resort fee, service fee, and other local taxes as separate lines unless the source evidence explicitly includes them in the room rate.
- Use exact source-backed dates, amounts, currencies, merchants, approval numbers, booking IDs, stay periods, and traveler names when visible.
- Preserve original source files. Create settlement copies, previews, and extracted images in a work folder.

## Workflow

1. Define the trip scope: traveler, destination, trip dates, purpose, event name, cost categories, output format, and target institution if known. Infer from supplied evidence when reliable; ask only for missing facts that affect reimbursement.
2. Collect evidence from local files, screenshots, Gmail, browser pages, card statements, booking confirmations, e-receipts, hotel folios, airline documents, and conference registration pages.
3. Read `references/evidence-rules.md` before classifying expenses, identifying missing evidence, or deciding whether a deposit/refund/tax item is reimbursable.
4. Build a source ledger with one row per financial item:

```text
cost_id, category, service_period, merchant, source_currency_amount, krw_amount,
payment_method, payment_date, approval_no, booking_or_ticket_id,
reimbursement_status, source_evidence
```

5. Reconcile related records: reservation vs receipt, receipt vs card approval, deposit vs final folio, original charge vs refund, split bookings vs continuous stay.
6. Prepare the requested deliverable:
   - For editable PPTX, use the `presentations:Presentations` skill and default to `/Users/sn/output/pptx`.
   - For PDF, use the `pdf:pdf` skill and default to `/Users/sn/output/pdf`.
   - For ledger spreadsheets, use the `spreadsheets:Spreadsheets` skill.
   - For Gmail evidence search, use the Gmail app/skill when available.
   - For logged-in web pages or card portals, use Chrome/browser control only when the user has authorized that access.
7. Read `references/document-structure.md` when creating PPT/PDF page order, tables, and reviewer-facing wording.
8. Verify the final artifact visually. Render slides/pages when possible and check that all claimed amounts map to visible source evidence.

## Expense Classification

Use conservative classifications:

- `청구`: actual expense supported by receipt/invoice/payment evidence.
- `청구 가능 후보`: likely reimbursable, but missing one supporting document such as final receipt or card approval.
- `정산 제외`: personal, duplicate, unsupported, or outside trip scope.
- `환불대기`: paid or held amount expected to be refunded, partially cancelled, or offset later.
- `가승인/보증금`: authorization or security deposit with no final charge evidence.
- `추가 확인 필요`: evidence conflicts or amount/date/category is ambiguous.

Never hide ambiguous items inside totals. Put them in a separate table or slide with the reason and next required evidence.

## Output Requirements

Every final evidence package should include:

- Trip summary: traveler, trip purpose, destination, event, travel/stay dates.
- Reimbursement summary: totals by category and status, with KRW totals separated from foreign-currency source amounts.
- Evidence mapping: each claimed line linked to source file/page/screenshot and approval or booking number.
- Category detail pages for lodging, airfare, registration, transport, and other costs as applicable.
- Exception page for deposits, preauthorizations, refunds, tourist taxes, missing receipts, or pending cancellation/refund.
- Original evidence appendix pages/screenshots, cropped only for readability without altering facts.

Use Korean administrative wording. Avoid conversational text such as "제가", "내가", or direct instructions to the user inside the deliverable.

## File Organization

Use a task-specific work folder:

```text
/Users/sn/work/business-trip-expense-docs/<trip-or-task-slug>/
```

Recommended contents:

```text
source_evidence/        copied originals or rendered evidence images
tmp/                    previews, extracted pages, OCR/text notes
expense-ledger.csv      working ledger
source-notes.md         source observations and assumptions
```

Final artifacts should use descriptive names such as:

```text
<event>_<destination>_<yyyymmdd-range>_expense_reimbursement_evidence.pptx
<event>_<destination>_<yyyymmdd-range>_expense_reimbursement_evidence.pdf
```

## Missing Evidence Handling

Ask for only the missing items that materially affect the claim. If the current evidence is enough to produce a reviewer-facing package but some items are unresolved, include an `추가 확인 필요` or `환불대기` section instead of blocking the whole document.
