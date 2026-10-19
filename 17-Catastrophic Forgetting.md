# Catastrophic Forgetting in Neural Networks and LLMs

## 1. What Is Catastrophic Forgetting?

**Catastrophic forgetting** is a problem in which a neural network loses some previously learned capabilities while learning a new task or adapting to new data.

It can occur when training updates that improve performance on a new task interfere with parameters that were useful for earlier tasks.

For example, a model may perform well on general translation tasks before fine-tuning but perform worse on those tasks after being trained heavily on a narrow medical dataset.

This outcome is possible, but it is not guaranteed.

## 2. Example

Imagine a model has these capabilities before additional training:

| Task | Before training |
|---|---|
| General translation | Good |
| General question answering | Good |
| Medical terminology | Basic |

Now suppose the model is fine-tuned extensively on medical text.

After training, it might show:

| Task | Possible result |
|---|---|
| General translation | Performance decreases |
| General question answering | Performance decreases |
| Medical terminology | Performance improves |

This is an illustrative example. Actual results depend on the dataset, training procedure, model, and evaluation method.

## 3. Why Can It Happen?

Neural networks use learned numerical parameters to represent patterns and perform computations.

Fine-tuning updates some or all of these parameters. The changes that help a new task can sometimes interfere with parameters or representations that supported older capabilities.

The risk can increase in some settings when:

- The new training dataset is narrow.
- Training focuses heavily on a new task.
- The learning rate or number of training steps is unsuitable.
- The training process does not preserve performance on earlier tasks.

## 4. How Can Catastrophic Forgetting Be Reduced?

### A. Mix old and new data

Include examples from earlier tasks alongside new task examples.

### B. Replay previous examples

Reintroduce selected examples from earlier training tasks during subsequent training.

### C. Use regularization

Regularization methods can discourage harmful changes to parameters that are important for previous capabilities.

### D. Use parameter-efficient fine-tuning

Methods such as LoRA train additional low-rank parameters rather than updating all original model weights.

This can reduce interference in some settings, but it does not guarantee that earlier capabilities will be preserved.

### E. Evaluate old and new tasks

Test the model on both new tasks and previous tasks before and after fine-tuning. This helps identify performance regressions.

## 5. Is Catastrophic Forgetting Inevitable?

No. Fine-tuning does not always cause catastrophic forgetting.

Its likelihood and severity depend on the model, training data, optimization method, and how old and new tasks relate to one another.

## Key Takeaway

Catastrophic forgetting occurs when learning new information harms previously learned capabilities.

The goal is to improve performance on new tasks while preserving as much useful existing capability as possible.
