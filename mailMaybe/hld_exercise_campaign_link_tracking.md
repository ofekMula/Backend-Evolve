# HLD Exercise for Tech Leads: Campaign Link Tracking

## Context

MailMaybe is an emerging SaaS company that provides an email campaign platform.

MailMaybe’s customers are campaign managers. They use the platform to create, launch, and measure marketing campaigns.

A typical campaign starts with an HTML email template. The template may include visual elements, personalized text, and links to the customer’s landing pages.

For example, a customer named **GarlicRings** may create a campaign that links to a hot-deals landing page:

```text
https://garlicrings.biz/landing123
```

The campaign manager also selects the target audience for the campaign. In many cases, this includes all subscribers, but sometimes it includes only a specific segment or subset of contacts.

When the campaign is launched, MailMaybe sends a personalized email to each target contact. For example, the template:

```html
Hi {{name}},
```

may be rendered as:

```html
Hi John,
```

Each recipient receives a personalized version of the email.

---

## Requested Feature

The product team wants to add **link tracking** to MailMaybe.

When a campaign email contains a URL that points to the customer’s landing page, MailMaybe should be able to automatically replace that URL with a MailMaybe tracking URL.

For example, instead of sending the recipient this original URL:

```text
https://garlicrings.biz/landing123
```

MailMaybe may rewrite the email so that the recipient sees and clicks a URL such as:

```text
https://mailmaybe.com/<something>
```

When the recipient clicks the MailMaybe URL, MailMaybe should first record the click and then redirect the recipient to the original customer URL:

```text
https://garlicrings.biz/landing123
```

The redirect should use an HTTP redirect, such as `302 Found`.

---

## Product Requirement

The feature should include a new customer-facing screen that allows campaign managers to measure engagement for each campaign.

At minimum, the screen should show:

- How many emails were sent for the campaign.
- How many tracked links were clicked.

You may suggest additional useful engagement metrics if you think they are relevant.

---

## Your Task

Write an HLD document for this feature.

The HLD should describe the proposed design at a high level, focusing on the main technical and product decisions required to deliver the feature safely.

Your document should be written as if you are a tech lead preparing the design for review with engineering, product, and relevant stakeholders.

---

## Points to Consider

Your HLD should address the following areas.

### 1. Stakeholders

Identify the relevant stakeholders for this feature.

Partial list:

- Campaign managers (customers)
- Product managers.
- Backend engineers.

You may add additional stakeholders if relevant.

---

### 2. Goals and Non-Goals

Define what this feature is expected to achieve.

Also define what is explicitly out of scope for the first version.

For example, consider whether the first version should include:

- Campaign-level metrics only.
- Per-link metrics.
- Per-recipient metrics.
- Bot-click filtering.
- Conversion tracking after the user reaches the customer’s landing page.

---

### 3. Success Criteria

Define how the team will know that the feature was successful.

Consider both product and technical success criteria.

For example:

- What should the customer be able to see?
- What level of correctness is expected from the metrics?
- What level of reliability is expected from the redirect flow?
- What performance expectations should be met?

---

### 4. High-Level Architecture

Describe the main components that are needed to support this feature.

---

### 5. Main Flows

Describe the important flows in the system.
You may use diagrams, bullet points, or sequence-style descriptions.

---

### 6. Feature Flag and Rollout

Describe how this feature should be rolled out safely.

---

### 7. Non-Functional Requirements

Discuss the important NFRs for this feature.

At minimum, consider:

- Availability.
- Latency.
- Retention.

