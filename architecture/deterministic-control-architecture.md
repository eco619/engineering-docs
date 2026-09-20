# Deterministic Control Architecture

**Status:** Active\
**Document Type:** Foundational Architecture\
**Scope:** eco619 intelligent and autonomous systems

## Purpose

This document defines the architectural direction for deterministic
control within eco619 intelligent and autonomous systems.

The architecture establishes a control boundary between intelligent
reasoning and authority to perform actions. It is intended to support
the Continuous Intelligence Platform (CIP) and future eco619 systems
using autonomous agents, compound AI systems, or other forms of
machine-directed execution.

This document records the engineering problem, architectural intent,
responsibilities, boundaries, and evolution of the concept. It
intentionally does not document implementation details sufficient to
reproduce, bypass, or reverse engineer the control mechanism.

The Deterministic Sentinel described here is an architectural direction
under development, not a completed implementation.

## Engineering Origin

The architecture emerged from a broader engineering question:

> How should an autonomous intelligent system behave when it seeks to
> perform an action that is outside an established boundary?

An intelligent agent can reason, reinterpret instructions, explore
alternatives, ask additional questions, and attempt different approaches
to an objective. Those characteristics are useful for investigation and
problem solving, but they create an important architectural distinction.

The system that reasons about an action should not necessarily be the
system that has final authority to permit that action.

This led to the concept of a deterministic control boundary that does
not negotiate with, adopt the reasoning of, or become persuaded by the
intelligent system requesting an action.

A second problem follows from that separation.

An autonomous system may legitimately enter an activity under valid
authority and later encounter a condition in which its expected path is
no longer available. It may be unable to complete the activity or exit
through the path originally authorized.

At that point, the system must not expand its own authority merely
because doing so appears necessary to escape the condition.

The architecture must therefore address not only authorization before an
action, but continued boundary enforcement, independent confirmation of
authority, containment, recovery, and escalation after autonomous
activity has begun.

## Foundational Principle

> Intelligent reasoning and authority to act are separate engineering
> responsibilities.

An AI system may determine that an action is useful, efficient,
necessary, or the best available way to accomplish an objective.

That determination does not establish permission to perform the action.

Authority must be determined by the applicable control architecture.

This separation remains applicable before execution, during execution,
and when an autonomous system encounters an unexpected condition.

## The Deterministic Sentinel

The Deterministic Sentinel is the current architectural concept for
enforcing deterministic authority boundaries.

Its purpose is not to perform the intelligent work of the requesting
agent. Its purpose is to determine whether an action is permitted
according to established control conditions and authority.

The Sentinel should remain functionally separate from the intelligence
seeking permission so that the requesting intelligence cannot redefine
the conditions under which its own actions are authorized.

The Sentinel is intended to become a reusable control responsibility for
future eco619 systems rather than a control mechanism designed only for
one CIP workflow.

Its detailed implementation, interfaces, enforcement mechanisms, and
internal control logic are outside the scope of this public
architectural document.

## The Deterministic Sentinel Is Intentionally Semantically Deaf

The proposed Deterministic Sentinel is intentionally semantically deaf
to the reasoning used by an intelligent agent to justify an action.

Semantic deafness does not mean that the Sentinel lacks the information
required to evaluate a control condition.

It means that persuasive language, argument, reinterpretation, urgency,
confidence, repetition, or an increasingly compelling explanation from
an intelligent system does not itself alter the deterministic authority
boundary.

An intelligent agent may explain why it believes an action is necessary.
It may explain why another path failed. It may identify consequences of
not proceeding. It may propose a different approach or repeatedly
reformulate the request.

Those arguments may be useful information to the intelligent system or
to an authorized human decision-maker.

They do not themselves establish authority.

The Sentinel evaluates the applicable control conditions rather than the
persuasiveness of the requesting intelligence.

The requesting agent should therefore be unable to negotiate, reason, or
linguistically persuade the deterministic authority mechanism into
changing an established permission boundary.

If authority changes, that change must originate from an applicable
authorized source rather than from the persistence or reasoning ability
of the requesting intelligence.

## Independent Authorization Confirmation

The control architecture should not rely upon a single intelligent
determination where an autonomous action crosses a protected authority
boundary.

For those conditions, the architecture is intended to support
**Independent Authorization Confirmation**.

Independent Authorization Confirmation is distinct from CIP's
information-verification processes. Its purpose is not to verify whether
extracted or interpreted information is correct. Its purpose is to
independently confirm that the control conditions required to permit an
action have been satisfied.

