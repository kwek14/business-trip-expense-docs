# 출장비 정산 증빙자료 구조

Use this reference when building a PPTX or PDF evidence package.

## Default PPTX Structure

1. Cover: title, trip/event, traveler, destination, dates, document purpose.
2. Trip overview: event purpose, travel/stay period, cost categories covered.
3. Reimbursement summary: confirmed claim total by category; separate pending/excluded amounts.
4. Expense ledger: one row per financial line with status and source evidence label.
5. Lodging detail: stay dates, hotel, booking IDs, room-rate payments, local taxes, deposits/refunds.
6. Airfare detail: itinerary/ticket, payment evidence, booking reference.
7. Other categories: registration, transport, baggage, visa, or other trip costs as applicable.
8. Exception handling: deposits/preauthorizations, refund-pending lines, missing receipts, amount mismatches.
9. Evidence appendix: screenshots, receipts, confirmations, folios, card approvals, email evidence.

Skip irrelevant sections, but do not skip the reimbursement summary, ledger, or exception handling when unresolved items exist.

## Default PDF Structure

For a PDF package, use the same order as the PPTX. Prefer A4 portrait for text-heavy evidence and A4 landscape for wide tables or screenshots. Add page numbers when practical.

## Reviewer-Facing Wording

Use concise Korean administrative wording:

- `정산 요청 금액`
- `증빙자료 요약`
- `결제 및 예약 내역`
- `현지세 별도 결제`
- `보증금/가승인 건은 정산 요청 금액에서 제외`
- `환불 또는 차감 완료 후 추가 증빙 필요`
- `카드 승인내역 기준 원화 결제금액`

Avoid:

- casual explanation to the user,
- unsupported claims that a payment includes taxes,
- hiding pending refunds in footnotes,
- decorative layouts that reduce legibility.

## Visual Layout

- Use tables for totals and ledger rows.
- Put one major claim per slide/page when evidence is complex.
- Keep screenshots large enough that merchant, amount, date, and approval number are readable.
- Use neutral colors and restrained emphasis. Red or yellow should be reserved for unresolved or excluded items.
- Add short source labels such as `증빙 A-1`, `카드내역 C-2`, or `예약확인 B-1`.

## Recommended Artifact Set

Create or maintain these working artifacts when the task is more than a single receipt:

```text
source-notes.md
expense-ledger.csv
source_evidence/
preview/
```

`source-notes.md` should record source observations, assumptions, missing evidence, and reconciliation decisions. `expense-ledger.csv` should be the numerical source for totals used in the final PPT/PDF.

## Verification Checklist

Before final delivery:

- Every `정산 요청` amount appears in the ledger.
- Every ledger row points to visible source evidence.
- Deposit/preauthorization/refund-pending rows are outside the requested total.
- Tourist/local taxes are separated unless source evidence says they are included.
- Dates in the package match the trip and source documents.
- Rendered previews show no clipped tables, unreadable screenshots, or overlapping text.
