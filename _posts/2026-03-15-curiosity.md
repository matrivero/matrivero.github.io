---
title: "Curiosity, Obsession, and One Line of Code"
date: 2026-03-15 12:00:00 +0100
#categories: [cybersecurity]
#tags: [inicio]
---

# Curiosity, Obsession, and One Line of Code

## From The Cuckoo’s Egg to the xz Backdoor

In the early 1980s, an astronomer-turned-sysadmin noticed a 75-cent accounting discrepancy. In 2024, a software engineer noticed a barely perceptible increase in CPU usage during SSH logins.

Different decades. Different systems. Same story.

Reading [The Cuckoo's Egg by Clifford Stoll](https://en.wikipedia.org/wiki/The_Cuckoo%27s_Egg_(book)) initially felt like diving into computer-security prehistory: dial-up modems, mainframes, international espionage. But when the [xz backdoor](https://en.wikipedia.org/wiki/XZ_Utils_backdoor) was discovered in the widely used XZ Utils package in 2024 by [Andres Freund](https://x.com/AndresFreundTec), I couldn’t ignore how closely these two stories rhyme.

At their core, both are about curiosity. And about the kind of constancy most people would consider unnecessary.

## The 75-Cent Clue

In The Cuckoo’s Egg, Stoll describes how a trivial accounting mismatch (75 cents) triggered an investigation that eventually uncovered a foreign hacker moving through U.S. military and research networks.

What still amazes me isn’t the scale of the breach. It’s the scale of the anomaly.

Seventy-five cents.

Almost anyone else would have shrugged, patched the ledger, and moved on. Stoll didn’t. He followed it, not because he knew something big was hiding there, but because it didn’t make sense.

That refusal to ignore discomfort is rare.

## The Millisecond Latency

Fast-forward to 2024. The xz backdoor was embedded deep in the release process of a core compression library used by major Linux distributions. It was subtle, sophisticated, and patient: the apparent outcome of long-term social engineering targeting a project maintainer.

And it wasn’t discovered through a formal security audit.

It was discovered because Andres Freund noticed something off: SSH logins were slightly slower. CPU usage was just a bit higher than expected.

Again, tiny anomaly.

Instead of dismissing it as noise, he profiled the system. He compared binaries. He traced execution paths. He reconstructed how malicious code had been injected in a way that bypassed source-level review.

If that millisecond delay had been ignored, the consequences could have been catastrophic.

## Treating Anomalies as Research Problems

One of the most important moments in The Cuckoo’s Egg has nothing to do with hacking techniques. It’s a conversation Stoll has with nobel-prize winner [Luis Alvarez](https://en.wikipedia.org/wiki/Luis_Walter_Alvarez).

Stoll is exhausted and frustrated. He’s chasing strange behavior across systems with no clear finish line. Alvarez reframes the entire situation with deceptively simple advice: treat it like a research problem.

Not a bug.
Not a ticket.
Not an operational nuisance.

A research problem.

That framing changes everything.

In research, you don’t start with a solution. You start with curiosity. You observe. You form hypotheses. You test them. You discard them. You refine your mental model. And you accept that progress may be slow, nonlinear, and uncertain.

Implicit in Alvarez’s advice is a deeper principle: fall in love with the problem, not with the solution.

Once Stoll adopts this mindset, he stops trying to “close” the issue and starts trying to understand it. The investigation becomes sustainable, not because it’s easy, but because it’s intellectually honest.

## The Same Mindset in the xz Backdoor Discovery

Seen through this lens, the xz backdoor discovery becomes even more striking.

Freund didn’t jump to conclusions. He didn’t assume malware. He didn’t chase a fix. Instead, he stayed with the problem:

Why is CPU usage higher?

Why does SSH latency increase only under certain conditions?

Why do the build artifacts differ from expectations?

Why does behavior diverge subtly but consistently?

That’s research thinking.

The moment you commit emotionally to a solution, you narrow your field of vision. When you commit to understanding the problem, you stay open to inconvenient truths. This is exactly what connects Freund’s investigation to Stoll’s: decades apart, wildly different technology, identical intellectual posture.

## Persistence in the Face of Ambiguity

Another parallel that stands out is duration.

Stoll spent months manually tracing network activity, logging sessions, coordinating across time zones and institutions, often without institutional support.

Freund didn’t spend an afternoon on a performance regression. He invested days into reverse-engineering build processes and diffing binaries, with no guarantee that anything serious would emerge.

Neither investigation was linear. Neither came with validation along the way. Persistence here wasn’t cinematic heroism, it was quiet, methodical, and occasionally obsessive.

## The Power of Technical Intuition

Curiosity alone isn’t enough. Both cases required technical intuition, the ability to sense when “normal” isn’t normal.

Stoll understood that accounting discrepancies can reveal structural truths. Freund understood that unexplained regressions in core infrastructure are rarely random.

This intuition doesn’t come from textbooks. It’s earned through years of friction: systems breaking, assumptions failing, models drifting, deployments behaving strangely. Over time, you develop a feel for when reality is lying to you.

## The Human Factor in Both Attacks

There’s also an uncomfortable similarity on the attacker’s side.

In The Cuckoo’s Egg, trust in academic and research networks is exploited. In the xz case, trust within the open-source community appears to have been carefully cultivated over years.

These weren’t purely technical attacks. They were social.

And they were stopped not by automation, but by individuals paying attention.

## What This Means for Those of Us Building Systems

Working with complex systems (APIs, ML pipelines, data platforms, infrastructure) I find this deeply instructive.

Most failures don’t announce themselves loudly.
They whisper.

A slight drift in metrics.
A strange log entry.
A model that behaves just a bit off-distribution.
A service that “feels” slower.

The pressure is always the same: fix it quickly and move on.

But these stories remind me that security and reliability are often defended not by frameworks or dashboards, but by people who decide that small inconsistencies deserve time.

## Constancy as a Security Strategy

What I ultimately take from both stories isn’t paranoia.

It’s constancy.

The willingness to:

Sit with ambiguity.

Measure carefully.

Compare expectation to reality.

Follow anomalies without knowing where they lead.

Keep going even when there’s no immediate payoff.

Tooling didn’t catch the 75-cent discrepancy.
Tooling didn’t catch the xz backdoor.

People did.

Curious, persistent people who fell in love with the problem.

## Final Reflection

When I first finished The Cuckoo’s Egg, I thought it was a story about early hacking culture. After the xz incident, I realized it’s really a story about mindset.

Technology evolves. Infrastructure scales. Attack surfaces multiply.

But the core defense remains unchanged.

Someone notices something small.
Someone refuses to ignore it.
Someone treats it as a research problem instead of an inconvenience.

And sometimes, that’s enough to stop something catastrophic.

That’s not just a lesson about security.

It’s a lesson about how understanding actually happen.
