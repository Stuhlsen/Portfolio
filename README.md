# QA Portfolio: GroceryMate Web Shop

A full manual testing cycle for three new features of a web shop, from unclear requirements to bug reports. Done during my QA bootcamp at Masterschool (April–May 2026) against the public training shop [GroceryMate](https://grocerymate.masterschool.com/).

> 📝 The documents are written in **German**.

## At a glance

| | |
|---|---|
| Features under test | Product ratings · age verification for alcohol · free-shipping threshold |
| Test cases designed | 18 |
| Scenarios executed | 19 |
| Bugs found and reported | **5** → [Issues](https://github.com/Stuhlsen/Portfolio/issues) |
| Test design techniques | Boundary value analysis · equivalence partitioning · use case testing · error guessing |

## The testing cycle

| Step | Document | What's inside |
|---|---|---|
| 1. Requirements analysis | [requirements.md](STLC/requirements.md) | Unclear requirements → clarifying questions → precise, testable requirements |
| 2. Test plan | [test plan.md](STLC/test%20plan.md) | Scope, test types, risks, entry/exit criteria, schedule |
| 3. Test case design | [test case design.md](STLC/test%20case%20design.md) | 18 test cases plus an automation-potential assessment |
| 4. Test execution | [functional test execution.md](STLC/functional%20test%20execution.md) | Step-by-step results (OK/NOK) with screenshots and links to the bug reports |

## Bugs found

| # | Feature | Finding |
|---|---|---|
| [#3](https://github.com/Stuhlsen/Portfolio/issues/3) | Age verification | Alcohol products can be opened directly by URL, without age verification |
| [#2](https://github.com/Stuhlsen/Portfolio/issues/2) | Age verification | The modal appears when opening the shop instead of the alcohol category |
| [#1](https://github.com/Stuhlsen/Portfolio/issues/1) | Shipping costs | Shipping costs do not update after removing a product from the cart |
| [#4](https://github.com/Stuhlsen/Portfolio/issues/4) | Ratings | Average rating does not update after editing an existing rating |
| [#5](https://github.com/Stuhlsen/Portfolio/issues/5) | Ratings | Character counter shows 500/500 in red although saving is allowed |

## Highlights

- **Boundary values tested to the cent and to the day:** subtotals of €19.99 / €20.00 / €20.01, and birth dates one day under, exactly at and one day over 18.
- **Negative testing found the most serious bug:** after being refused as underage, alcohol products were still reachable by direct URL (#3).
- **Requirements first:** every feature started with open questions that were turned into a precise, testable requirement before any test case was written.

## More from me

🚴 [Training Dashboard](https://github.com/Stuhlsen/training-dashboard): a live platform I build and test myself, with 3,700+ automated tests.
💼 [LinkedIn](https://www.linkedin.com/in/alexander-mueller89)
