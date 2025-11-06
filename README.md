# A Calculus for Redundant System Design

* Possible Titles:
    - A Redundancy Aware Calculus for System Design Analysis
    - A Calculus for Redundant System Design

* Venue: DSN? NFM? FM?

## File descriptions
- valve_model: A basic dGL program showing what is physically possible in the system.
- valve_model_basic: The valve_model dGL program instrumented to also have metrics to measure the operational and redundancy costs.
- attack: A overflow attack specification, written as a mapping from dGL subgames representing PLC control to the way the attacker overrides the control decisions, plus how long the attack runs.
- attack_analysis: A dGL program that composes the valve_model_basic with the attack specification. Its control envelope (preconditions annotations of every subgame saying when they can safely be played) analyzes the system behavior under attack. If state \sigma is in the envelope at program point p, that means starting at program point p there is a way to mitigate the attack with cost \sigma(cost_metric) where cost_metric measures the operational/redundancy costs incurred.
- reasoning_description.txt: Describes an example if how the game in attack_analysis gives us a way to verify if our analysis of system behavior is correct.

## Notes/Open questions:
- Is the attack syntax of replacing subgames a good abstraction to represent real attacks? Is it general enough to represent some well-known class of attacks?
- Is the metric instrumentation general enough to represent metrics of practical interest?
    * If we can arbitrarily add new variables, are there even any theoretical limitations to what we can express?
    * On the other hand, is there a systematic way to do instrumentation so that adding typical metrics is easy for practitioners?
- Do we really want control envelopes, or is dGL enough? I think envelopes make more sense if we want to somehow extract mitigation as a part of our story, otherwise dGL could be enough.

## Paper

Overleaf (currently very little, tentative text): https://www.overleaf.com/1633871886gmcpnjrykzsg#fe8c83