# justaskdavidb-infotech-service-management

Information technology service management using GitHub to help with tracking and managing changes across all repositories.

## Overview

This repository provides IT Service Management (ITSM) templates and processes for managing production changes following industry best practices. It serves as a central location for documenting and tracking changes across all justaskdavidb repositories.

## Available Templates

### Change Management Template

A comprehensive change request template that follows ITSM best practices for production changes, designed for Change Advisory Board (CAB) approval.

**Location**: [`templates/CHANGE_MANAGEMENT_TEMPLATE.md`](templates/CHANGE_MANAGEMENT_TEMPLATE.md)

**Features**:
- Complete change request documentation structure
- Pre-deployment, deployment, and validation procedures
- Backout/rollback planning
- Test evidence documentation
- Risk and impact assessment
- CAB approval tracking
- Post-implementation review

**Quick Start**:
```bash
# Copy the template to create a new change request
cp templates/CHANGE_MANAGEMENT_TEMPLATE.md changes/CR-YYYY-NNNN-description.md
```

For detailed usage instructions, see [`templates/README.md`](templates/README.md)

## Benefits

- **Standardized Process**: Consistent approach to managing changes across all repositories
- **Risk Mitigation**: Comprehensive risk assessment and rollback procedures
- **Improved Communication**: Clear stakeholder notification and status updates
- **Audit Trail**: Complete documentation of all changes for compliance and review
- **Quality Assurance**: Systematic validation and testing procedures

## Getting Started

1. Review the [Change Management Template](templates/CHANGE_MANAGEMENT_TEMPLATE.md)
2. Read the [Template Usage Guide](templates/README.md)
3. Create your first change request by copying the template
4. Follow the documented procedures for your change

## Contributing

If you have suggestions for improving these templates or want to add additional ITSM templates, please:
- Open an issue describing your suggestion
- Submit a pull request with proposed changes

## License

See [LICENSE](LICENSE) file for details.
