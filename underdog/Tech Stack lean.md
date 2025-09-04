# Teck Stack

A pretty lean and modern stack 👌 

Let me break it down in terms of **fit, costs, and potential gaps**:

---

### ✅ Strengths of this stack

1. **Fullstack framework – Next.js**

   * Free, widely adopted, great for SEO and server-side rendering.
   * You’ll get strong community support and long-term stability.

2. **Database – Supabase (\$25)**

   * Postgres-based, great developer experience, built-in auth and storage.
   * Scales well for early SaaS/MVP stages.

3. **Emails & Automation – Bento (\$0.01/user)**

   * Very cheap at scale, and integrates nicely for marketing automation.
   * Useful if you plan lifecycle emails (onboarding, retention).

4. **Hosting – Hetzner + Coolify (\$4+)**

   * Cost-efficient, especially compared to Vercel or AWS.
   * Coolify gives a Heroku-like developer experience with self-hosting flexibility.

5. **Analytics – Plausible (Free for self-hosted)**

   * Lightweight, privacy-focused.
   * Ideal for startups avoiding Google Analytics bloat.

6. **Support – Fernand (\$29 per active agent)**

   * Cheaper than Intercom/HelpScout for a small team.
   * Covers chat, support desk, FAQs.

7. **Social Media Scheduling – Typefully (\$12.50)**

   * Focused on X/Twitter growth, simple and effective.
   * Could be optional early on unless content marketing is core.

8. **Sales – Polar (4% + \$0.40/transaction)**

   * Very lean way to monetize.
   * Transparent fee structure, no heavy SaaS lock-in.

---

### ⚖️ Things to Consider

* **Auth**: Supabase includes authentication, but if you need more granular enterprise auth (SSO, role-based access control), you may eventually need Auth0/Clerk.
* **Scaling Costs**: Hetzner is cheap, but Supabase + email automation could spike depending on your user growth.
* **Integrations**: Make sure Typefully + Polar + Bento can all be tied back into your CRM (if you plan to use one).
* **Vendor Lock-in**: Supabase and Bento are startups themselves — if they change pricing, you’ll need a migration plan.
* **Compliance**: If you’re handling payments via Polar, double-check their compliance (GDPR, PCI-DSS) to avoid surprises later.

---

### 💰 Rough Monthly Cost Estimate (for early-stage startup)

* **Next.js**: \$0
* **Supabase**: \$25
* **Bento**: \$10 (assuming \~1k users = \$10)
* **Hetzner + Coolify**: \$10–20
* **Plausible**: \$0 (self-host)
* **Fernand**: \$29 (1 agent)
* **Typefully**: \$12.50
* **Polar**: Only when you sell

👉 Total fixed \~ **\$85–100/month**, plus sales fees. That’s really lean for running a SaaS.

---
