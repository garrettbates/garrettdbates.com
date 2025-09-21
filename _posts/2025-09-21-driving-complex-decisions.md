---
layout: post
title: Driving Complex Decisions
date: 2025-09-21 00:00 -0800
read_time: 10 min read
lucidchart:
    link: https://lucid.app/folder/invitations/accept?invitationId=inv_86fad235-3733-4655-9613-412a096e2ec2
    title: Lucidchart Folder
    image: /assets/driving-complex-decisions/lucidchart-folder.png
moreFromAuthor:
  -
    postSlug: anything-but-option-b
  - 
    postSlug: why-use-onion-layering
  -
    postSlug: why-disallow-package-within-the-class-name
nounProjectIcons:
  - 
    link: https://thenounproject.com/icon/888647/
    name: Arrow
  -
    link: https://thenounproject.com/icon/4938954/
    name: Shine
---

<div style="display:flex;justify-content:center;padding:20px 0">
    <a href="https://www.youtube.com/watch?v=x2IP6_jxYD4" target="_blank">
        <img src="/assets/driving-complex-decisions/more-is-lost-by-indecision-than-wrong-decision.png" alt="More is lost by indecision than by wrong decision" style="max-height:558px">
    </a>
</div>

Picture this: You're an up and coming engineer fresh off a big win. In doing so you've won the trust of your peers and leaders, and also proven your readiness for bigger challenges. You are thrown into an ambiguous space with a few open questions that will dictate the direction of thousands of hours of engineering time. The decisions you make now will meaningfully impact the business and hundreds of people's day to day lives. You are now accountable for this - proudly so. But how do you actually get this done? What are the steps? And how do you know if you are over analyzing vs. being reckless? How do you push through conflicting views from your trusted teammates?

This article lays out a structured approach for driving complex decisions quickly, collaboratively, and effectively. We’ll cover mental models, practical steps, and pitfalls to avoid so you can lead with confidence in moments that truly matter.

## Many Paths, Not One

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/driving-complex-decisions/many-paths-to-the-promise-land.svg" alt="Many paths to the promise land">
</div>

First let's take a step back and acknowledge that solving technical challenges affords an unexpected amount of artistic freedom. There are typically many paths - even if we can only just barely see one of them. Our primary goal as the driver is to navigate through and identify the top contenders utilizing the full potential of the team.

## Pitfall #1: Chasing the “Golden Path”

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/driving-complex-decisions/the-golden-path.svg" alt="Many paths to the promise land">
</div>

The first major pitfall is pursuing a "golden path". It involves a mental model where we underemphasize that there are many solutions and try to focus in on what is the single best and most optimal solution to the problem. This approach provides an easy mental escape to procrastinate making progress on the decision by making the discovery of this path a pre-requisite to any other action.

The biggest indicator that you might be trapped in pursuing the golden path would be spending multiple days ideating before pulling in teammates for feedback. The more time you spend alone the more committed you get to an idea that very well may be ripped to shreds by the group at large. Your mindset for the first pass should be getting to "a solution" and not "the solution". Easier said than done as it can be tough to balance what is "enough" since too little thought can end up being a waste of your teams time.

Remember - you are not accountable for finding the golden path as part of your first proposal! The idea is that you want to land as close as possible to the golden path at the end of the decision making process, and the best way to do so is by incorporating as many minds as you can for as long as you can. This should shift your mindset towards trying to pump out your first proposal to the group as fast as possible as your first move.

## The Provocation Path

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/driving-complex-decisions/the-provocation-path.svg" alt="Provoke your team">
</div>

I like to call all of my initial proposals "provocations". It helps me mentally to distance myself from the solution in public - as if I didn't spend 8 hours last night refining and tweaking it. It is also intended to acknowledge that it may offend some sensibilities within the group and that I am welcoming to feedback. This solution path may not be optimal or glamorous but it gets the job done and I'm able to to defend it against basic inquiry.

Embrace that this path will likely have some rough spots you are not proud of. Colloqially I'll refer to this as "throwing out some garbage solution" to encourage others to get something out there. Of course it should have a basic level of diligence - but many engineers, especially those with a newly increased scope of responsibility tend to overestimate just how much diligence should be put in for the first pass. Remember this is not the final solution - it is just to get the discussion started. Something basic like a few sequence diagrams is typically enough.

Once your provocation is ready you should round up all of those who are significantly impacted by the decision and clearly articulate your approach. Once they fully understand your proposal and why you chose it you can move on to the next step.

## Adjusting The Path: Harnessing the Team

> “It is the mark of an educated mind to be able to entertain a thought without accepting it.” -Aristotle

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/driving-complex-decisions/adjusting-the-path.svg" alt="Adjusting the path" >
</div>

By this point you've laid out at least one solution for the team to consider. There should be relief amongst the team that independent of anything else - at least there exists one path forward. Now is the time to pull out the full potential of the team and incorporate their thoughts into the strategy. Prepare your ego since this is the point at which your provocation proposal gets ripped to shreds.

Lean into every alternative and criticism and seek to understand them in depth. Write down the points that people believe should influence the decision. Gracefully navigate [emotionally charged objections](/anything-but-option-b). Follow up on any recommended data analysis. The final output should look something like this:

```
Options for <decision>:
    A: <short description>
        Pros:
            * ...
        Cons:
            * ...
    B: <short description>
        Pros:
            ...
        Cons:
            ...
```

The primary outcome here is shared understanding amongst the team. As the team gains clarity expect and embrace that your own position on what the right path forward is may shift throughout the process. This is a good thing! 

