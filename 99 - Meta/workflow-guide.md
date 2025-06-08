# INMPARA Workflow Guide

Step-by-step implementation of the INMPARA system for bottom-up knowledge management.

## 🚦 The Seven-Step Workflow

### 🟢 1. Capture → Inbox (I)

**When**: Immediately, whenever a thought, idea, insight, or useful snippet occurs
**What**: Short notes, quick thoughts, screenshots, links, voice notes, code snippets, errors
**How**: Quick capture in `0 - Inbox/` folder using whatever method is fastest

**Examples**:
- `Azure Databricks PE issue encountered—check private DNS config`
- `Interesting AI paper: transformer attention mechanisms`
- `Meeting insight: need better async communication tools`

### 🔵 2. Create Atomic Notes → Notes (N)

**When**: Daily processing (ideally end of day or morning)
**What**: Transform inbox items into clear, single-concept notes
**How**: Timestamp-based IDs, Markdown format, clear titles

**Template**:
```markdown
# [Clear Descriptive Title]
Created: YYYY-MM-DD HH:MM
Tags: #tag1 #tag2

## Content
[Single concept, clearly explained in your words]

## Links
- Related to: [[Other Note]]
- See also: [[Reference]]

## Next Steps
- [ ] Action if needed
```

**Example**:
```
20250608T1540-azure-databricks-private-endpoint-dns.md

# Azure Databricks Private Endpoint DNS Setup

Created: 2025-06-08 15:40
Tags: #azure #databricks #dns #networking

## Content
Encountered DNS resolution issues when setting up private endpoints for Databricks workspace.

Key findings:
- Private DNS zone required: `privatelink.azuredatabricks.net`
- A-record setup mandatory for internal auth endpoints
- VNet linkage must be confirmed in DNS zone

## Links
- Related to: [[Azure Private Endpoint Patterns]]
- See also: [[Terraform DNS Configuration]]

## Next Steps
- [ ] Check Terraform module for automated DNS creation
- [ ] Verify private endpoint setup in staging environment
```

### 🟣 3. Notice Patterns & Create MOCs (M)

**When**: Weekly review or when natural clusters become obvious
**What**: Group related atomic notes into Maps of Content
**How**: Create hub notes that link and contextualize related atomic notes

**MOC Template**:
```markdown
# [Topic] MOC
Created: YYYY-MM-DD
Type: Map of Content
Tags: #moc #[topic]

## Overview
[Brief description of this knowledge cluster]

## Core Concepts
- [[Note 1]] - Brief description
- [[Note 2]] - Brief description

## Subtopics
### [Subtopic 1]
- [[Related Note A]]
- [[Related Note B]]

### [Subtopic 2]
- [[Related Note C]]
- [[Related Note D]]

## Emerging Patterns
[Insights from reviewing these notes together]

## Potential Projects
[Ideas for actionable work that emerged from this cluster]
```

**Example**:
```markdown
# Azure Networking MOC
Created: 2025-06-08
Type: Map of Content
Tags: #moc #azure #networking

## Overview
Central hub for Azure networking knowledge, patterns, and troubleshooting.

## Core Concepts
- [[20250608T1540-azure-databricks-private-endpoint-dns]] - Private endpoint DNS configuration
- [[20250607T0900-azure-vnet-peering-limitations]] - VNet peering constraints
- [[20250606T1430-azure-bastion-connectivity-issues]] - Bastion troubleshooting

## Subtopics
### Private Endpoints & DNS
- [[Azure Private DNS Zone Configuration]]
- [[Private Endpoint Terraform Patterns]]

### VNet Architecture
- [[Hub-Spoke Network Design]]
- [[Network Security Group Best Practices]]

## Emerging Patterns
- DNS configuration is consistently the most complex part of private endpoint setup
- Terraform modules need better DNS automation
- Hub-spoke topology becoming standard for enterprise workloads

## Potential Projects
- Standardized Terraform module for private endpoint + DNS
- Azure networking troubleshooting playbook
```

### 🟠 4. Initiate Projects from MOCs (P)

