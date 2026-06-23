# Case Processing Flow

## 1. Case Processing (After Receiving a Case)

```
case → Classify Type:
├── Incident
│   → Request additional information for investigation
│   → Is information sufficient?
│       ├── No → Request more info (Instance name, IP, time, error message)
│       └── Yes → Can we fix it ourselves?
│           ├── Yes → Fix internally → Reply to customer → end
│           └── No → Escalate to infra/dev team → Reply to customer → end
├── Request
│   → Select answer from Q&A knowledge base
│   → Reply to customer → end
├── Abuse Report (external)
│   → Dante ตรวจสอบ IP (รู้เทียบ ip-ranges.yaml)
│   ├── Commercial → Admin forward noc@inet.co.th → end
│   └── Gate/Kory → Dante วิเคราะห์ประเภท + compose reply → Admin ตรวจสอบ → Reply
└── Policy / Compliance
    → Check for T&C violation on Gate platform
    → Reply to customer → end
```

## 2. Channel Routing (How Customers Reach Us)

```
Customer chooses channel:
├── Phone → Call TTM (02-257-7189) → Follow TTM x OLS flow
├── Email → technical support → OP checks email + replies
└── Ticket → Open Ticket directly → OP checks Ticket + replies
```

## 3. Platform Routing (Self Service Call Flow for TTM/NOC)

### Core Rule
- Always ask Portal first. Never decide based on email alone.
- The same email can be registered on both Kory and Gate.
- Use Public IP to cross-verify when the case involves Instance/VM/Network.

### Required Information
1. Portal in use (Kory / Gate / Commercial Cloud)
2. Account Email
3. Public IP (mandatory for Instance, VM, Network, Ping, SSH/RDP, Website, Port, Security Group cases)
4. Symptom details or request description
5. Service-specific info (Instance name, domain, SSL order, Payment slip, etc.)

### Platform Decision Flow

```
Step 1: Customer calls in → TTM answers
Step 2: Ask Portal (Kory / Gate / Commercial)
Step 3: Request Email + Public IP (if Instance/Network)
Step 4: Route based on Portal/IP:
├── Kory (kory.openlandscape.cloud / IP 203.154.16.0/24)
│   → Open case at pro-tracker.openlandscape.cloud
│   → Classify as Request or Incident
│   → Notify OP OLS
├── Gate (gate.openlandscape.cloud / IP in Gate ranges)
│   → Open Ticket at internal.openlandscape.cloud
│   → Classify as Request or Incident
│   → Notify OP OLS
├── Email/Verify (insufficient data)
│   → Request more info (Portal + Public IP)
│   → If only email available → open as Kory case first
└── Commercial Cloud (portal.openlandscape.cloud, alpha.openlandscape.cloud, Commercial IP ranges)
    → Direct customer to noc@inet.co.th
```

### Platform Rules
- A: `kory.openlandscape.cloud` or IP `203.154.16.0/24` → open case at `pro-tracker.openlandscape.cloud`
- B: `gate.openlandscape.cloud` or IP in Gate ranges → open Ticket at `internal.openlandscape.cloud`
- C: Only email available (last resort) → open as Kory case first, let OP OLS verify
- D: Commercial Cloud or Commercial IP → direct customer to `noc@inet.co.th`
- E: Always reply via Ticket/Email system for tracking and documentation

### Domain Check (Gate-specific)
- If customer reports domain issue → ask full domain name → search in `internal.openlandscape.cloud`
- If found → use the linked Account Email to open Ticket
- If not found → send to Email/Verify flow, do not open as Gate Ticket

### Checklist Before Opening a Case
1. Portal identified (Kory / Gate / Commercial / unclear)
2. Account Email collected
3. Public IP collected (for Instance/VM/Network cases)
4. Case type classified (Request / Incident)
5. Customer details summarized (symptoms, request, time, service info)
6. Attachments noted (customer can add later in the ticket)

### Response Policy
- Callback is NOT the primary channel for closing cases
- Always reply via Ticket or Email for full history and documentation
- Outside working hours: "The team will check and update via Ticket on the next business day"
