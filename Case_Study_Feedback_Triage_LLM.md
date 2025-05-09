# 📝 Case Study: Improving User Feedback Triage with LLMs

## 🔍 Problem

Manual user feedback triage is time-consuming, inconsistent, and hard to scale. Product teams often miss valuable insights due to volume, lack of tagging, or vague descriptions.

## 🎯 Goal

Use an LLM to automate the categorization and prioritization of user feedback based on:
- Feature requests
- Bugs
- UX issues
- Praise
- Urgency

---

## 🛠 Dataset Creation

I curated a dataset of 1,000 synthetic user feedback entries modeled on real-world sources (e.g., support tickets, in-app reviews). Each entry was labeled with:
- Category (Feature Request, Bug, etc.)
- Urgency (Low, Medium, High)
- Example labels:

```json
{
  "text": "It crashes when I click 'Upload'. Please fix ASAP!",
  "category": "Bug",
  "urgency": "High"
}
```

Data format: JSONL, used for instruction tuning.

---

## 🧠 Model + Fine-tuning

**Base model:** `mistralai/Mistral-7B-Instruct` (HF Transformers)

**Training approach:** LoRA + PEFT  
- Epochs: 3  
- Learning rate: 2e-5  
- Training tokens: ~40K

Prompt template:

```
System: You are a support assistant helping categorize user feedback.
User: "The settings menu is confusing. I expected to find notifications there."
Assistant: Category: UX issue; Urgency: Medium
```

---

## 📊 Evaluation

- **Accuracy**: 87% on validation set (200 entries)
- **Manual review**: 80% match with human-labeled examples
- **Confusion matrix**: Some confusion between UX issues and Feature Requests

Evaluation was done with:
- GPT-4 grader (for edge cases)
- Manual spot checks
- Scoring metrics in notebook (`evaluate_outputs.ipynb`)

---

## 💡 Key Learnings

- Few-shot prompting was surprisingly strong, but fine-tuning helped with consistency.
- Most mislabeled items lacked clear urgency cues — future work could incorporate heuristics.
- LoRA was sufficient; full fine-tuning wasn't needed.

---

## 🔗 Next Steps

- Deploy as API to auto-label feedback in real-time
- Integrate into internal tools (e.g., Notion, Slack bot)
- Expand dataset with real user data (with privacy guardrails)

---

## 📎 Resources
- [Dataset example](../datasets/classification_tasks.jsonl)
- [Training config](../configs/finetune_config.json)
- [Notebook for evaluation](../notebooks/evaluate_outputs.ipynb)

(Optional: [Watch Loom walkthrough](https://loom.com/your-demo-link))
