---
name: meta-ad-campaign-framework
description: >
  Use this skill when an agent needs to design or validate a Meta (Facebook & Instagram)
  ad campaign using industry-grade frameworks that comply with the latest Meta Ads
  platform updates and policies.
inputs:
  business_objective:
    type: string
    description: Primary Meta Ads objective (e.g., leads, purchases, app_installs).
  target_audience:
    type: object
    properties:
      geography: string
      age_range: string
      interests: array
      custom_audiences: array
      lookalike_sources: array
  offer_details:
    type: object
    properties:
      offer_type: string
      value_proposition: string
      landing_page_url: string
  budget_and_timeline:
    type: object
    properties:
      daily_budget: number
      campaign_duration_days: number
  creative_inputs:
    type: object
    properties:
      available_formats: array
      primary_messages: array
  tracking_setup:
    type: object
    properties:
      pixel_installed: boolean
      conversion_events: array
outputs:
  campaign_blueprint:
    type: object
    properties:
      campaign_structure: object
      ad_set_structure: object
      creative_requirements: object
      tracking_requirements: object
  compliance_notes:
    type: array
constraints:
  - Must not decide business or marketing strategy.
  - Must not generate ad copy or creative assets.
  - Must not modify budgets beyond provided values.
  - Must not assume unavailable Meta Ads features.
  - Must rely only on official Meta update sources.
---

## Preconditions

- The agent has already selected Meta Ads as the execution channel.
- All required inputs are present and syntactically valid.
- Access to official Meta Ads documentation is available.

## Execution Steps

1. **Validate Campaign Objective**
   - Invoke `scripts/validate-meta-objective.md`
   - Confirm objective is active, supported, and not deprecated.

2. **Validate Audience Eligibility**
   - Invoke `scripts/audience-eligibility-check.md`
   - Remove or flag disallowed targeting parameters.
   - Enforce current detailed targeting and privacy constraints.

3. **Map Objective to Campaign Framework**
   - Create a single-objective campaign.
   - Define ad sets by audience segmentation logic only.
   - Ensure no cross-objective contamination.

4. **Apply Meta Automation Rules**
   - Enforce Advantage+ defaults where required.
   - Validate placement logic against current Meta recommendations.
   - Do not override system-mandated automations.

5. **Define Creative Requirements**
   - Specify required formats, ratios, and durations.
   - Map creative formats to placements.
   - Do not generate creative content.

6. **Validate Tracking and Measurement**
   - Invoke `scripts/tracking-requirements-check.md`
   - Validate pixel/SDK presence.
   - Confirm conversion event availability.
   - Validate attribution window compatibility.

7. **Generate Compliance Notes**
   - List all applied Meta policy and system checks.
   - Flag any partial or blocked configurations.

8. **Validate Output Schema**
   - Validate final output against `assets/campaign-structure-schema.json`.

## Postconditions

- A complete Meta Ads campaign blueprint is generated.
- Campaign structure complies with current Meta Ads rules.
- All platform constraints and updates are reflected.
- No strategic or subjective decisions are introduced.

## Failure Modes and Handling

- **Unsupported Objective**
  - Stop execution and return a clear error.
- **Invalid or Restricted Targeting**
  - Flag offending parameters and request correction.
- **Missing Tracking Setup**
  - Produce partial output with blocking warnings.
- **Schema Validation Failure**
  - Reject output and return schema mismatch details.
