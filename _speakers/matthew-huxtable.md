---
name: Matthew Huxtable
title: Site Reliability Engineer
company: Sparx
talk-title: The forgotten musketeer - availability is a security concern too!
headshot: /assets/images/headshots/head-matthew-huxtable.jpg
track: 3
timeslot: "16.00"
type: Talk, 45 minutes
level: 1
twitter:
 - matthewhuxtable
# linkedin: 
takeaways:
 - An understanding of the principles of Site Reliability Engineering, its suitability as a modern approach to operations (and not just by technology/development companies!), and practical steps for its implementation
 - I'll answer the question "Why is production more broken than we think?", briefly consider external cyber threats (although these are well-covered elsewhere), and address fundamental fallacies with many approaches to system/software quality assurance/testing
 - Provide practical steps for discussing and promoting availability as a first-class concern with technology leads, product owners, and other key decision makers to ensure it receives the visibility it requires to allow strategy to be set and risks understood.
---

In today's digital world, data is the new currency. We invest significant effort in safeguarding and protecting our customers' data, yet all too often fail to fully consider the other fundamental pillar of information security: availability. The uptime of our systems is no longer the sole remit of engineers; organisations add value through the provision of always-on technology platforms, and rapidly fall into obsolescence when such systems are unavailable.

Risks to our system availability abound throughout the development lifecycle, and often originate from unexpected sources. We protect against malicious third-party actors despite the significant risk associated with increasingly sophisticated software systems to which our developers deploy changes multiple times per day.

Originally pioneered at Google, <strong>Site Reliability Engineering</strong> is the discipline which automates processes and builds systems to ensure a pragmatic approach to this risk in the development cycle. We know systems fail in spite of human effort, not because of it, so we continually optimise and refine the boring parts to promote a pragmatic approach to risk throughout the development cycle. 

In this talk, I will share my experience implementing SRE in a small organisation to promote availability, discuss the theoretical properties of reliability engineering, and provide practical guidance on building systems which cope well with continual change.

{% include speakers-takeaways.html %}