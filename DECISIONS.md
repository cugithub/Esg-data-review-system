# DECISIONS.md

## Decision 1
Used Django REST Framework for backend.

### Why
Provides fast API development and strong admin support.

---

## Decision 2
Used CSV upload instead of live SAP integration.

### Why
CSV exports are common in enterprise workflows and easier for a 4-day prototype.

---

## Decision 3
Stored raw uploaded data separately.

### Why
Needed for audit trail and debugging ingestion issues.

---

## Decision 4
Used suspicious row flags.

### Why
Analysts need visibility into potentially incorrect records.

---

## Decision 5
Used React frontend.

### Why
Simple dashboard creation and API integration.

---

## Decision 6
Used PostgreSQL.

### Why
Reliable relational database for structured ESG data.
