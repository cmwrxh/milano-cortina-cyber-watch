# DDoS Detection Signals Playbook

This playbook helps identify Distributed Denial of Service (DDoS) activity affecting public-facing services.

---

## 1) Early Warning Indicators

### Traffic anomalies
- Sudden spike in requests per second
- Traffic from unexpected geographic regions
- Large volume of identical requests

### Application behavior
- Increased latency
- Elevated error rates (HTTP 5xx)
- Database connection exhaustion

### Infrastructure signals
- CPU or memory saturation
- Network bandwidth saturation
- Reverse proxy queue growth

---

## 2) Monitoring Metrics Checklist

Track these metrics continuously:

### Network Layer
- Incoming bandwidth utilization
- Packets per second
- SYN request spikes

### Application Layer
- Requests per second
- Error rate percentage
- Response time percentile (P95/P99)

### Security Layer
- WAF alert frequency
- Blocked request count
- Rate-limited request count

---

## 3) Detection Threshold Examples

| Metric | Warning Threshold | Critical Threshold |
|---------|-----------------|-------------------|
| Requests/sec | 2x baseline | 5x baseline |
| Error rate | >3% | >10% |
| Latency P99 | 2x baseline | 4x baseline |

---

## 4) Verification Steps

Before declaring an incident:

- Confirm legitimate marketing/event traffic spikes
- Check upstream provider status
- Review WAF and firewall logs
- Validate origin server health

---

## 5) Escalation Criteria

Escalate when:

- Service availability degrades
- Threshold breaches persist for 5+ minutes
- Security alerts confirm malicious traffic patterns

---

## 6) Evidence Collection

Capture:

- Traffic graphs
- WAF logs
- Reverse proxy logs
- Server performance metrics
- Timeline of detection events

Store evidence in `/evidence/`
