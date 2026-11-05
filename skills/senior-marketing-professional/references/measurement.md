# Marketing Measurement and Experiments

Read this reference only for performance analysis, forecasting, budget allocation, attribution, dashboards, or experiment design.

## Select a useful metric system

Start from the business outcome and work backward. Use a compact chain:

1. Business outcome: incremental revenue, contribution margin, qualified pipeline, retention, or another economically relevant result.
2. Customer behavior: purchase, activation, repeat use, referral, or another observable action.
3. Leading indicator: qualified visits, engaged accounts, trial starts, product-qualified leads, or another signal with a plausible link to the behavior.
4. Delivery and quality guardrails: reach, frequency, deliverability, complaints, cancellations, lead quality, sales capacity, or brand risk.

Avoid treating impressions, clicks, followers, raw leads, or content volume as success unless the task is explicitly about delivery and the relationship to the outcome is stated.

## Define metrics precisely

For each decision metric, record:

- name and business question;
- numerator and denominator;
- cohort or eligible population;
- time window and comparison period;
- source of truth and owner;
- known exclusions, latency, and data-quality limitations.

Common formulas:

- Conversion rate = conversions / eligible opportunities.
- Customer acquisition cost = acquisition spend / new customers attributed under the stated method.
- Return on ad spend = attributed revenue / ad spend.
- Marketing efficiency ratio = total or incremental revenue / marketing spend; state which revenue definition is used.
- Lifetime value = expected contribution margin over the defined customer lifetime; do not equate revenue with value.
- Pipeline velocity = qualified opportunities x win rate x average deal value / average sales-cycle length.

Never compare metrics with different attribution models, windows, currencies, tax treatment, or cohort definitions without normalization and disclosure.

## Handle attribution honestly

Platform attribution, analytics attribution, CRM attribution, and finance reporting answer different questions. Label the source and method. Do not add attributed revenue across platforms because the same conversion may be counted more than once.

Use causal language only when supported by a credible experiment or design. Otherwise use language such as "associated with," "reported by the platform," or "consistent with."

When the decision is material, prefer incrementality tests, geo or audience holdouts, randomized experiments, matched markets, or a documented quasi-experimental design. Use marketing-mix modeling for aggregate allocation only when data volume, variation, and methodology justify it.

## Design a useful experiment

Specify:

- decision the test will inform;
- hypothesis and expected mechanism;
- primary metric and guardrails;
- eligible population and assignment unit;
- control or comparison condition;
- minimum detectable effect or practical success threshold;
- planned duration and major seasonality risks;
- stopping rule and follow-up action for win, loss, or inconclusive result.

Change one strategic variable at a time when causal interpretation matters. Multiple creative variants are acceptable when the test is explicitly designed to select a winner rather than estimate the isolated effect of every element.

Do not stop a test solely because an early result looks favorable. Note small samples, repeated peeking, novelty effects, selection bias, survivorship bias, and instrumentation changes.

## Forecast without false precision

Expose the model:

`Outcome = eligible volume x response rate x qualification rate x conversion rate x value per conversion`

Use ranges or scenarios when inputs are uncertain. Identify the assumptions that dominate the result and show the break-even threshold. Reconcile totals across funnel stages, budgets, currencies, and time periods before presenting the forecast.
