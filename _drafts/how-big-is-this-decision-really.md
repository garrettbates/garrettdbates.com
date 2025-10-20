---
layout: post
title: "How Big Is This Decision, Really?"
date: 2025-10-18 00:42 -0700
image: /assets/how-big-is-this-decision-really/how-big-is-this-decision-really.png
---

🎬
> You have no idea the physical toll three vasectomies have on a person! - [Michael Scott](https://www.youtube.com/watch?v=2hshkdneE8o){:target="_blank"}

<div style="display:flex;justify-content:center;padding:20px 0">
    <a href="https://www.youtube.com/watch?v=2hshkdneE8o" target="_blank">
        <img src="/assets/how-big-is-this-decision-really/snip-snap-snip-snap.gif" alt="Snip snap snip snap" style="max-height:558px">
    </a>
</div>

Some decisions require just a little bit more diligence than others. However, it can be tough to know just *how much effort* to put in. Shoot from the hip? Or go through the wringer pulling in everyone and their mother to ensure alignment?

In this post, we’ll walk through a simple framework to help you right-size your effort before diving in. You’ll find four levels of decision scope — from small, single-team calls to large, cross-org investments — each with guidance on typical timelines, who to involve, and how to document outcomes.

If you haven’t read [Driving Complex Decisions](/driving-complex-decisions)
, it lays out the foundational building blocks and mental models that this post builds upon. Here, we’ll focus on concrete examples and how to tailor the process by decision size.

## 🧭 How to use this guide
Before diving in, here’s a quick map of the four “levels” of decision scope we’ll cover — from small, self-contained changes to major cross-org investments. Use this as a reference to gauge how much diligence and coordination your upcoming decision likely needs.

| **Decision Level** | **Scope**                                  | **Approx. Timeline** | **Primary Focus**                                         |
| ------------------ | ------------------------------------------ | -------------------- | --------------------------------------------------------- |
| **Level 1**        | Change within a single team                | 1–3 days             | Context gathering & team alignment                        |
| **Level 2**        | Adjustment between already connected teams | 4–6 days             | Shared understanding & API/contract clarity               |
| **Level 3**        | First-time connection between two teams    | ~2 weeks             | Defining roles, responsibilities & integration approach   |
| **Level 4**        | Introducing a new team or capability       | 3–4 weeks            | Cross-functional design & exec-level investment alignment |

Each level builds on the one before it — expanding the scope, the number of voices involved, and the degree of rigor required. Think of them less as rigid rules and more as calibration points. With that context in mind, let’s start at the smallest scale: a significant change within a single team’s boundary.

## Level 1: Significant change within a single team's boundary

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/how-big-is-this-decision-really/within-single-teams-boundary.svg" alt="Significant change within a single team's boundary">
</div>

### Defining characteristics
* Lives entirely within one team's domain (~10 people)
* Lasting and consequential outcome for that team

### Approximate timeline (~1-3 days)
<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/how-big-is-this-decision-really/single-team-timeline.png" alt="Single team timeline">
</div>

### Key takeaways
* Oftentimes decision can be made with **a single team meeting** and some prior diligence in gathering context.
  * Example pre-meeting preparation to accelerate:
    * Triggering reason why this decision needs to be made now
    * Historical context of what will change
    * Options considered and recommendation
* Account for the possibility of needing to circle back at least once with new research after the initial shareout.
* Decision should be recorded for future team reference (e.g. as an [ADR](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions))

## Level 2: Modifying a contract between already connected teams

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/how-big-is-this-decision-really/modifying-contract-between-already-connected-teams.svg" alt="Modifying contract between already connected teams">
</div>

### Defining characteristics
* The teams already have an established relationship and integration
* There exists dependencies between the teams for complete rollout of the change

### Approximate timeline (~4-6 days)

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/how-big-is-this-decision-really/modifying-contract-already-connected-teams-timeline.svg" alt="Modifying contract between already connected teams">
</div>

### Key takeaways
* You must talk to and brainstorm with **both teams**
  * Very common transgression to only get alignment with the system undergoing change, start implementation, and get feedback from the consuming team later (big source of snip-snap)
* Focus of your effort should be on **shared understanding** between the teams
  * The final outcome of what the API contract will be is less important than both teams having clarity on **why** the change was made
* Record every salient input made along the way (e.g. pros/cons) so those team members who missed the decision brainstorming can also understand the **why** behind it
    * Any new field being added or updated **must** include **a list** of alternatives considered and a justification for why the field name is optimal (consider what will flow most naturally in conversation, what is most precise, what doesn't collide with other terms, what is part of current ubiquitous language, etc.)


## Level 3: First time connection between two teams

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/how-big-is-this-decision-really/first-time-connection.svg" alt="First time connection between two teams">
</div>

### Defining characteristics
* Near zero collaboration between the teams prior
  * Must navigate differences in priorities, tech stacks, and even vocabulary
* Huge number of possible solutions
* Decision will define the long lasting roles and responsibilities of each team

### Approximate timeline (~2 weeks)

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/how-big-is-this-decision-really/first-time-connection-between-two-teams-timeline.png" alt="First time connection between two teams timeline">
</div>

### Key takeaways
* Preparation prior to team engagement is **necessary** at this scope
  * System integration diagram
  * Sequence diagram
    * Summarize key takeaways of each sequence
* Expect **multiple iterations** with each stakeholder
* Approver should be beyond just each team lead - ensure you escalate your proposal to the **single unifying leader across both teams**
* Decision should be recorded in centralized location for the **entire organization** to discover and review
   
## Level 4: Introducing a new team

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/how-big-is-this-decision-really/introducing-a-new-team.png" alt="Introducing a new team" style="height:300px;">
</div>

### Defining characteristics
* Decision outcome implies significant shifts in **organizational investment**
* Burning unmet need within the organization demanding a new capability
  * Likely multiple teams (3+) which are seeking to use this new teams output
* Huge degree of ambiguity in both **what** and **how** we build/buy

### Approximate timeline (~3-4 weeks)
<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/how-big-is-this-decision-really/introducing-a-new-team-timeline.png" alt="Introducing a new team timeline">
</div>

### Key takeaways
* Must have **complete cross-functional representation** - XD, PM, Engineering
* Big increase in **outward based research** up front
  * Potential clients of the team
  * Build vs. Buy analysis
* Multiple drivers and **parallel provocations**
* Must escalate to **executive level leadership** who has investment authority

## 💡 Closing thoughts
Great decision-making isn’t about moving fast or slow — it’s about moving at the right speed for the scope of impact. Use these levels as a shared language so teams can calibrate together, spend effort where it matters most, and make alignment feel natural instead of forced.