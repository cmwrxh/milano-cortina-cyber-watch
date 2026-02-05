# WAF / Edge Protection Rules Checklist (Vendor-Neutral)

Use this checklist for Cloudflare, Fastly, Akamai, AWS WAF, or any edge/WAF provider.

---

## 1) Baseline protections
- [ ] Enable WAF managed rules (OWASP baseline)
- [ ] Block obvious bad bots / known malicious user agents
- [ ] Enable geo controls if your service is regional
- [ ] Enforce HTTPS, redirect HTTP → HTTPS

---

## 2) Rate limiting
- [ ] Rate limit per-IP on `/login`, `/signup`, `/search`, `/api/*`
- [ ] Add stricter rate limits for expensive endpoints
- [ ] Add burst capacity (short spikes) but cap sustained abuse
- [ ] Set meaningful block duration for repeat offenders

---

## 3) Bot management
- [ ] Challenge suspicious traffic (JS challenge / CAPTCHA)
- [ ] Allow verified bots (search engines) via allowlist
- [ ] Detect headless browsers and automation patterns
- [ ] Block requests missing typical browser headers (where appropriate)

---

## 4) Origin protection
- [ ] Lock origin to only accept traffic from the WAF/edge IPs
- [ ] Hide origin IP (no direct DNS leaks)
- [ ] Ensure internal admin endpoints are not public

---

## 5) Abuse detection rules
- [ ] Block repeated 401/403 spikes (credential stuffing)
- [ ] Block repeated 404 spikes (scanning)
- [ ] Flag unusual query payload sizes
- [ ] Flag repeated POST requests with identical payload patterns

---

## 6) Logging & monitoring
- [ ] Enable request logs (sampled if needed)
- [ ] Track WAF blocks over time
- [ ] Create alerts for sudden block spikes + error spikes
- [ ] Keep incident evidence snapshots

---

## 7) Emergency switches (during incident)
- [ ] “Under Attack Mode” profile ready
- [ ] Temporary stricter rate limits preset
- [ ] Ability to block ASNs/regions quickly
- [ ] Static cache mode / read-only mode documented
