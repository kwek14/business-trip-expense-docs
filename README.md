# business-trip-expense-docs

`business-trip-expense-docs` is a Codex skill for preparing reimbursement-ready evidence packages for business trip expenses.

It is designed for Korean research-project, university, industry-academic cooperation, and corporate reimbursement workflows where trip expenses must be documented with receipts, booking confirmations, card approvals, and supporting evidence.

## What It Does

This skill guides Codex through preparing structured reimbursement materials for costs such as:

- lodging expenses
- airfare
- conference registration fees
- local transportation
- tourist tax, city tax, and other local taxes
- personal-card payments to be reimbursed
- booking-platform receipts from services such as Agoda or Booking.com
- hotel folios, card approval screenshots, and email receipts

It is especially careful about separating actual reimbursable expenses from:

- deposits
- preauthorizations
- pending refunds
- partially cancelled charges
- unresolved local tax deductions
- missing or conflicting evidence

## Intended Output

The skill helps Codex create reviewer-facing reimbursement materials, usually as:

- editable PowerPoint evidence decks
- PDF evidence packages
- source ledgers
- expense summary tables
- evidence mapping tables

The generated materials should be written for reimbursement reviewers, not as casual explanations to the user.

## Install

Clone this repository into your Codex skills directory:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"

git clone https://github.com/kwek14/business-trip-expense-docs.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/business-trip-expense-docs"
```

Restart Codex or start a new session so the skill can be discovered.

## Usage

Invoke the skill explicitly:

```text
Use $business-trip-expense-docs to prepare a reimbursement-ready evidence package for my business trip expenses.
```

Example requests:

```text
출장 숙박비 정산 증빙자료를 PPT로 만들어줘.
```

```text
국외출장 항공료와 호텔비 카드 결제내역을 정산용 PDF로 정리해줘.
```

```text
Agoda 예약확인서, 호텔 영수증, 카드 승인내역을 기준으로 정산자료를 만들어줘. 보증금은 환불대기로 분리해줘.
```

## Repository Structure

```text
business-trip-expense-docs/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── document-structure.md
    └── evidence-rules.md
```

## Privacy Note

This repository should contain only skill instructions and reusable rules.

Do not commit actual reimbursement evidence such as:

- receipts
- invoices
- card statements
- approval screenshots
- passports
- tickets
- hotel folios
- generated reimbursement PPT/PDF files

Those files may contain personal information, payment details, travel schedules, booking numbers, or institutional data.

## License

Add a license if you plan to share or reuse this skill publicly.
