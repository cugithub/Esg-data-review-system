# MODEL.md

## Data Model Design

The application uses separate tables for raw uploaded data and normalized emission records.

This separation helps:
- maintain audit history
- preserve source-of-truth
- support reprocessing later

---

# Main Tables

## Organization

Stores company information.

Fields:
- id
- name
- created_at

Purpose:
Supports multi-tenancy.

---

## DataSource

Tracks uploaded sources.

Fields:
- organization
- source_type
- uploaded_file
- uploaded_at

Purpose:
Tracks where data came from.

---

## RawData

Stores original uploaded rows.

Fields:
- datasource
- raw_json
- status

Purpose:
Preserves original enterprise data before transformation.

---

## EmissionRecord

Stores normalized ESG records.

Fields:
- category
- scope
- amount
- unit
- normalized_value
- is_suspicious
- is_approved

Purpose:
Stores cleaned ESG data for analyst review.

---

## ReviewLog

Stores analyst actions.

Fields:
- emission_record
- action
- reviewed_at

Purpose:
Maintains audit trail.

---

# Scope Categorization

## Scope 1
Direct emissions:
- fuel usage

## Scope 2
Purchased electricity.

## Scope 3
Business travel.

---

# Audit Trail

The system preserves:
- upload source
- uploaded file
- review status
- approval history

This helps maintain traceability for audits.

---

# Normalization

Different uploaded formats are converted into common structure.

Example:
- liters
- kWh
- travel distance

All become standardized emission records.
