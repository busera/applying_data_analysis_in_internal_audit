# Introduction and Purpose

Internal audit data analysis often fails before the first script is written. The usual problem is not the tool; it is an unclear audit question.

A weak question sounds like:

> Can we analyze purchase orders?

A stronger question sounds like:

> For purchase orders above CHF 50,000 created during the audit period, identify cases where approval occurred after release, the approver was not authorized for the amount, or the requester and approver were the same person.

The second version is usable because it defines the population, expected behavior, exception logic, required fields, and audit purpose.

This section adapts research-methodology distinctions from Card, Min, and Serghiou's *Open, rigorous and reproducible research* to internal audit practice. The goal is not to make every audit analysis academic. The goal is to help auditors label the type of question they are asking, choose a suitable analytical approach, and avoid overstating what the data can prove.

The two core distinctions are:

- **Confirmatory vs. exploratory**: Are we testing a defined expectation, or looking for patterns and leads?
- **Causal vs. non-causal**: Are we trying to assess an intervention's effect, or describe relationships, distributions, and exceptions?

These distinctions matter because they affect data requirements, evidence strength, reporting language, and whether the output can support an audit conclusion or only a planning lead.
