# AGENTS.md - WBST Order Center Public Prototype

This repository contains the public, sanitized review prototype for the WBST order center. It is intended for product, design, development, and test review of page structure, workflows, interactions, and acceptance points. All business data in the prototype is demo data.

## Scope

- Main prototype: `index.html`, a single-file offline HTML prototype.
- Flow source files: `flows/`.
- Version snapshot: `versions/v1.0.0/index.html`, read-only baseline.
- Version notes: `CHANGELOG.md` and GitHub releases.

Do not upload private research notes, contracts, PRDs, real customer names, contacts, phone numbers, addresses, account data, order amounts, or internal workspace paths.

## Product Boundaries

- Internal PC covers order operations, customer authorization, sales master data, customer credit, workflow review pages, dense lists, details, dialogs, approvals, row expansion, and local demo persistence.
- Customer PC covers customer order workbench, order creation, order detail, confirmation, and messages.
- Mobile covers customer-side quick order, order tracking, confirmation, after-sales entry, address, authorization, and messages.
- Customer-facing pages must not expose internal credit details, internal approvers, missing material details, transfer failure reasons, or internal responsibility departments.

## Menus And Flows

- Order Center menus must map to the order workbench, order entry, preorders, exception pool, order approval, formal sales orders, order changes, fulfillment/logistics, returns/rejection, reconciliation/payment, and the order business flow page.
- Customer Credit menus must map to the credit workbench, credit profile, credit limit, credit approval, receivable/overdue, freeze/release, credit rules, and the credit business flow page.
- Flow diagrams use real business participants such as customer, sales, finance, planning/production, warehouse/logistics, and approvers. Do not add a generic system lane.
- Flow nodes, menu entries, page titles, tabs, details, and jump targets should stay aligned.

## List And Dialog Standards

- Dense internal lists include query area, toolbar, sortable table, selectable rows, fixed operation column, pagination, status tags, row actions, and empty states where applicable.
- Create actions must open a real business dialog with required fields, validation, cancel/confirm actions, and saved demo rows.
- Detail actions must open a real detail dialog with business sections, status, process records, and related data.
- Row expansion is used only where extra operational context is meaningful. Remove expand affordances from pages that do not need expansion.
- Demo changes can use local browser persistence. Keep it deterministic and easy to reset through normal browser data clearing.

## Dashboard Standards

- Order workbench focuses on order intake efficiency, processing chain, transfer exceptions, and fulfillment risk.
- Credit workbench focuses on credit assets, limit occupation, receivable overdue, and risk control.
- Red means urgent, failed, overdue, frozen, over-limit, or blocked.
- Yellow means warning, pending, near due, high usage, or needs attention.
- Green means normal, effective, sufficient, completed, or on schedule.
- Do not rely on color alone. Pair color with icon, text, count, amount, ratio, or unit.
- All charts must show names and numbers by default without requiring hover.
- Chart clicks should jump to the corresponding business list and reuse existing tabs.

## UI And Technical Rules

- Keep the prototype offline-friendly. Use the embedded ECharts and Iconfont assets already in the file.
- Menus are floating overlays above business pages and must not push, shrink, or resize page content.
- Dialogs, flow details, messages, version entry, and terminal switcher can stay above floating menus.
- PC pages should prioritize dense, scannable business information. Avoid marketing-style hero layouts.
- Mobile pages should keep the iPhone-style grouped layout and bottom navigation.
- Validate common viewport sizes: 749x841, 890x950, 1080x900, 1440x900, and 1920x1080.

## Version Protection

- Do not change `V1.0.0`, `VERSION_HISTORY`, `CHANGELOG.md`, Git tags, releases, or `versions/v1.0.0/index.html` for ordinary prototype fixes.
- A new version requires coordinated updates to current version data, immutable snapshot, changelog, tag, and release.
- Public updates must remain sanitized and must not overwrite the private working prototype.
