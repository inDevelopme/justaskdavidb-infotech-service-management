# Example Change Request - Database Schema Update

This is a simplified example showing how to fill out the Change Management Template.

## Change Request Information

| Field | Details |
|-------|---------|
| **Change Request ID** | CR-2025-0001 |
| **Change Title** | Update customer database schema to support multi-region data |
| **Requested By** | Development Team / John Smith |
| **Date Submitted** | 2025-11-11 |
| **Target Implementation Date** | 2025-11-25 02:00 AM UTC |
| **Change Type** | ☐ Standard ☑ Normal ☐ Emergency |
| **Change Category** | ☐ Infrastructure ☐ Application ☑ Database ☐ Network ☐ Security ☐ Other |
| **Priority** | ☐ Critical ☑ High ☐ Medium ☐ Low |
| **Risk Level** | ☐ High ☑ Medium ☐ Low |

---

## 1. Change Description

### 1.1 Summary of Change
Add new columns to the `customers` table to support regional data storage requirements. This includes `region_id`, `data_residency_country`, and `compliance_tier` fields.

### 1.2 Business Justification
Our expansion into EU and APAC regions requires compliance with data residency regulations (GDPR, local data protection laws). This schema update enables our application to properly track and enforce regional data storage requirements, which is a legal requirement for operation in these markets.

### 1.3 Systems/Components Affected
- Production database server: `prod-db-01.example.com`
- Customer Management API (reads from this table)
- Customer Portal application
- Reporting service (uses this table for analytics)
- Backup/DR systems

---

## 4. Pre-Deployment Procedures

### 4.1 Prerequisites
- [x] Database backup verified (last successful: 2025-11-10 23:00 UTC)
- [x] Schema changes tested in dev, QA, and staging
- [x] API changes deployed to support new fields (deployed 2025-11-08)
- [x] Change window approved by stakeholders
- [x] DBA team availability confirmed

### 4.2 Pre-Implementation Checklist
- [x] Backup verification completed
- [x] All dependencies identified and notified
- [x] Required access/permissions confirmed
- [x] Change window confirmed with stakeholders
- [x] Communication sent to affected users
- [x] Rollback procedure tested and verified
- [x] Team members briefed on their roles
- [x] Emergency contacts list updated

---

## 5. Deployment Procedures

### 5.1 Implementation Steps

**Step 1:** Verify database backup and take pre-change snapshot
```sql
-- Verify last backup
SELECT * FROM backup_history WHERE status = 'SUCCESS' 
ORDER BY backup_time DESC LIMIT 1;

-- Create snapshot
CREATE SNAPSHOT customers_pre_change_2025_11_25;
```
- Expected outcome: Snapshot created successfully
- Estimated duration: 5 minutes

**Step 2:** Execute schema changes
```sql
-- Add new columns
ALTER TABLE customers 
ADD COLUMN region_id INT DEFAULT 1,
ADD COLUMN data_residency_country VARCHAR(2) DEFAULT 'US',
ADD COLUMN compliance_tier VARCHAR(20) DEFAULT 'standard';

-- Add indexes for performance
CREATE INDEX idx_customers_region ON customers(region_id);
CREATE INDEX idx_customers_country ON customers(data_residency_country);
```
- Expected outcome: Columns and indexes created, table remains accessible
- Estimated duration: 10 minutes

**Step 3:** Update default values for existing rows
```sql
-- Update existing customers to proper region based on address
UPDATE customers 
SET region_id = 1, data_residency_country = 'US'
WHERE country = 'United States';
```
- Expected outcome: Existing records updated with appropriate values
- Estimated duration: 5 minutes

---

## 6. Validation & Testing Procedures

### 6.1 Validation Steps

- [x] **Test 1**: Verify new columns exist
  - Expected Result: DESCRIBE customers shows new columns
  - Actual Result: ✓ All three columns present with correct data types
  - Status: ☑ Pass ☐ Fail

- [x] **Test 2**: Verify API can read/write new fields
  - Expected Result: GET/POST requests succeed with new fields
  - Actual Result: ✓ API responses include new fields
  - Status: ☑ Pass ☐ Fail

