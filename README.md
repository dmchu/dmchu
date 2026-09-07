## Dmitry Chuveev

Platform and reliability engineering for payments infrastructure on AWS.

I look after a five-cluster Kubernetes fleet and the systems around it — infrastructure as code,
the delivery path, observability, and the access model. Roughly seventeen services on a
consolidated Postgres estate, run by a small team, which shapes most of the decisions below.

### What I work on

Boundaries, mostly. The places where two systems that don't speak the same language have to
meet — a managed database and a desktop client, a hosting platform and a log backend, four alert
producers and one person reading a phone at 3am.

What they have in common is that **the default failure at a boundary is silence, not an error**.
A dashboard stays green, a counter stays flat, a query returns success and no rows, a pod stays
`Running`. So the work is usually two mechanisms rather than one: something that does the job,
and something whose only job is to prove the first is still running.

Recent examples:

- Replaced shared database passwords with short-lived per-person IAM tokens. The interesting
  part wasn't the auth — it was an audit showing the secure path already existed and had been
  used zero times, because it was harder than the password sitting next to it.
- Built an observability operating model with a layered signal hierarchy, service objectives and
  three alert tiers, so that pages are business-outcome regressions rather than platform noise.
- Consolidated twelve database clusters into one, database-per-service, without a maintenance
  window.
- Ran a 40-proposal architecture review through adversarial verification. Twenty-two proposals
  were refuted — twelve of which would have caused an incident had they shipped. That refutation
  rate turned out to be the useful output.

### Interests

Verification over confidence: writing down the mechanism, then proving it holds rather than
assuming it does. Most of what I've learned the expensive way is about controls that look applied
and do nothing.

Currently renewing CKS and working through the AWS DevOps Professional material.

### Elsewhere

- [LinkedIn](https://www.linkedin.com/in/dmitry-chuveev/)
- `platform-patterns` — five patterns from the work above, each with the decision record behind
  it, including the option that lost. Publishing shortly.

<sub>The repositories below are from an earlier career in test automation and are kept for
history.</sub>