**When**: When a specific outcome or deliverable becomes clear from MOCs
**What**: Define actionable initiatives with clear goals and next steps
**How**: Create project notes that reference relevant MOCs and atomic notes

**Project Template**:
```markdown
# [Project Name]
Created: YYYY-MM-DD
Status: Planning | Active | On Hold | Completed
Type: Project
Tags: #project #[domain]

## Objective
[Clear statement of what success looks like]

## Context
[Why this project matters, what prompted it]

## Related Knowledge
- Primary MOC: [[Relevant MOC]]
- Key Notes: [[Note 1]], [[Note 2]]

## Tasks
- [ ] Task 1
- [ ] Task 2
- [ ] Task 3

## Resources Needed
- [Tools, time, people, etc.]

## Success Criteria
- [How you'll know it's done]

## Timeline
- Start: [Date]
- Target completion: [Date]
```

### 🟡 5. Identify Long-Term Areas (A)

**When**: When you repeatedly engage with similar topics or have ongoing responsibilities
**What**: Create stable areas of ongoing interest/responsibility
**How**: Area notes that link to related MOCs, projects, and notes

**Area Template**:
```markdown
# [Area Name]
Created: YYYY-MM-DD
Type: Area
Tags: #area #[domain]

## Purpose
[Why this area matters, your role/responsibility]

## Related MOCs
- [[MOC 1]]
- [[MOC 2]]

## Active Projects
- [[Project A]]
- [[Project B]]

## Key Resources
- [[Resource 1]]
- [[Resource 2]]

## Review Schedule
- [How often you review this area]

## Current Focus
[What you're prioritizing in this area right now]
```

### ⚪️ 6. Curate Stable Resources (R)

**When**: When external references or documents are frequently consulted
**What**: Organize reference materials and external resources
**How**: Resource notes or linked external sources

**Resource Template**:
```markdown
# [Resource Name]
Created: YYYY-MM-DD
Type: Resource
Tags: #resource #[domain]

## Description
[What this resource is and why it's valuable]

## Key Information
[Essential facts, commands, references]

## Usage Context
[When and how you typically use this]

## Related Knowledge
- Supports: [[Area]] or [[Project]]
- References: [[Note 1]], [[Note 2]]

## External Links
- [Link 1]
- [Link 2]
```

### 🔴 7. Archive Inactive Items (A)

**When**: After project completion or when notes/MOCs are no longer actively consulted
**What**: Move completed or inactive items to archive
**How**: Simple folder structure in `6 - Archive/`

**Archive Structure**:
```
6 - Archive/
├── completed-projects/
├── archived-notes/
├── old-mocs/
└── outdated-resources/
```

## ♻️ Review Cycles

### Daily (5-10 minutes)
- Process inbox items into atomic notes
- Quick review of today's notes for immediate connections

### Weekly (30-45 minutes)
- Review week's atomic notes for patterns
- Create or update MOCs as clusters emerge
- Identify potential projects or areas

### Monthly (1-2 hours)
- Review active projects and areas
- Archive completed items
- Refine MOCs and note connections
- Plan upcoming project work

## 🤖 AI Integration Points

### Capture Phase
- Voice-to-text transcription
- Auto-summarization of long content
- Quick note formatting

### Processing Phase
- Suggest related notes during atomic note creation
- Auto-tagging based on content
- Identify potential duplicates

### Pattern Recognition
- Suggest MOC creation when note clusters reach critical mass
- Recommend connections between existing MOCs
- Identify potential projects from note patterns

### Maintenance
- Suggest archive candidates
- Identify orphaned notes
- Recommend MOC updates

## Tips for Success

1. **Start small**: Begin with just inbox and notes, add other folders as needed
2. **Be consistent**: Daily processing is more important than perfect categorization
3. **Trust emergence**: Don't force MOCs or projects before they're ready
4. **Review regularly**: The system only works with regular maintenance
5. **Adapt freely**: Modify templates and processes to match your needs

The goal is sustainable knowledge building, not perfect organization.
