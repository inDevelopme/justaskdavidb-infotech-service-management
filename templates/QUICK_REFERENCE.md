# Change Management Quick Reference

This is a quick reference guide for the key sections of the Change Management Template.

## Essential Sections for CAB Approval

When preparing a change request for CAB approval, ensure these critical sections are thoroughly completed:

### 1. Change Classification
- **Change Type**: Standard, Normal, or Emergency
- **Priority**: Critical, High, Medium, or Low  
- **Risk Level**: High, Medium, or Low

### 2. Test Evidence (Section 7)
**What CAB wants to see:**
- Results from Development, QA/Staging, and UAT environments
- Screenshots, logs, and test reports
- Performance test results
- Security scan results (if applicable)

**Why it matters:** Demonstrates due diligence and reduces implementation risk

### 3. Backout/Rollback Plan (Section 8)
**What CAB wants to see:**
- Clear rollback decision criteria
- Step-by-step rollback procedures
- Estimated rollback time
- Point of no return identification

**Why it matters:** Ensures business continuity if the change fails

### 4. Validation Procedures (Section 6)
**What CAB wants to see:**
- Specific, measurable validation steps
- Expected vs. actual results
- Pass/fail criteria
- Smoke tests for quick verification

**Why it matters:** Confirms the change works as intended

### 5. Pre-Deployment Procedures (Section 4)
**What CAB wants to see:**
- Complete prerequisites checklist
- Backup verification
- Access/permissions confirmed
- Dependencies identified and notified

**Why it matters:** Prevents implementation delays and issues

### 6. Deployment Procedures (Section 5)
**What CAB wants to see:**
- Detailed step-by-step instructions
- Expected outcomes for each step
- Time estimates
- Team roles and responsibilities

**Why it matters:** Ensures consistent, repeatable implementation

### 7. Approver Section (Section 10)
**Required for approval:**
- CAB Chair approval
- Technical Authority sign-off
- Security Representative review (for security-related changes)
- Business Representative acknowledgment
- Operations Manager approval

### 8. Impact Assessment (Section 2)
**What CAB wants to see:**
- Service availability impact (outage duration if any)
- Number of users affected
- Downstream dependencies
- Geographic scope

**Why it matters:** Helps CAB assess risk and schedule appropriately

### 9. Communication Plan (Section 9)
**What CAB wants to see:**
- Stakeholder notification schedule
- Communication templates
- Status update plan
- Support team readiness

**Why it matters:** Manages expectations and ensures smooth coordination

## Common CAB Rejection Reasons

❌ **Insufficient Test Evidence**
- Solution: Test in all environments, document results thoroughly

❌ **Unclear or Untested Rollback Plan**
- Solution: Test the rollback procedure, document exact steps

❌ **Incomplete Impact Assessment**
- Solution: Identify all affected systems and dependencies

❌ **Missing Prerequisites**
- Solution: Complete the pre-deployment checklist

❌ **Inadequate Communication Plan**
- Solution: Define clear stakeholder notifications

❌ **High Risk Without Mitigation**
- Solution: Identify risks and document mitigation strategies

## Tips for CAB Presentation

1. **Be Concise**: Present the key points, have details ready for questions
2. **Know Your Numbers**: Users impacted, downtime duration, rollback time
3. **Show Evidence**: Have test results and screenshots ready
4. **Be Prepared**: Know your rollback plan cold
5. **Communicate Confidence**: If you're not confident, CAB won't be either

## Checklist Before Submitting to CAB

- [ ] All sections of the template are completed
- [ ] Test evidence from all environments is attached
- [ ] Rollback plan has been tested
- [ ] Impact assessment is thorough and realistic
- [ ] Communication plan covers all stakeholders
- [ ] Team roles and responsibilities are assigned
- [ ] Prerequisites are documented and achievable
- [ ] Risk assessment includes mitigation strategies
- [ ] Implementation timeline is realistic
- [ ] Technical lead has reviewed and approved
- [ ] All attachments and references are accessible

## Emergency Changes

For emergency changes requiring expedited approval:

1. **Document the emergency** - Why can't this wait for normal CAB?
2. **Identify emergency approvers** - Who has authority to approve?
3. **Streamline but don't skip** - Focus on critical sections (impact, rollback, validation)
4. **Communicate urgency** - Ensure all stakeholders understand the situation
5. **Follow up** - Complete full post-implementation review

## Standard Changes

Standard changes are pre-approved, low-risk changes:

- Must follow documented procedures exactly
- No CAB approval needed for each instance
- May require periodic CAB review of the standard change procedure
- Examples: password resets, standard patches, routine maintenance

---

**Remember**: The goal of the CAB is not to block changes, but to ensure they are well-planned, properly tested, and safely implemented. A thorough change request demonstrates professionalism and increases approval likelihood.

For the complete template, see [CHANGE_MANAGEMENT_TEMPLATE.md](CHANGE_MANAGEMENT_TEMPLATE.md)
