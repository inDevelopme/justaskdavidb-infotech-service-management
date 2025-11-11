# Change Request Form

## Change Request Information

| Field | Details |
|-------|---------|
| **Change Request ID** | CR-YYYY-NNNN |
| **Change Title** | [Brief, descriptive title of the change] |
| **Requested By** | [Name/Team] |
| **Date Submitted** | YYYY-MM-DD |
| **Target Implementation Date** | YYYY-MM-DD HH:MM (Timezone) |
| **Change Type** | ☐ Standard ☐ Normal ☐ Emergency |
| **Change Category** | ☐ Infrastructure ☐ Application ☐ Database ☐ Network ☐ Security ☐ Other |
| **Priority** | ☐ Critical ☐ High ☐ Medium ☐ Low |
| **Risk Level** | ☐ High ☐ Medium ☐ Low |

---

## 1. Change Description

### 1.1 Summary of Change
[Provide a clear, concise description of what will be changed]

### 1.2 Business Justification
[Explain why this change is needed and the business value it provides]

### 1.3 Systems/Components Affected
[List all systems, applications, databases, servers, or infrastructure components that will be impacted]

- Component 1:
- Component 2:
- Component 3:

---

## 2. Impact Assessment

### 2.1 Service Impact
| Impact Area | Level | Description |
|-------------|-------|-------------|
| **Service Availability** | ☐ None ☐ Minimal ☐ Partial ☐ Full Outage | [Details] |
| **Performance** | ☐ None ☐ Minimal ☐ Moderate ☐ Significant | [Details] |
| **Data/Functionality** | ☐ None ☐ Minimal ☐ Moderate ☐ Significant | [Details] |

### 2.2 Users Affected
- **Number of Users Impacted**: [Specify number or percentage]
- **User Groups**: [List affected user groups/departments]
- **Geographic Impact**: ☐ Global ☐ Regional ☐ Local

### 2.3 Downstream Dependencies
[Identify any dependent systems, integrations, or processes that may be affected]

- Dependency 1:
- Dependency 2:

---

## 3. Risk Assessment

### 3.1 Implementation Risks
| Risk Description | Probability | Impact | Mitigation Strategy |
|-----------------|-------------|--------|---------------------|
| [Risk 1] | ☐ High ☐ Medium ☐ Low | ☐ High ☐ Medium ☐ Low | [Mitigation approach] |
| [Risk 2] | ☐ High ☐ Medium ☐ Low | ☐ High ☐ Medium ☐ Low | [Mitigation approach] |

### 3.2 Security Considerations
[Describe any security implications and how they will be addressed]

### 3.3 Compliance/Regulatory Impact
[Identify any compliance or regulatory considerations]

---

## 4. Pre-Deployment Procedures

### 4.1 Prerequisites
[List all conditions that must be met before implementation]

- [ ] Prerequisite 1
- [ ] Prerequisite 2
- [ ] Prerequisite 3

### 4.2 Pre-Implementation Checklist
- [ ] Backup verification completed
- [ ] All dependencies identified and notified
- [ ] Required access/permissions confirmed
- [ ] Change window confirmed with stakeholders
- [ ] Communication sent to affected users
- [ ] Rollback procedure tested and verified
- [ ] Team members briefed on their roles
- [ ] Emergency contacts list updated

### 4.3 Environment Preparation
[Describe any environment setup or configuration needed before deployment]

```bash
# Example preparation commands
# Add specific commands here
```

---

## 5. Deployment Procedures

### 5.1 Implementation Steps
[Provide detailed, step-by-step instructions for implementing the change]

**Step 1:** [Action]
```bash
# Commands or actions
```
- Expected outcome:
- Estimated duration:

**Step 2:** [Action]
```bash
# Commands or actions
```
- Expected outcome:
- Estimated duration:

**Step 3:** [Action]
```bash
# Commands or actions
```
- Expected outcome:
- Estimated duration:

### 5.2 Implementation Team Roles
| Name | Role | Responsibility | Contact |
|------|------|----------------|---------|
| [Name] | Change Manager | Overall coordination | [Email/Phone] |
| [Name] | Technical Lead | Implementation execution | [Email/Phone] |
| [Name] | QA/Tester | Validation | [Email/Phone] |
| [Name] | Communications | Stakeholder updates | [Email/Phone] |

### 5.3 Implementation Timeline
| Activity | Start Time | Duration | End Time |
|----------|------------|----------|----------|
| Pre-checks | | | |
| Deployment Start | | | |
| Validation | | | |
| Sign-off | | | |

---

## 6. Validation & Testing Procedures

### 6.1 Validation Steps
[Define specific tests to verify the change was successful]

- [ ] **Test 1**: [Description]
  - Expected Result: [What should happen]
  - Actual Result: [To be completed during implementation]
  - Status: ☐ Pass ☐ Fail

- [ ] **Test 2**: [Description]
  - Expected Result: [What should happen]
  - Actual Result: [To be completed during implementation]
  - Status: ☐ Pass ☐ Fail

- [ ] **Test 3**: [Description]
  - Expected Result: [What should happen]
  - Actual Result: [To be completed during implementation]
  - Status: ☐ Pass ☐ Fail

### 6.2 Smoke Tests
[Define quick tests to verify basic functionality]

```bash
# Example smoke test commands
```

### 6.3 Performance Validation
[Describe any performance metrics to monitor]

- Metric 1: [Baseline] → [Target]
- Metric 2: [Baseline] → [Target]

---

## 7. Test Evidence

### 7.1 Pre-Production Testing
[Document testing performed in non-production environments]

