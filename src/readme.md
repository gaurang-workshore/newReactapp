# SearchForma - Design Scope 3: Terminology & Help System
## Scope of Work Document

**Project:** SearchForma 3.0  
**Date:** December 25, 2024

---

## 1. PROJECT OVERVIEW

Build a comprehensive terminology and help system for SearchForma to serve two distinct user groups:
- **Expert Investors**: Need quick data access without interruptions
- **Newcomers**: Need contextual education on real estate investment terms

**Design Principle**: Assume users have limited financial/real estate knowledge. Prioritize clarity, simplicity, and speed.

---

## 2. DELIVERABLES

### 2.1 Info Icon System

**What to Build:**
- Reusable ⓘ icon component with states (default, hover, active)
- Tooltip/pop-up component that displays:
  - Short definition (1-2 sentences)
  - "View full definition →" link to glossary

**Where to Place:**
Audit ALL pages and add info icons next to these terms:

| Term | Location | Example Placement |
|------|----------|-------------------|
| Cap Rate | Property metrics | "Cap Rate: 6.2% ⓘ" |
| Cash-on-Cash Return | Financial summary | "CoC Return: 8.5% ⓘ" |
| NOI | Income/expense breakdown | "NOI: $12,450 ⓘ" |
| DSCR | Financing assumptions | "DSCR: 1.25 ⓘ" |
| Gross Rent Multiplier | Valuation metrics card | "GRM: 12.5 ⓘ" |
| Price Per Square Foot | Property overview | "$125/sqft ⓘ" |
| Take Home Equity | Proforma/exit sections | "Take Home: $45,000 ⓘ" |
| Fair Market Rent | AI analysis | "FMR: $1,200/mo ⓘ" |
| Vacancy Rate | Cash flow projection | "Vacancy: 5% ⓘ" |
| CapEx Reserve | Operating expenses | "CapEx: $200/mo ⓘ" |
| Property Taxes | Expense line items | "Taxes: $2,400/yr ⓘ" |
| HOA Fees | Expense section | "HOA: $50/mo ⓘ" |
| Equity Multiple | Valuation metrics | "EM: 2.74x ⓘ" |
| IRR | Financial projections | "IRR: 15.2% ⓘ" |

**Terms by Page:**

**Homepage/Landing:**
- SFR (Single-Family Rental)
- Cap Rate
- Equity Multiple
- Take Home Equity
- Cash-on-Cash Return
- Expense Ratio
- Persona: Reinvestor, cash flow, appreciation

**Search Results & Property Cards:**
- Cash-on-Cash
- Initial Cash-In
- Days on Market
- Disposition Cost
- FormaIQ

**Property Detail Page (PDP):**
- IRR
- Yield on Cost
- Appreciation
- Comparable Sales (Comps)
- Absorption Rate
- Entry Cap Rate
- Initial Cash-on-Cash Return
- Projected IRR
- Annual CoC Return
- Exit Cap Rate
- Cash Flow After Debt Service

**Behavioral Consideration:**
- Only show info icon on FIRST occurrence of a term per user session
- Consider hover delay: Should definition appear after X seconds of hovering?
- Avoid overwhelming users with too many icons

---

### 2.2 Glossary Page

**What to Build:**
Full-featured glossary page with:
- **100+ terms** (client will provide full list)
- **A-Z navigation** (jump to letter sections)
- **Search functionality** (real-time filtering)
- **Categories** (group related terms)
- **Clean, professional styling** matching SearchForma brand

**Structure:**
```
[Search Bar]
[A] [B] [C] [D] ... [Z]

--- A ---
Absorption Rate
  Definition: The rate at which available properties...
  [Related: Days on Market, Inventory]

Appreciation
  Definition: The increase in property value over time...
  [Related: Cap Rate, Equity Multiple]
```

**Client Deliverable:**
- Client will provide full glossary with 100 terms
- We implement the design and functionality

---

### 2.3 Disclaimer System

**Component Types:**

**A. Data Freshness Disclaimer**
- Appears when user clicks ⓘ next to timestamps
- Text: 
  > "The last time we pulled this information was [timestamp]. Market conditions may have changed since this data was collected. Numbers shown are projections based on current market dynamics and are subject to change."
  > 
  > [View full disclaimer →]

**B. Investment Disclaimer**
- Appears in financial projections sections
- Text: "Not financial advice" disclaimer

**Placement Locations:**

