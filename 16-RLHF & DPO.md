# RLHF and DPO: Alignment in LLMs

## 1. What Is Alignment?

Alignment in language models refers to training and evaluation methods intended to make model behavior better match desired goals and preferences, such as helpfulness, clarity, instruction following, and safety.

A model may produce grammatically correct text but still give an unhelpful answer. Alignment techniques can help improve its behavior.

## 2. Human Preferences

Consider the prompt:

**Prompt:** Explain photosynthesis to a 10-year-old.

**Response A:**

Plants use sunlight to make their own food. Sunlight provides the energy they need for this process.

**Response B:**

Photosynthesis is a biochemical process involving photochemical reactions and carbon fixation.

Both responses may contain valid information, but Response A may be preferred because it better matches the requested audience.

Preference data can help train models to produce responses that better fit such requirements.

## 3. RLHF

**RLHF** stands for **Reinforcement Learning from Human Feedback**.

A common RLHF pipeline uses human preference data to train a reward model, then uses reinforcement learning to optimize a language model against that reward signal.

### A simplified RLHF pipeline

1. **Collect preference data:** Reviewers compare or rate model responses.
2. **Train a reward model:** The reward model learns to estimate which responses are preferred.
3. **Optimize the language model:** Reinforcement learning adjusts the model to improve its reward.
4. **Evaluate the result:** Check response quality, safety, and other target behaviors.

Some RLHF implementations also use constraints or penalties to limit undesirable changes from an earlier model.

RLHF is a family of approaches, and not every implementation uses exactly the same pipeline.

## 4. DPO

**DPO** stands for **Direct Preference Optimization**.

DPO trains a model using preference pairs, typically consisting of:

- A prompt.
- A preferred response, often called `chosen`.
- A less-preferred response, often called `rejected`.

Standard DPO directly optimizes the model using these preferences relative to a reference model. It does not require training a separate reward model and running the same reinforcement-learning loop used in common PPO-based RLHF pipelines.

### Example

**Prompt:** Explain AI in simple language.

**Chosen response:** AI is technology that allows computers to perform tasks that normally require human-like intelligence.

**Rejected response:** An unnecessarily confusing response that does not fit the user's request.

The training objective encourages the model to prefer the chosen response over the rejected response.

## 5. RLHF vs. DPO

| RLHF (common PPO-based approach) | DPO |
|---|---|
| Uses human preference data or feedback. | Uses preference pairs. |
| Commonly trains a separate reward model. | Standard DPO does not require a separate reward model. |
| Uses a reinforcement-learning optimization loop. | Directly optimizes a preference-based objective. |
| Can involve a more complex training pipeline. | Often has a simpler training pipeline. |

Both methods depend on the quality of their preference data and training setup. Neither guarantees perfect alignment.

## 6. Why Is Alignment Useful?

Alignment methods can help models:

- Follow instructions more consistently.
- Produce clearer and more relevant responses.
- Better match desired tone and format.
- Reduce some undesirable behaviors.
- Respond in ways preferred by human reviewers.

However, preferences can be subjective, and optimizing for preferences does not automatically guarantee factual accuracy.

## Key Takeaway

RLHF and DPO are alignment techniques that use preferences to shape a model's behavior.

**Simple distinction:** Common RLHF pipelines use a reward model and reinforcement learning. Standard DPO directly learns from preferred and less-preferred response pairs.
