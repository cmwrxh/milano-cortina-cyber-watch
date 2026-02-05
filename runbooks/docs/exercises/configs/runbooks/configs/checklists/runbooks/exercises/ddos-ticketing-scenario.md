# Tabletop Exercise: Ticketing Portal Under DDoS Attack

## Scenario Overview
A high-profile global event ticketing portal begins experiencing heavy traffic spikes shortly after ticket sales open. Customers report slow loading times and failed transactions.

---

## Objectives
- Test incident detection speed
- Test communication coordination
- Test technical mitigation readiness
- Test decision escalation process

---

## Participants
- Infrastructure / DevOps team
- Security / SOC team
- Customer Support team
- Communications / PR team
- Product owner

---

## Timeline Simulation

### T+0 Minutes
Ticket sales open. Traffic increases to 3x normal baseline.

### T+5 Minutes
Monitoring alerts show:
- Increased request volume
- Latency rising
- Error rate increasing

Decision prompts:
- Is this legitimate traffic?
- What verification steps are taken?

---

### T+15 Minutes
Indicators suggest automated traffic flood:
- Large number of repeated requests
- High login failure attempts
- WAF alerts increasing

Decision prompts:
- When do you declare an incident?
- Who gets notified?

---

### T+30 Minutes
System performance degrades:
- Checkout failures rising
- Customer complaints increasing
- Social media complaints begin

Decision prompts:
- Do you enable emergency WAF protections?
- Do you temporarily disable non-critical services?

---

### T+60 Minutes
Attack intensifies:
- Database under stress
- Infrastructure scaling attempts failing

Decision prompts:
- Do you activate read-only mode?
- Do you restrict traffic geographically?
- Do you publish public incident notice?

---

## Exercise Evaluation Criteria

### Detection
- Time to alert acknowledgement
- Accuracy of root cause identification

### Response
- Speed of mitigation deployment
- Effectiveness of traffic controls

### Communication
- Clarity of internal updates
- Clarity of public messaging

### Coordination
- Role clarity
- Escalation efficiency

---

## After Action Review Questions
- What detection signals were missed?
- What mitigation controls were ineffective?
- What communication delays occurred?
- What infrastructure improvements are needed?

---

## Success Metrics
- Service restored within defined SLA
- Clear communication maintained
- Evidence captured for postmortem