| Location | Disclaimer Type |
|----------|----------------|
| AI Analysis Section | Timestamp + data freshness |
| Financial Projections | Investment disclaimer |
| Email Notifications | Footer disclaimer + Policy link |
| Global Footer | Links to Policy, Disclaimer, Glossary |

**What to Build:**
- Reusable disclaimer pop-up component
- Timestamp formatting utility
- Policy & Disclaimer page (client will provide copy)

---

### 2.4 Email Templates

**Required Email Types:**

**1. Deal Alert Emails**
- Subject: "Matches for Your Saved Search: 1.4x under $50,000"
- Includes:
  - Property image
  - Address
  - Price
  - Key metrics (Equity Multiple, Initial Investment)
  - CTA: "View Property Details"

**2. Investment Update Email**
- Subject: "An investment just got better 📈"
- Shows:
  - Property you're tracking
  - Metric changes table
  - Updated values
  - CTA: "View Updated Proforma"

**3. Welcome Email**
- Platform overview
- Link to Glossary
- Quick Reference Card
- Getting started guide

**4. Verification Email**
- Clear CTA for email verification
- Disclaimer footer

**5. Saved Search Alerts**
- "Data as of [timestamp]"
- Disclaimer footer
- Matching properties

**All Emails Must Include:**
- Footer with links to Policy & Disclaimer page
- Disclaimer text
- Unsubscribe option
- SearchForma branding

**Design Requirements:**
- Responsive (mobile-friendly)
- Match SearchForma brand colors/fonts
- Professional, clean layout
- Clear CTAs

---

### 2.5 FormaIQ Branding Fix

**Issue:**
Need to fix spacing and font treatment for "formaIQ" logo

**Requirements:**
- Match the style of "searchforma" logo
- Specific "f" treatment (client has reference)
- Consistent spacing

**Action:**
- Review attached reference from client
- Apply same styling treatment

---

## 3. CLIENT DELIVERABLES NEEDED

**What Client Will Provide:**
- [ ] Full glossary with 100 terms and definitions
- [ ] Disclaimer copy for Policy & Disclaimer page
- [ ] FormaIQ logo reference/specifications
- [ ] Approval on info icon placement locations
- [ ] Email copy for all template types

---

## 4. SUCCESS METRICS

**How to measure success:**
- Info icon interaction rate (what % of users click?)
- Glossary page visits
- Time spent on glossary
- Search queries in glossary
- Email open rates
- Email click-through rates
- User feedback on clarity

---

## 5. OUT OF SCOPE

The following items are NOT included:
- Writing glossary definitions (client provides)
- Writing disclaimer legal copy (client provides)
- Changing existing page layouts (only adding icons)
- Backend API changes (unless needed for glossary data)
- SEO optimization
- Analytics setup (beyond basic event tracking)

---

## 6. RISKS & MITIGATION

| Risk | Impact | Mitigation |
|------|--------|------------|
| Client delays providing glossary content | High | Start with sample terms, build infrastructure |
| Too many info icons overwhelming users | Medium | A/B test icon density, user feedback |
| Email deliverability issues | Medium | Test with multiple email clients, follow best practices |
| Mobile tooltip UX challenges | Medium | Prototype early, user test on mobile devices |
| Performance impact of tooltips | Low | Lazy load, optimize rendering |

---

## APPENDIX A: TERM CATEGORIES

**Suggested Categories for Glossary:**

1. **Financial Metrics**
   - Cap Rate, Cash-on-Cash, IRR, Equity Multiple, etc.

2. **Property Metrics**
   - Price Per Square Foot, Days on Market, Absorption Rate

3. **Income & Expenses**
   - NOI, CapEx Reserve, Property Taxes, HOA Fees

4. **Financing Terms**
   - DSCR, LTV, Down Payment

5. **Valuation Methods**
   - Comparable Sales (Comps), Gross Rent Multiplier

6. **Investment Strategy**
   - Appreciation, Cash Flow, Equity

7. **Market Terms**
   - Fair Market Rent, Vacancy Rate

---

## APPENDIX B: EMAIL TEMPLATE WIREFRAMES

*Include screenshots/mockups from the PDF pages 5-6*

**Example 1: Deal Alert Email**
- Header: SearchForma logo
- Subject: "Matches for '1.4x under $50,000'"
- Property image
- Address link
- Key metrics
- CTA button

**Example 2: Investment Update Email**
- Header: SearchForma logo
- Title: "An Investment Just Got Better 📈"
- Property image
- Metric changes table
- CTA: "View Updated Proforma"
- Footer disclaimer

---

**End of Scope Document**
