---
name: meta-ad-campaign-framework
description: >
  Build and validate Meta (Facebook & Instagram) ad campaign structures using
  industry-grade frameworks. ALWAYS use this skill when creating, reviewing,
  or validating Meta Ads campaign setups for compliance with current Meta Ads
  platform rules and updates.
last-updated: 2026-02-01
allowed-tools: None
---

# Meta Ad Campaign Framework Skill

Builds a Meta Ads campaign blueprint that complies with current platform objectives,
targeting rules, automation defaults, and tracking requirements.

This skill does NOT decide strategy, write ads, optimize performance, or publish campaigns.

> **Freshness check**: If more than 30 days have passed since the `last-updated` date,
inform the user that Meta Ads platform rules may have changed and recommend verifying
against the official Meta Ads documentation before execution.

## Keeping This Skill Updated

**Primary sources (authoritative only):**
- Meta Business Help Center
- Meta Ads release notes
- Meta for Developers documentation
- Official Meta Business blog

This skill must be updated whenever:
- Campaign objectives are deprecated or renamed
- Targeting or privacy rules change
- Advantage+ or automation defaults are modified
- Attribution or tracking requirements change

## Setup

Before using this skill, ensure:

1. **Inputs are final**
   - Business objective is already chosen
   - Audience definition is finalized
   - Budget and timeline are fixed
   - Tracking setup status is known

2. **No strategy decisions required**
   - If the user asks *what* objective, audience, or budget to use, stop.
   - This skill only executes structure validation and construction.

## When to Use

Use this skill when:
- A Meta Ads campaign structure must be created or reviewed
- Platform compliance must be enforced
- The agent needs a deterministic campaign blueprint
- The campaign must align with current Meta Ads system behavior

Do NOT use this skill to:
- Decide funnels, messaging, or creative angles
- Generate ad copy or visuals
- Optimize or iterate live campaigns

## Workflow

Follow this workflow exactly and in order.

### 1. Validate Campaign Objective
- Confirm the objective exists and is currently supported
- Reject deprecated or merged objectives
- Verify compatibility with provided tracking inputs

### 2. Validate Audience Eligibility
- Validate geography and age limits
- Check interest and behavior targeting availability
- Validate custom and lookalike audience sources
- Enforce sensitive-category and privacy restrictions

If any audience parameter is invalid, flag it and stop.

### 3. Create Campaign Structure
- Create a single-objective campaign
- Define ad sets strictly by audience segmentation
- Ensure no cross-objective or mixed-purpose ad sets

### 4. Apply Meta Platform Defaults
- Enforce required Advantage+ behaviors
- Validate placement configuration
- Do not override mandatory automation rules

### 5. Define Creative Requirements
- Specify allowed formats per placement
- Define aspect ratios, duration limits, and file constraints
- Do NOT generate creative content

### 6. Validate Tracking Setup
- Confirm pixel or SDK installation status
- Validate required conversion events
- Verify attribution window compatibility

If tracking is incomplete, return a blocking warning.

### 7. Generate Compliance Notes
- List all Meta policy checks applied
- Flag limitations, missing inputs, or blocked configurations

### 8. Final Validation
- Ensure output matches the required campaign blueprint structure
- Reject output if structural validation fails

## Output

This skill produces:
- A Meta Ads campaign blueprint
- A list of applied compliance checks and warnings

## Automation Guidelines

- Do not assume feature availability
- Do not bypass platform safeguards
- Do not simulate publishing or budget allocation
- Prefer blocking warnings over partial execution

When in doubt, stop and request corrected inputs.
