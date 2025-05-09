# 📄 Product Requirements Document (PRD)

## Feature: AI Onboarding Assistant

### Problem Statement
Users often abandon onboarding flows because they feel generic, slow, or hard to navigate. Manual support is costly and doesn’t scale.

### Solution
An LLM-powered onboarding assistant that guides new users based on their goals, product type, and real-time questions. The assistant will operate as a chat interface embedded in the onboarding screen.

---

## User Stories

- As a new user, I want to describe my goal in natural language and receive step-by-step setup guidance.
- As a PM, I want analytics on where users drop off during onboarding so we can improve funnel conversion.

---

## LLM Capabilities Required

- Intent recognition from open-ended input
- Step-by-step guidance generation
- Retrieval from onboarding docs or API docs (optional RAG)
- Tone control (friendly, concise)

---

## Prompts Examples

**System prompt**:  
“You are a product onboarding expert helping users complete setup quickly and successfully.”

**User prompt**:  
“I want to set up Stripe payments and get notified when someone subscribes.”

**LLM response**:  
“Great! To set up Stripe:  
1. Go to Billing Settings → Connect Stripe.  
2. Set up a webhook to receive payment notifications.”

---

## Evaluation Metrics

- 🎯 Task completion rate
- ⏱ Time-to-setup
- 📉 Drop-off rate during onboarding
- 📊 User satisfaction (feedback rating)

---

## Launch Plan

- Phase 1: Integrate chat interface + scripted LLM responses
- Phase 2: Add dynamic response generation + intent handling
- Phase 3: Evaluate and improve with human-in-the-loop review