The requesting intelligence may provide the context necessary to
identify what action it is attempting to perform, but its conclusion
that the action should be permitted does not constitute authorization.

The confirming responsibility should independently establish the
applicable authorization condition rather than merely repeat or accept
the requesting agent's conclusion.

Where the required authorization cannot be independently established,
the architecture should not infer permission simply to allow autonomous
execution to continue.

The exact mechanism, independence requirements, and control logic used
for confirmation are implementation responsibilities and are
intentionally not defined here.

## Authorization Does Not Become Blanket Authority

Permission to begin an activity does not provide unrestricted authority
over every condition that may arise during that activity.

An autonomous system may enter a process legitimately and subsequently
encounter a new condition, unexpected information, unavailable
destination, failed dependency, changed external state, or other
circumstance requiring an action outside the authority originally
granted.

The original authorization should not automatically extend to that new
action.

The applicable control boundary remains in force throughout execution.

Where the new action requires additional authority, that authority must
be established independently of the requesting agent's desire to
complete its objective.

## Continuous Boundary Enforcement

Deterministic control is not solely an entry gate.

Applicable authority boundaries should remain effective while autonomous
work is underway.

An action authorized at one point in a process does not permit the
intelligent system to redefine later actions as implicitly authorized
merely because they contribute to the same objective.

The architecture should therefore preserve the distinction between
authority to begin an activity, authority to perform actions within that
activity, authority to respond to changed conditions, and authority to
recover or exit when the expected path is no longer available.

The specific control points required by an individual system should be
defined by that system's architecture and risk.

## Controlled Containment and Recovery

An autonomous system may reach a condition in which it cannot complete
or exit an activity through its authorized path.

This creates a distinct control problem.

The intelligent system may be capable of reasoning about alternative
paths. It may identify an action that appears capable of resolving the
condition. That does not mean it has authority to execute that action.

Authorization to enter an autonomous activity does not imply
unrestricted authority to recover from every condition encountered
during that activity.

If the authorized path is no longer available, the system should not
independently expand its authority merely to escape the condition.

The deterministic control architecture should support a controlled
condition in which:

-   further unauthorized action is prevented,
-   the current state can be preserved where applicable,
-   the condition can be identified for engineering or authorized
    review,
-   the intelligent system may reason about possible recovery options
    without gaining authority to execute them,
-   an authorized recovery path may be established,
-   and escalation may occur where additional human or system authority
    is required.

Where no authorized recovery path exists, the system should remain
within the applicable protected boundary rather than invent a new
permission boundary.

Containment is therefore not simply stopping an agent. The architecture
must account for the state in which the autonomous activity has been
left and provide a controlled path toward recovery, escalation, or other
authorized resolution.

## Recovery Does Not Override Authority

A recovery action is still an action.

The fact that an autonomous system is blocked, trapped within a process,
unable to reach an expected destination, or unable to complete its
objective does not itself authorize an exception.

A proposed recovery path should remain subject to the applicable
deterministic control conditions and, where required, Independent
Authorization Confirmation.

The intelligent system may propose recovery.

The control architecture determines whether the proposed recovery may be
executed.

Where human authority is required, the system should escalate rather
than simulate or infer that authority.

## Human Authority

Human authority remains an architectural responsibility.

Where a controlled action requires human approval, the system should
identify the required authority and support an explicit decision path
rather than silently expanding its own permissions.

Human approval should not be simulated, inferred, or substituted by an
AI system.

The architecture should preserve the distinction between:

-   an AI recommendation or proposed action,
-   a deterministic control decision,
-   an independently confirmed authorization condition,
-   and an authorized human decision.

An authorized human may change a condition or grant authority where the
applicable architecture permits it. The intelligent system itself should
not impersonate that authority.

## Control Progression

At the architectural level, deterministic control may be understood
through the following progression:

**Action Request → Authority Evaluation → Independent Authorization
Confirmation → Permit / Deny → Controlled Execution → Continued Boundary
Enforcement → Containment if Required → Authorized Recovery or
Escalation**

This progression describes responsibility and control intent.

It does not prescribe the implementation mechanism, number of technical
components, communication method, or internal decision logic used to
achieve those responsibilities.

## Deterministic Behavior

Deterministic control means that established control conditions produce
established control outcomes.

The Sentinel should not become another reasoning participant in a
disagreement with an autonomous agent.

It should evaluate the applicable control conditions and enforce the
resulting decision.

An intelligent agent may continue to reason about its objective. It may
identify another legitimate path, request additional authority, or
escalate the condition where permitted.

It should not be able to reason the deterministic control itself into
changing an established boundary.

## Provider Independence