It is a common pitfall to not know when this collaboration phase is over. Note that getting to a shared recommendation is explicitly not a part of this phase. You do not have to circle until everyone agrees. You solely need to ensure that the the group has full understanding of all options + pros/cons and also that the group has no further options + pros/cons to contribute.

## Picking a Path: Making the Call
The easiest part of the process for the driver. Identify an accountable leader and have them choose based on the due diligence of the team. As a rule of thumb, I try to make the approver the person who has the most to lose if the decision is suboptimal. Let the approver state their intended choice before finalizing it and allow members of the team a last opportunity to filibuster.

## Before and After: Two Timelines

### A Common (Flawed) Timeline

<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/driving-complex-decisions/typical-complex-decision-timeline.svg" alt="Typical complex decision timeline">
</div>

I have seen a huge number of engineers follow the above sequence. They conflate their first proposal with being the probable final direction leaving barely any time for collaboration. Once inevitable misalignment arises there is a scramble to try and force the group into accepting the provocation proposal, potentially even escalating when it doesn't go their way. The escalation happens prematurely where there is still unanswered data analysis or options which haven't been considered. Finally more scrambling until a decision has to be made to unblock execution. Yikes.

### An Idealized Timeline


<div style="display:flex;justify-content:center;padding:20px 0">
    <img src="/assets/driving-complex-decisions/ideal-complex-decision-timeline.svg" alt="Ideal complex decision timeline">
</div>

Notice how there is incredible pressure in this timeline to pump out a provocation to the group quickly. There is laser focus on procuring all available options + pros/cons from the group with minimal attempt at forcing alignment. All relevant data is collected prior to a final escalation to the approver.

## A Practical Checklist 

Here’s a structured **10-step checklist** to guide your next complex decision:

| Step Number | Step Name | Description | Acceptance Criteria | Maximum Timeframe |
|-------------|----------------------|-------------|-------------------|---------------------|
| 1 | Provocation Creation | Driver creates an initial proposal to kickstart discussion | At least one viable solution is documented and ready to share. Sequence diagram between relevant systems created. Driver can defend the proposal against basic inquiry. | 1-2 days |
| 2 | Initial Provocation Shareout | Driver presents the initial proposal to stakeholders | All relevant stakeholders have been briefed on the provocation proposal | 1 day |
| 3 | Provocation Understanding | Driver follows up until stakeholders comprehend the initial proposal | Questions about the provocation have been answered; All stakeholders explicitly confirm they understand the baseline option. | 1-2 days |
| 4 | Stakeholder Brainstorms | Driver facilitates sessions to gather alternatives and input | Every stakeholder acknowledges they understand every option and its corresponding pros/cons. The team has no further options or pros/cons to add to the discussion. Salient points have been written down for future reference. | 1-2 days |
| 5 | Stakeholder Brainstorm Follow Ups | Driver gets insights from subject matter experts and completes data investigations | All stakeholders explicitly confirm there are no outstanding follow ups necessary to make the decision | 2-3 days |
| 6 | Stakeholder Brainstorm Distillation | Driver organizes the teams thoughts and ideas | All options and corresponding pros/cons have been written down in a way that is easily consumable at a glance; distillation provided to the approver | 1 day |
| 7 | Approver Declares Intent | Approver provides a preview of the option they plan to choose | Approver informs the team of what decision they plan on making | 1 day |
| 8 | Approval Fillibuster | Approver facilitates getting feedback from team members before finalizing the decision | All team members acknowledge that the approver adequately understands the full implications of their intended decision | 1 day |
| 9 | Decision Made | Approver makes the final call | Stakeholders informed verbally; execution effectively unblocked | 1 day |
| 10 | Cascade Broadly | Driver documents the decision for broad consumption | Decision recorded in conjunction with approver signature; Link to decision shared with front line engineers | 1-2 days |

Notice how it can take upwards of 14 days to get to an approval after the initial provocation even with an idealized set of checkpoints. This really leaves no buffer for the driver to dilly dally in constructing the provocation proposal. Rip the band-aid off and start those stakeholder brainstorm discussions ASAP!

# Final Thoughts
Leading complex decisions is one of engineering's most profound privileges and responsibilities. When you're entrusted with choices that will shape thousands of hours of work and impact hundreds of lives, you're not just solving technical problems; you're stewarding the future direction of your team and organization.

The path forward isn't about finding perfection—it's about having the courage to start imperfectly. Your first "provocation" doesn't need to be brilliant; it needs to be brave. It's the spark that ignites collective wisdom, the catalyst that transforms individual uncertainty into shared clarity.

Remember that the most elegant solutions emerge not from isolation, but from the beautiful messiness of collaboration. When you invite others to tear apart your initial ideas, you're not showing weakness—you're demonstrating the kind of intellectual humility that builds extraordinary teams. Every criticism absorbed, every alternative explored, every ego set aside in service of the greater good brings you closer to something truly meaningful.

The structured approach outlined here isn't just a process—it's a pathway to growth. Each complex decision you navigate with intentionality builds your capacity to handle even greater challenges. You're not just driving decisions; you're developing the judgment, resilience, and leadership skills that will define your career.

Most importantly, embrace the weight of these moments. The decisions you make ripple through your organization, affecting how people work, what they build, and ultimately, how they feel about their contribution to something larger than themselves. That's both humbling and incredibly empowering.

Trust the process, trust your team, and trust yourself. More is indeed lost by indecision than by wrong decision—but with thoughtful collaboration and courageous action, you'll find that most of your decisions won't be wrong at all. They'll be exactly what your team needed, when they needed it most.
