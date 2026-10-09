# Home Credit - Loan Against Property (LAP) AI Voice Agent

An autonomous voice qualification agent built for Home Credit to screen existing customers for pre-approved Loan Against Property (LAP) offers up to ₹75 Lakhs.

## Platform & Tech Stack
- Engine: Retell AI
- LLM: GPT-4.1 / GPT-4o
- Acoustic Profile: English Voice, latency-optimized (<25 words per turn)
- Tool Integration: Autonomous end_call trigger for qualification and policy exits

## Key Business Logic & State Architecture
1. Dynamic State Tracking: Extracts multi-variable inputs out-of-order without re-asking answered fields.
2. Compound Qualification: Strictly verifies bank disbursement mode alongside occupation before moving forward.
3. Deterministic Branching:
   - Happy Path: 7-point verification passed -> Handoff to Senior Loan Advisor.
   - Immediate Disqualification: Agricultural property, Cash income, missing original documents, or tenure outside 3–15 years -> Instant exit.
   - Loan Transfer Pivot: Existing mortgage / EMI reduction requests routed to Transfer Specialist.
   - Over-Limit Protocol: Caps amounts >₹75 Lakhs with customer consent gate.
