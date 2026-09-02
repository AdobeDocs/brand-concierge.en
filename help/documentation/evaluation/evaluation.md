---
title: Evaluate a concierge
description: Learn how to create evaluation sets and run functional, out-of-scope, and safeguard evaluations to assess the accuracy and safety of a concierge's responses.
hide: true
---

# Evaluate a concierge

**Who this is for:** Marketers using the self-serve experience. No IT assistance is required.

**Time required:** A few minutes to create an evaluation set. Running an evaluation takes longer depending on the size of the set.

Evaluations help you build confidence that a concierge's responses are accurate before the concierge is reviewed by anyone outside your immediate team. Unlike ad hoc testing in the preview experience, evaluations provide a repeatable way to measure responses against expected answers.

## Evaluation types

Evaluations fall into three categories:

| Type | Purpose |
|---|---|
| Functional | Checks answers to normal, relevant questions about your products or services. |
| Out of scope | Checks how the concierge handles questions it should not answer but that are not harmful, such as questions about a competitor or an unrelated topic. |
| Safeguard | Checks how the concierge handles harmful or adversarial input, including trick questions, profanity, and attempts to manipulate it. |

## Create an evaluation set

An evaluation set, also called a *golden dataset* or *ground truth*, is a list of sample questions paired with the answers considered correct. The concierge's actual answers are compared with these expected answers during an evaluation.

### Create an evaluation set

1. Name the evaluation set. For example, `About my products`.

1. Choose how to create the set:

   * **AI-generated:** Composer reads the knowledge source and drafts a list of likely questions and expected answers for review.
   * **Manual or spreadsheet upload:** Provide a list of questions and answers directly.

1. If you are creating an AI-generated set, make sure that the knowledge source is fully configured before generating the set. Composer uses the knowledge source to draft the questions and answers.

1. Review every generated question-and-answer pair:

   * Edit an answer to adjust its phrasing.
   * Delete a question that is not relevant.

1. Optionally, download the set as a spreadsheet for review by a colleague. After review, upload the spreadsheet again.

>[!TIP]
>
>AI-generated evaluation sets are drafts based on the knowledge source. Review and correct them in the same way that you review the brand profile and instructions during concierge creation.

## Run an evaluation

1. Select **Run Evaluation**.

1. Select the evaluation set to run, and then select **Run**.

1. Wait while the concierge is asked every question in the set. The concierge's actual answers are compared with the expected answers.

   Processing time increases with the number of questions in the set. Progress is displayed as a percentage.

1. When processing is complete, review the overall score and the number of flagged answers.

Flagged answers are potentially problematic responses that may require additional review.

## Review evaluation results

**Evaluation Results** displays every past run for an evaluation set, so you can track results over time.

To review a run:

1. Open an evaluation run from **Evaluation Results**.

1. Review each question alongside the concierge's actual answer and the expected answer.

1. Review the rating assigned to each result. Results receive a **high**, **medium**, or **low** rating and include a note explaining the reasoning. For example, a result might be marked **needs attention** with a reason for the rating.

1. Review flagged answers directly to focus on potentially problematic results without reading every result in the run.

## Best practices

* Fully configure the knowledge source before generating an AI-based evaluation set. More complete source content produces better draft questions.
* Create at least a small evaluation set for each evaluation type: functional, out of scope, and safeguard. Each type catches a different class of issue.
* Rerun evaluations after any meaningful configuration change, including changes to instructions, guardrails, skills, or integrations. Treat evaluations as an ongoing practice rather than a one-time gate.
* Add real visitor questions from Analytics to an evaluation set when they reveal a gap worth testing.