- [x] **Test 3**: Verify existing functionality unchanged
  - Expected Result: Customer portal loads customer data correctly
  - Actual Result: ✓ All customer data displays properly
  - Status: ☑ Pass ☐ Fail

---

## 7. Test Evidence

### 7.1 Pre-Production Testing

| Environment | Test Date | Test Results | Tester | Evidence Location |
|-------------|-----------|--------------|--------|-------------------|
| Development | 2025-11-05 | ☑ Pass ☐ Fail | Jane Doe | `/docs/test-reports/dev-schema-test.pdf` |
| QA/Staging | 2025-11-08 | ☑ Pass ☐ Fail | QA Team | `/docs/test-reports/qa-schema-test.pdf` |
| UAT | 2025-11-10 | ☑ Pass ☐ Fail | Business Users | `/docs/test-reports/uat-schema-test.pdf` |

### 7.2 Test Artifacts
- Test Report: `https://confluence.example.com/change-2025-0001`
- Screenshots: `https://drive.example.com/schema-validation-screenshots`
- Performance Results: Average query time impact < 5ms (acceptable)
- Schema diff: Available in repository under `/db/migrations/2025-0001/`

---

## 8. Backout/Rollback Plan

### 8.1 Rollback Decision Criteria
- Critical functionality failure (unable to create/read customers)
- Performance degradation > 50% on customer queries
- Data corruption detected in customer records
- Application errors exceed 1% of requests

### 8.2 Rollback Procedures

**Step 1:** Stop application traffic to database
```bash
# Put application in maintenance mode
kubectl scale deployment customer-api --replicas=0
```
- Expected duration: 2 minutes

**Step 2:** Drop new columns
```sql
ALTER TABLE customers 
DROP COLUMN region_id,
DROP COLUMN data_residency_country,
DROP COLUMN compliance_tier;

-- Remove indexes
DROP INDEX idx_customers_region;
DROP INDEX idx_customers_country;
```
- Expected duration: 5 minutes

**Step 3:** Restore application traffic
```bash
# Remove maintenance mode
kubectl scale deployment customer-api --replicas=3
```
- Expected duration: 3 minutes

### 8.4 Rollback Time Estimate
- **Total Rollback Time**: 15 minutes
- **Point of No Return**: After step 3 (data population) - rollback still possible but data updates would be lost

---

## 10. Approval Section

### 10.1 Change Advisory Board (CAB) Review

| CAB Member | Role | Approval | Date | Comments |
|------------|------|----------|------|----------|
| Sarah Johnson | CAB Chair | ☑ Approved ☐ Rejected ☐ Deferred | 2025-11-18 | Approved pending successful staging validation |
| Mike Chen | Technical Authority | ☑ Approved ☐ Rejected ☐ Deferred | 2025-11-18 | Rollback plan is solid |
| Lisa Wang | Security Representative | ☑ Approved ☐ Rejected ☐ Deferred | 2025-11-18 | No security concerns |
| Tom Brown | Business Representative | ☑ Approved ☐ Rejected ☐ Deferred | 2025-11-18 | Critical for EU expansion |
| Alice Cooper | Operations Manager | ☑ Approved ☐ Rejected ☐ Deferred | 2025-11-18 | Weekend window approved |

### 10.3 Implementation Authorization
- **Authorized By**: Sarah Johnson / CAB Chair
- **Authorization Date**: 2025-11-18
- **Conditions/Requirements**: 
  - Must complete during approved maintenance window (02:00-04:00 UTC)
  - DBA must be on call during implementation
  - Notify stakeholders 24 hours before implementation

---

## Notes

This is a simplified example. In a real change request, you would include more detail in sections like:
- Impact Assessment (section 2)
- Risk Assessment (section 3)  
- Communication Plan (section 9)
- Post-Implementation Review (section 11)
- Additional Information (section 12)

See the full template at [CHANGE_MANAGEMENT_TEMPLATE.md](CHANGE_MANAGEMENT_TEMPLATE.md) for all sections.
