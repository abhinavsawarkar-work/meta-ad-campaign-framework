---
name: meta-ad-campaign-framework
description: >
  Builds and validates a Meta (Facebook and Instagram) ad campaign structure
  using industry-grade frameworks while enforcing compliance with the latest
  official Meta Ads platform updates.
---

# Meta Ad Campaign Framework

Follow these instructions exactly when this skill is activated.  
This skill executes a deterministic process to produce a Meta Ads campaign blueprint.
It does not make strategic decisions, generate creatives, or optimize performance.

## When to Use

Use this skill when:

- A Meta Ads campaign structure must be created or reviewed.
- The campaign must comply with current Meta Ads objectives, targeting rules, and automation defaults.
- All strategic decisions and inputs have already been provided by the calling agent.
- A platform-aligned, execution-ready campaign blueprint is required.

Do not use this skill to:
- Decide marketing strategy, positioning, or budgets.
- Write ad copy or design creatives.
- Optimize or iterate live campaigns.

## Steps

1. **Validate Objective**
   - Confirm the provided objective is currently supported by Meta Ads.
   - Reject deprecated or unavailable objectives.
   - Verify compatibility with tracking inputs.

2. **Validate Audience**
   - Check geography, age range, interests, and audience sources.
   - Enforce current Meta Ads targeting and privacy restrictions.
   - Flag or remove disallowed parameters.

3. **Create Campaign Structure**
   - Generate a single-objective campaign.
   - Define ad sets strictly by audience segmentation.
   - Ensure ads are isolated at the creative level.

4. **Apply Platform Defaults**
   - Enforce required Meta automation and Advantage+ behaviors.
   - Validate placement configuration against current platform rules.
   - Do not override system-mandated settings.

5. **Define Creative Requirements**
   - Specify allowed formats, aspect ratios, and duration constraints.
   - Map creative formats to placements.
   - Do not generate or modify creative content.

6. **Validate Tracking**
   - Confirm pixel or SDK installation.
   - Validate required conversion events.
   - Verify attribution window compatibility.

7. **Generate Compliance Notes**
   - Record all Meta policy and platform checks applied.
   - Flag missing, blocked, or partial configurations.

8. **Validate Output**
   - Ensure the campaign blueprint conforms to the required structure schema.
   - Reject output if structural validation fails.
