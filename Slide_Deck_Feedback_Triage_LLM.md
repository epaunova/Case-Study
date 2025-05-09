# 📊 Slide Deck: Improving User Feedback Triage with LLMs

## Slide 1: Title
- Improving User Feedback Triage with LLMs
- Eva Paunova – AI Product Manager Case Study

---

## Slide 2: Problem
- High volume of unstructured user feedback
- Manual triage is slow, inconsistent
- Valuable insights often missed

---

## Slide 3: Goal
- Categorize feedback automatically
- Identify urgency (Low, Medium, High)
- Improve response time and roadmap insights

---

## Slide 4: Dataset
- 1,000 synthetic feedback entries
- Labeled: Category + Urgency
- Format: JSONL (prompt-completion)

---

## Slide 5: Model + Fine-Tuning
- Base: Mistral-7B-Instruct (HF)
- Approach: LoRA + PEFT
- Prompt structure: Few-shot + instruction style

---

## Slide 6: Evaluation
- Accuracy: 87%
- GPT-4 spot grading
- Human-labeled validation: 80% agreement
- Confusion UX vs Feature Requests

---

## Slide 7: Key Learnings
- Few-shot was strong baseline
- Fine-tuning improved consistency
- LoRA sufficient (efficient training)

---

## Slide 8: Next Steps
- Deploy API for real-time triage
- Slack/Notion integration
- Add real user data w/ privacy handling

---

## Slide 9: Thank You
- Contact info / GitHub / Loom link