| Environment | Test Date | Test Results | Tester | Evidence Location |
|-------------|-----------|--------------|--------|-------------------|
| Development | | ☐ Pass ☐ Fail | | [Link/Path] |
| QA/Staging | | ☐ Pass ☐ Fail | | [Link/Path] |
| UAT | | ☐ Pass ☐ Fail | | [Link/Path] |

### 7.2 Test Artifacts
[Attach or link to test results, screenshots, logs, etc.]

- Test Report: [Link]
- Screenshots: [Link]
- Performance Results: [Link]
- Security Scan Results: [Link]

---

## 8. Backout/Rollback Plan

### 8.1 Rollback Decision Criteria
[Define conditions that would trigger a rollback]

- Criteria 1: [e.g., Critical functionality failure]
- Criteria 2: [e.g., Performance degradation > 20%]
- Criteria 3: [e.g., Data corruption detected]

### 8.2 Rollback Procedures
[Provide detailed steps to revert the change]

**Step 1:** [Action to rollback]
```bash
# Rollback commands
```
- Expected duration:

**Step 2:** [Action to rollback]
```bash
# Rollback commands
```
- Expected duration:

### 8.3 Rollback Validation
[Define tests to verify successful rollback]

- [ ] Test 1: [Verification step]
- [ ] Test 2: [Verification step]

### 8.4 Rollback Time Estimate
- **Total Rollback Time**: [XX minutes/hours]
- **Point of No Return**: [Time/step after which rollback becomes complex/impossible]

---

## 9. Communication Plan

### 9.1 Stakeholder Notification

| Stakeholder Group | Notification Method | Timing | Responsible Party |
|-------------------|---------------------|--------|-------------------|
| End Users | Email/Portal | 48h before | [Name] |
| IT Operations | Email/Chat | 24h before | [Name] |
| Management | Email | 72h before | [Name] |
| Support Teams | Email/Meeting | 24h before | [Name] |

### 9.2 Communication Templates

**Pre-Implementation Notice:**
```
Subject: [Change Type] Maintenance - [System] - [Date/Time]

Dear [Stakeholder],

This is to inform you of an upcoming change to [System/Service]...
[Include details, impact, duration, contact information]
```

**Implementation Status Updates:**
```
Subject: [Change ID] - Implementation [Started/In Progress/Completed/Rolled Back]

Status: [Current status]
Impact: [Any current impact]
Next Update: [Time]
```

**Post-Implementation Notice:**
```
Subject: [Change ID] - Implementation Complete

The change has been successfully completed...
[Include results, any follow-up actions]
```

---

## 10. Approval Section

### 10.1 Change Advisory Board (CAB) Review

| CAB Member | Role | Approval | Date | Comments |
|------------|------|----------|------|----------|
| [Name] | CAB Chair | ☐ Approved ☐ Rejected ☐ Deferred | | |
| [Name] | Technical Authority | ☐ Approved ☐ Rejected ☐ Deferred | | |
| [Name] | Security Representative | ☐ Approved ☐ Rejected ☐ Deferred | | |
| [Name] | Business Representative | ☐ Approved ☐ Rejected ☐ Deferred | | |
| [Name] | Operations Manager | ☐ Approved ☐ Rejected ☐ Deferred | | |

### 10.2 Emergency Change Approval (if applicable)
[For emergency changes requiring expedited approval]

| Approver | Role | Approval | Date/Time | Justification |
|----------|------|----------|-----------|---------------|
| [Name] | Emergency Authority | ☐ Approved ☐ Rejected | | |

### 10.3 Implementation Authorization
- **Authorized By**: [Name/Title]
- **Authorization Date**: YYYY-MM-DD
- **Conditions/Requirements**: [Any special conditions for approval]

---

## 11. Post-Implementation Review

### 11.1 Implementation Summary
- **Actual Start Time**: [Time]
- **Actual End Time**: [Time]
- **Status**: ☐ Successful ☐ Successful with Issues ☐ Failed ☐ Rolled Back

### 11.2 Issues Encountered
[Document any problems or deviations from the plan]

| Issue | Impact | Resolution | Time Lost |
|-------|--------|------------|-----------|
| | | | |

### 11.3 Validation Results
- [ ] All validation tests passed
- [ ] System performance within acceptable parameters
- [ ] No critical errors detected
- [ ] User acceptance confirmed

### 11.4 Lessons Learned
[What went well, what could be improved]

**What Went Well:**
- 
- 

**Areas for Improvement:**
- 
- 

**Recommendations for Future Changes:**
- 
- 

### 11.5 Follow-up Actions
[Any remaining tasks or monitoring requirements]

| Action Item | Assigned To | Due Date | Status |
|-------------|-------------|----------|--------|
| | | | |

### 11.6 Sign-off
- **Change Manager**: [Name] - Date: [YYYY-MM-DD]
- **Technical Lead**: [Name] - Date: [YYYY-MM-DD]
- **Business Owner**: [Name] - Date: [YYYY-MM-DD]

---

## 12. Additional Information

### 12.1 Related Changes
[Link to any related or dependent change requests]

- CR-YYYY-NNNN: [Description]

### 12.2 Documentation Updates
[List any documentation that needs to be updated as a result of this change]

- [ ] Technical documentation
- [ ] User guides
- [ ] Runbooks
- [ ] Architecture diagrams
- [ ] Configuration management database (CMDB)

### 12.3 Attachments/References
[Links to relevant documents, diagrams, specifications]

- Design Document: [Link]
- Architecture Diagram: [Link]
- Test Plan: [Link]
- Runbook: [Link]

---

## Template Version
**Version**: 1.0  
**Last Updated**: 2025-11-11  
**Owner**: IT Service Management Team
