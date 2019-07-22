---
name: Olly Stephens
title: DevSecOps Architect
company: Adarga
talk-title: Policy as code - why you should, how you can
headshot: /assets/images/headshots/head-olly-stephens.jpg
track: "3"
timeslot: "14.00"
type: Talk, 45 minutes
level: 1
twitter:
 - ollystep
# linkedin: 
takeaways:
 - An introduction to policy as code, OPA and the "Rego" language.
 - Practical examples of using these to ensure infrastructure configuration (specifically Terraform and Kubernetes manifests) conform to policies.

---
All organizations have policies. Policies are essential to the long-term success of organizations because they encode important knowledge about how to comply with legal or security requirements, work within technical constraints, avoid repeating mistakes, and so on.

And more and more these days, organizations are codifying all of their infrastructure. The mantra "everything as code". So why would you leave your policies languishing on a wiki page or in a word document?

This talk will take a look at Open Policy Agent - a toolset for writing policies in code that's being incubated by CNCF, and is already integrated into a number of different areas. It will focus on using OPA-based tooling to check conformity of configuration files. As we move to a world where all of our infrastructure is defined declaratively and applied automatically, whilst development, security and operational roles are merged, the ability to enforce policy becomes more important.

We'll also look at some of the other benefits of this approach, such as the ability to write unit tests for your policies.

{% include speakers-takeaways.html %}

<h3>Bio</h3>
Olly started his career as an EDA software engineer, writing RTL and gate-level simulators, then joined ARM in 1999 to focus on engineering productivity. Whilst there he was responsible for the overall architecture of their engineering platform, as well as leading exploration into future innovations/evolutions such as cloud-based engineering, big data workflows, and infrastructure as code. 

Olly joined Adarga in December 2018, to lead the devsecops practice and continue his work on robust cloud-native high performant architectures. He has particular interest in all forms of workflow orchestration, as well as a general interest in data-driven story telling.