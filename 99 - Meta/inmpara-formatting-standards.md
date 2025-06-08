# INMPARA Formatting Standards

> **Purpose**: Tool-agnostic semantic formatting for AI-enhanced knowledge management  
> **Principle**: Rich semantic structure using standard Markdown  
> **Goal**: Maximum portability with maximum AI enhancement potential  

## Core Design Principles

### 1. Tool Agnostic
- Standard Markdown syntax works everywhere
- YAML frontmatter supported by most modern tools
- No proprietary features required for core functionality

### 2. AI-First Structure
- Rich metadata for AI processing and automation
- Semantic patterns for knowledge graph building
- Forward references enable emergent connections

### 3. Semantic Density
- Every note contributes to knowledge graph
- Observations create searchable facts
- Relations enable navigation and discovery

### 4. Emergence-Friendly
- Structure emerges from content, not imposed top-down
- Forward references support bottom-up development
- Categories develop naturally through use

## Frontmatter Standards

### Required Fields
```yaml
---
title: [Descriptive Title - No File Extension]
type: [inbox|note|moc|project|area|resource|archive]
tags:
  - [primary-domain]
  - [content-type]
  - [technology-focus]
  - [specific-area]
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: [active|planning|completed|archived|on-hold|needs-review]
stage: [0-inbox|1-notes|2-mocs|3-projects|4-areas|5-resources|6-archive]
domain: [high-level-category]
permalink: [folder-path/kebab-case-filename]
---
```

### Field Definitions

**title**: Exactly matches the content H1 header
**type**: Maps to INMPARA stage for clarity
**tags**: 3-6 tags in hierarchical order (domain → type → technology → specifics)
**status**: Current state for lifecycle management
**stage**: INMPARA workflow position
**domain**: High-level categorization for cross-cutting themes
**permalink**: Relative path for consistent linking

### Example Frontmatter by Type

#### Note (1 - Notes)
```yaml
---
title: Azure Databricks Private Endpoint DNS Setup
type: note
tags:
  - azure
  - databricks
  - dns
  - networking
  - troubleshooting
created: 2025-06-08
updated: 2025-06-08
status: active
stage: 1-notes
domain: cloud-infrastructure
permalink: 1-notes/azure-databricks-private-endpoint-dns-setup
---
```

#### MOC (2 - MOCs)
```yaml
---
title: Azure Infrastructure MOC
type: moc
tags:
  - moc
  - azure
  - infrastructure
  - cloud-platform
created: 2025-06-08
updated: 2025-06-08
status: active
stage: 2-mocs
domain: cloud-infrastructure
permalink: 2-mocs/azure-infrastructure-moc
---
```

## Content Structure Standards

### Universal Content Pattern
```markdown
# [Title Matching Frontmatter]

## [Context Section - varies by type]
[Type-specific opening content]

## Observations
- [category] Factual observation or insight #relevant-tags
- [category] Another key finding #relevant-tags

## Relations
- relation_type [[Target Entity]]
- relation_type [[Target Entity]]

## Related Knowledge
- [[Cross Reference 1]]
- [[Cross Reference 2]]

## Tags
#tag1 #tag2 #tag3 #tag4
```

### Type-Specific Structures

#### Notes (1 - Notes)
```markdown
# [Note Title]

## Content
[Main insight or finding in your own words]

## Context
[Source, situation, or trigger for this note]

## Observations
- [technical-finding] Specific discovery #tech-tags
- [insight] Key understanding #concept-tags

## Relations
- relates_to [[Connected Concept]]
- part_of [[Parent MOC]]

## Related Knowledge
- [[Supporting Note 1]]
- [[Reference Resource 1]]

## Next Steps
- [ ] Follow-up action
- [ ] Investigation to pursue

## Tags
#domain #type #technology #specifics
```

#### MOCs (2 - MOCs)
```markdown
# [Topic] MOC

## Overview
[Purpose and scope of this knowledge cluster]

## Core Concepts
- [[Key Note 1]] - Brief insight description
- [[Key Note 2]] - Brief insight description

## Knowledge Clusters
### [Subtopic 1]
- [[Note A]]
- [[Note B]]

### [Subtopic 2]
- [[Note C]]
- [[Note D]]

## Observations
- [pattern] Recurring theme across notes #pattern-tag
- [insight] Understanding from connections #insight-tag

## Relations
- connects_to [[Related MOC]]
- enables [[Project Opportunities]]

## Emerging Patterns
[Insights visible only through MOC perspective]

## Potential Projects
[Actionable work suggested by knowledge cluster]

## Tags
#moc #domain #technology #cluster-type
```

