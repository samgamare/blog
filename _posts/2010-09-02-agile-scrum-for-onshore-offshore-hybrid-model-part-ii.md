---
title: 'Agile/Scrum for onshore/offshore hybrid model – Part II'
date: '2010-09-02T20:11:00+05:30'
author: 'Sam Gamare'
excerpt: 'Do''s and Don''t s for Agile / Scrum teams for what works with respect to roles, meetings, processes and tools.'
layout: post
image: /assets/images/icons/icon-agile-part-ii.svg
permalink: /blog/2010/09/02/agile-scrum-for-onshore-offshore-hybrid-model-part-ii/

tags:
    - Agile
    - Backlog
    - OffShore
    - OnShore
    - 'Planning Poker'
    - Scrum
    - Sprint
    - Story
---
<div class="header-image-wrapper">
  <img src="/assets/images/agile-global-teams.png" alt="Agile Global Teams" width="90%">
</div><br>


Continued from [Agile/Scrum for onshore/offshore hybrid model – Part I](/blog/2010/09/01/agile-scrum-for-onshore-offshore-hybrid-model-part-i/)

In the previous article we discussed about Roles, Meetings, Processes, and Tools to use in our hybrid model. In this article we will briefly go over the do’s and don’ts that will get us moving in the RIGHT direction.

**Do’s**

• Offshore Scrum Master can be a traditional PM, but has to have a “Servant leader and Facilitator” mindset.

• For a new Scrum team, it is important to understand the ramp up time for resources, and various environment setup and continuous integration setup – before 1st Dev Sprint begins.

• Automated Continuous Integration (CruiseControl/Hudson + SVN/CVS + Maven Integration).

• Automated Testing, possibly including load testing if feasible.

• Access to Product Owner (or a proxy at least) is very important to the Delivery Team’s success.

• Measure each teams velocity after each sprint and identify positives and negatives to ripple to other teams. This ensures that we can carry best practices from productive teams to other teams, while is also ensures the “slower” team gets positive feedback to do the right things to increase productivity.

• Bugs are not to be automatically fixed in the following sprint, rather they should be prioritized to the appropriate future Sprint.

• Scrum Teams should be grouped/assembled on high level functionality (group of closely related features).

• Following Agile/Scrum does not excuse us from documentation, rather the documentation happens iteratively over multiple sprints.

• Co-mingling: Ideally Agile/Scrum prefers co-location, however in today’s day and age that may not always be feasible. It is useful to consider sending the US lead to India and vice versa. The comfort and understanding within the team it achieves is worth the plane ticket in matter of few weeks.

• Define backlog feature items with the following attributes:

o Mandatory Items: Description, Rank/Priority, Complexity/Cost/Size (Story Points).

o Preferred Items: Acceptance Criteria (including NFR’s), Owner, Parent Item, Tests, Dependencies

**Don’ts**

• Passive agreements on either side should be taken note of and cross confirmations raised.

• Don’t assume requirements available as defined in feature backlog are complete. Its paradoxical in that sense but a feature should not be picked up for development if it is not considered well defined.

• A unfocused scrum team is recipe for disaster or lower output.

• It is probably worth documenting that moving code from Dev to Integration to QA to Staging does not generally happen within one sprint, and unless we have a very well established testing and development environment such a automated move is not advised.

Some of my colleagues have asked me about questions that most fit questions and answer kind of blog. Please stay tuned for the next one of this series.