The deterministic control architecture should remain independent of a
particular AI model or provider.

Models and providers may change. Their reasoning behavior, capabilities,
language behavior, and level of autonomy may also change.

The authority boundary should remain understandable and enforceable
regardless of which intelligent system is operating behind it.

This separation allows intelligent capabilities to evolve without
requiring authority to become dependent upon the behavior of a
particular model.

## Traceability

Control activity should support sufficient traceability to establish,
where applicable:

-   what action was requested,
-   which system or responsibility requested it,
-   what authority boundary applied,
-   whether authorization was established,
-   whether Independent Authorization Confirmation was required and
    obtained,
-   whether the action was permitted, denied, contained, blocked, or
    escalated,
-   whether execution later encountered a condition outside the original
    authority,
-   whether a recovery action was proposed,
-   and what authorized source changed the outcome if authority was
    subsequently modified.

Traceability should support engineering understanding, accountability,
and later review without exposing protected control implementation
details.

## Relationship to Platform Observability

Deterministic control and platform observability are separate but
related architectural responsibilities.

The control architecture determines whether an action may occur.

Observability provides sufficient execution-state information to
understand what the platform is doing, whether responsibilities have
completed, and whether processing has become waiting, blocked,
contained, or failed.

Where deterministic control prevents continued execution or places an
activity into a controlled condition, sufficient execution-state
information should exist for the condition to be understood and
appropriately addressed.

Observability does not grant authority, and authority does not eliminate
the need for observability.

## Security of the Architecture

Public engineering documentation should explain the existence, purpose,
responsibility, and architectural significance of deterministic control.

It should demonstrate that the Deterministic Sentinel represents a
substantive engineering architecture rather than a conceptual label.

At the same time, public documentation should not disclose
implementation details that would materially assist circumvention,
bypass, reproduction, or reverse engineering of the control mechanism.

Detailed implementation information, enforcement logic, interfaces,
decision structures, and other security-sensitive engineering
information should remain within appropriately controlled engineering
records.

## Relationship to Continuous Intelligence Platform

CIP provides the immediate engineering environment from which portions
of this architectural direction have developed.

The Deterministic Control Architecture is intentionally broader than
CIP.

CIP's autonomous responsibilities, verification architecture, processing
boundaries, and engineering experience may inform development of the
control architecture, but the resulting control principles are intended
to support future eco619 systems as well.

The architecture should therefore avoid unnecessary dependence upon
CIP-specific file processing, information structures, or workflows.

## Future-System Responsibility

Future eco619 systems may interact with external systems, modify
information, initiate processes, communicate with other agents, perform
long-running autonomous activity, or encounter circumstances that cannot
be completely anticipated when execution begins.

Those systems may require different control rules.

The underlying architectural separation should remain consistent where
deterministic authority is required:

**intelligence may reason; authority determines whether action is
permitted.**

Future systems should be able to inherit this control principle without
reproducing the control architecture independently for every new build.

## Current Architectural Status

The Deterministic Sentinel remains an architectural direction under
development.

The foundational concepts are sufficiently established to document:

-   separation of intelligence and authority,
-   deterministic authority boundaries,
-   intentional semantic deafness,
-   Independent Authorization Confirmation,
-   continued boundary enforcement,
-   controlled containment and recovery,
-   authorized escalation,
-   provider independence,
-   and human authority.

Detailed engineering responsibilities will continue to develop as the
architecture is evaluated against future autonomous-system requirements.

Documentation should evolve with that engineering work without
presenting theoretical or unimplemented mechanisms as completed
capability.

## Future Evolution

Future engineering may further define responsibilities for authority
evaluation, action classification, Independent Authorization
Confirmation, execution-time control boundaries, containment state,
recovery authorization, escalation, control-state preservation,
interaction with external systems, agent-to-agent activity, inherited
controls across future platforms, and response to attempts to cross or
circumvent established boundaries.

These responsibilities should be introduced deliberately and documented
when their architecture is sufficiently established.

## Engineering Philosophy

Intelligence and authority are different engineering responsibilities.

The ability to reason about why an action should occur is not the
authority to perform it.

A deterministic control boundary should not become persuadable simply
because the intelligence requesting an action becomes more capable or
more convincing.

Authorization to enter an autonomous process does not grant unlimited
authority to complete or escape it.

When the permitted path no longer exists, intelligence may help
determine what could happen next. Authority must still determine what
may happen next.

Autonomy should expand capability without silently expanding authority.

Technology should support human judgment and established authority. It
should never replace them.

---

**Developed by eco619**  
**Principal Architect:** Joseph Contreras
