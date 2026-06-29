# Rules of Engagement — Phishing Simulation
## Internee.pk | Authorized Internal Security Awareness Program

> **Instructions:** Complete every field below before any campaign asset is touched. All four sign-off authorities must sign. Retain a copy in the security team's records for a minimum of 12 months.

---

## 1. Program Details

| Field | Value |
|---|---|
| **Program name** | _(e.g., "Internee.pk Security Awareness Wave 1")_ |
| **Program owner** | _(Name, Title)_ |
| **Technical lead** | _(Name, Title — person running GoPhish)_ |
| **RoE version** | v1.0 |
| **RoE date** | \_\_\_\_ / \_\_\_\_ / \_\_\_\_ |

---

## 2. Scope

### 2.1 In-Scope
- **Departments / teams:** _(list all departments included)_
- **Approximate headcount:** ___
- **Email domain(s):** _(e.g., @internee.pk)_
- **GoPhish server location:** _(IP / hostname of the test server)_
- **Landing page domain:** _(e.g., phishtest.internee.internal — must NOT be a deceptive look-alike)_

### 2.2 Explicitly Out-of-Scope
- [ ] System/service accounts and shared mailboxes
- [ ] Employees currently on medical leave or compassionate leave
- [ ] _(Any other exclusions — add rows as needed)_
- _______________________________________________

---

## 3. Test Window

| | Date | Time (PKT) |
|---|---|---|
| **Campaign start** | | |
| **Campaign end** | | |
| **Results embargo (before leadership briefing)** | | |
| **Blackout periods (no sending)** | | |

**Reason for chosen window:** _(explain why this period was selected — avoid quarter-end, major launches, high-stress periods)_

---

## 4. Campaign Parameters

| Parameter | Value |
|---|---|
| **GoPhish template(s) used** | _(Template 1 / 2 / 3 or custom — name them)_ |
| **Sending address / display name** | _(test mailbox address)_ |
| **Landing page URL** | _(full URL)_ |
| **Data captured** | Click event, form submission event _(no plaintext passwords)_ |
| **Redirect after click** | Post-click training explainer page |
| **Redirect after submission** | Training explainer page (same) |

---

## 5. Data Handling

- **Who can view individual-level results:** _(e.g., IT Security Lead, HR Lead only)_
- **Organization-wide reporting:** Aggregated by department — no named individuals in all-hands or leadership reports
- **Retention period for raw event logs:** \_\_\_ days, then deleted/anonymized
- **Storage location:** _(secured, access-controlled path)_
- **Password field handling:** Landing page will NOT store any value entered in a password field. The field is masked and discarded server-side.

---

## 6. Emergency Stop Procedure

| Trigger | Action |
|---|---|
| Recipient reports genuine distress | Immediately pause campaign; IT Security Lead to call recipient directly |
| Helpdesk ticket volume spikes > 10 tickets/hr related to the test | Pause campaign; notify emergency contact |
| Any indication of campaign content leaking externally | Pause campaign; notify Legal immediately |

**Emergency contact (during campaign window):**
- Name: _______________________________
- Mobile: _______________________________
- Escalation: _______________________________

---

## 7. No-Harm Commitments

By signing below, all parties confirm:

- [ ] No real malicious code, macros, or destructive payloads will be used at any time.
- [ ] No external look-alike domains will be registered or used.
- [ ] No real credentials will be logged, stored, or transmitted from the landing page.
- [ ] All GoPhish infrastructure will be isolated from production systems.
- [ ] Campaign data will not be shared outside the named stakeholder group.
- [ ] The purpose of this program is employee education and organizational improvement — not discipline.

---

## 8. Legal & Compliance Confirmation

- [ ] Legal / Compliance has reviewed this RoE and confirmed it is consistent with Internee.pk's IT-use policy and employment agreements.
- [ ] Legal / Compliance has confirmed this activity is compliant with Pakistan's Prevention of Electronic Crimes Act (PECA) 2016.
- [ ] HR has confirmed that using the internal employee directory for this program is covered by existing employee policy acknowledgements, or has obtained separate confirmation.

---

## 9. Sign-Off

| Authority | Name | Title | Signature | Date |
|---|---|---|---|---|
| Senior Leadership / Executive Sponsor | | | | |
| IT / Security Lead | | | | |
| HR Lead | | | | |
| Legal / Compliance | | | | |

---

_This document is classified Internal / Confidential. Retain for a minimum of 12 months._