## Semantic Markup Patterns

### Observation Categories
Use these categories to structure factual content:

- **[technical-finding]**: Specific technical discoveries
- **[insight]**: Understanding or connection between concepts
- **[pattern]**: Recurring behavior or structure
- **[requirement]**: Must-have condition or constraint
- **[issue]**: Problem or challenge encountered
- **[decision]**: Choice made and rationale
- **[idea]**: Creative thought or possibility
- **[trend]**: Directional change or evolution
- **[capability]**: Ability or competency
- **[limitation]**: Constraint or boundary

### Relation Types
Use these to connect entities semantically:

- **relates_to**: General semantic connection
- **part_of**: Hierarchical membership
- **enables**: Capability or permission relationship
- **requires**: Dependency relationship
- **implements**: Realization of abstract concept
- **emerges_from**: Bottom-up derivation
- **connects_to**: Peer-level association
- **solves**: Problem-solution relationship
- **supports**: Foundational relationship
- **extends**: Enhancement or expansion

### Forward References
- Link to entities that don't exist yet: `[[Future Concept]]`
- AI systems can resolve these when entities are created
- Enables bottom-up knowledge development
- Supports emergent structure discovery

## Tag Taxonomy

### Hierarchical Tag Structure
1. **Domain** (Required): `ai-systems`, `cloud-infrastructure`, `personal-development`
2. **Type** (Required): `note`, `moc`, `project`, `area`, `resource`
3. **Technology** (If applicable): `azure`, `terraform`, `kubernetes`, `python`
4. **Specifics** (2-3 tags): `networking`, `automation`, `troubleshooting`

### Tag Format Rules
- Lowercase with hyphens: `cloud-infrastructure`
- No spaces or underscores: `ai-systems` not `AI Systems` or `ai_systems`
- 3-6 tags total for optimal discoverability
- Consistent across related content

### Domain Examples
- **Technical**: `cloud-infrastructure`, `ai-systems`, `development-tools`
- **Professional**: `systems-engineering`, `project-management`, `team-leadership`
- **Personal**: `personal-development`, `health-wellness`, `financial-planning`

## Linking Standards

### Internal Links
- Use double brackets: `[[Note Title]]`
- Link to exact titles for reliability
- Create forward references freely
- Prefer descriptive titles over file paths

### External Links
- Standard Markdown: `[Description](URL)`
- Include access date for references
- Prefer authoritative sources
- Archive important external content locally when possible

## Quality Indicators

### High-Quality Notes
- ✅ Clear, specific title
- ✅ Rich frontmatter with all required fields
- ✅ 2-4 semantic observations
- ✅ 2-3 relationship connections
- ✅ Consistent tag hierarchy
- ✅ Links to 2+ related entities

### High-Quality MOCs
- ✅ Clear overview of knowledge cluster
- ✅ Logical organization of linked notes
- ✅ Insights visible only through MOC perspective
- ✅ Identification of patterns and gaps
- ✅ Forward-looking project opportunities
- ✅ Connections to related MOCs

## Tool Integration

### Obsidian
- Graph view shows semantic relationships
- Tags panel enables faceted discovery
- Backlinks reveal implicit connections
- Search includes frontmatter fields

### Notion
- Database views filter by frontmatter properties
- Relations link between different content types
- Templates enforce consistent structure
- Formulas calculate metadata insights

### Basic Memory / Custom Tools
- Semantic parsing extracts observations and relations
- Knowledge graph visualization
- AI-powered connection suggestions
- Automated insight generation

### Plain Text / Any Tool
- Standard Markdown ensures readability
- YAML frontmatter provides structure
- Semantic patterns enable manual analysis
- Full content portability

## Migration and Maintenance

### Converting Existing Content
1. Add INMPARA frontmatter to existing notes
2. Structure content using semantic patterns
3. Add observations and relations
4. Create forward references to missing entities
5. Organize into INMPARA folder structure

### Ongoing Maintenance
- Update 'updated' field when modifying content
- Review and refine tags quarterly
- Validate links during weekly reviews
- Archive completed projects and outdated resources

### Quality Assurance
- Regular frontmatter validation
- Link integrity checking
- Tag consistency review
- Semantic density assessment

---

**Remember**: The goal is sustainable knowledge building with maximum AI enhancement potential while maintaining complete tool independence.

## Tags
#inmpara #formatting #standards #knowledge-management #ai-enhancement
