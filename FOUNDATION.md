# FLIPNET — Foundation Document

**Author:** Jake Hoover, Founding Chair
**Companion document:** `CONSTITUTION.md`

> This document is the technical and operational source of truth for FLIPNET. The Constitution is the governance covenant. The Constitution wins on matters of governance and mission; this document wins on matters of architecture, technology, and operations. They are designed to be consistent. Conflicts between them are flagged and resolved.

---

## Part I: What This Is

FLIPNET is permanent public infrastructure for human communication, built to outlast its founder, governed eventually by a Swiss Foundation (Stiftung), operated by no one for personal profit, and given to humanity once it is worthy of the gift.

There is no launch date. The platform launches when it is ready. It is self-funded by the founder and has no revenue dependencies. The first dollar of platform surplus goes into the Stiftung formation fund.

Every participating account belongs to a real, government-verified human, costs $5/year, and is renewed annually. No bots. No anonymous abuse. No farms of fake accounts.

The Stiftung handoff is scaffolded into the codebase from day one — every admin action audit-logged, every governance decision exportable, every financial transaction publishable. When the Board exists, it inherits a complete record. The Stiftung is not a destination. The Stiftung is the architecture.

---

## Part II: Founding Principles

These are the non-negotiable commitments that govern every decision in this project. They are not marketing copy. They are operating constraints. They are also encoded in the Constitution as irrevocable provisions (see Constitution §1.5 and Article XV).

### 1. Verified humans only
Every participating account is a real, verified human. Verification is performed by Stripe Identity and lasts twelve months. The cost is $5 USD or local equivalent annually. This is the foundation that makes everything else possible.

### 2. Non-extractive forever
No advertising based on behavioral data. No selling user data. No algorithmic manipulation designed to maximize time-on-platform. No equity offerings. No acquisition by a larger platform. No premium features that create a different platform experience for paying users. Surplus revenue, when it exists, flows to the Community Distribution Fund per the Constitution. The founder draws no profit from the platform's operations.

### 3. Transparent by construction
Every algorithm that affects content visibility is documented in plain language. Every admin action is logged in an immutable audit trail. Every financial transaction is recorded for quarterly publication. The codebase is open source under AGPL-3.0 from the first commit. There are no hidden systems.

### 4. Built for transfer
Every line of code, every database schema, every operational decision is made knowing that the platform will eventually be transferred to a Swiss Foundation governed by a board of the most ethical people we can find. The current founder is a custodian, not an owner. The architecture reflects this from day one.

### 5. Honest about limits
Where we cannot make a guarantee, we say so. Where we are still building, we say so. Where the law forces compliance with something we would rather not do, we say so transparently. Trust is built through honesty about what we can and cannot promise.

---

## Part III: Governance

### The path to the Stiftung

FLIPNET is owned by FLIPNET LLC (Oregon Registry #255242399), a single-member LLC with Jake Hoover as the sole member. The path to the Swiss Foundation (Stiftung) is described in detail in the Constitution (Article I). The summary:

**Phase 1 — Founder operation (today through ~Year 2):** The founder operates the platform, makes all governance decisions, and self-funds infrastructure. Every decision is logged in the audit trail. The founder commits in writing to the principles in this document and the Constitution.

**Phase 2 — Board search (Year 1–3, parallel):** The platform is used as a search mechanism to find the most ethical, mission-aligned board members available. This is an ongoing identification of people whose values match the mission, who have demonstrated integrity in public, and who would accept the responsibility of governance.

**Phase 3 — Stiftung formation and transfer:** When a credible board exists, when the platform has demonstrated stability, and when the founder has secured ~$10k for Swiss legal formation, the Stiftung is formed and the LLC transfers all platform assets, intellectual property, and governance authority to it. This is a gift, not a sale.

There is no deadline for Phase 3. It happens when it should happen. The Constitution defines a compelled-transition trigger (§1.3) as a structural defense against indefinite postponement.

### Governance scaffolding in the codebase

Even though no board exists yet, the platform is built as if it always existed:

- All admin and superuser actions are written to an append-only audit log with cryptographic chain hashing.
- Every financial transaction is categorized and tagged for quarterly reporting.
- Every moderation decision is exportable in a standardized format.
- A `governance_decisions` table tracks every formal policy change with rationale.
- A read-only public transparency dashboard publishes summary statistics (without personal data) on a schedule.

When the board takes over, they inherit a complete history.

### The Constitution

The FLIPNET Constitution (`CONSTITUTION.md`) is the binding governance covenant. The technical architecture in this document supports the governance commitments in the Constitution. They are paired documents — neither stands alone.

---

## Part IV: The Verified Humans Positioning

### Why $5/year

Five dollars is enough to be a meaningful spam moat. A bot operator who needs ten thousand accounts is now looking at fifty thousand dollars per year and the practical problem of obtaining ten thousand government-verified identities. Not impossible to bypass at small scale; uneconomical at any meaningful scale.

Five dollars is also small enough to not exclude users on financial grounds. A coffee in any developed country costs more. Scholarship verification is offered to users who genuinely cannot afford the fee, processed through community sponsorship: a verified user in good standing may sponsor verification for one other user per calendar year. The one-per-year cap is structural — it prevents sponsorship from becoming a back door for coordinated account creation while keeping the platform accessible.

The $5 covers underlying costs and contributes a small operational margin. Stripe Identity charges $1.50 per verification. Stripe's billing fee on a $5 charge is ~$0.45 (2.9% + $0.30). That leaves ~$3.05 per verified user per year for infrastructure, moderation, and the Stiftung formation fund. The fee is not where the platform makes money. It is where the platform pays for itself.

### Why annual renewal

People change. Accounts dormant for over a year are statistically more likely to have been compromised, abandoned, or sold. Annual re-verification ensures every participating account belongs to a real, current human who still wants to be there. It also provides a regular touchpoint for refreshing user agreement to the Constitution.

A user whose verification lapses does not lose their account or content. They lose the ability to post, comment, react, message, or vote until re-verified. They retain read access and can re-verify at any time. Their data is theirs and remains exportable regardless of verification status.

Lifetime verification was considered and rejected. The lifetime model creates a treadmill where every dollar of revenue must come from new users forever, with no recurring base. The annual model produces predictable revenue, prunes dormant accounts naturally, and reinforces the verification commitment over time.

### What this enables

A guaranteed-no-bots social platform is the most valuable real estate on the internet right now. Every other platform is being overrun by AI-generated content, automated influence operations, and spam at scale. FLIPNET does not have this problem by construction.

This positioning is also impossible to copy. Platforms with user bases built on anonymity cannot reverse course without alienating the users they have. FLIPNET starts from the verified position and never deviates.

Verified identity is also the foundation for the governance promise: it is what makes verified voting in board elections possible, what makes the Ethos reputation system meaningful, and what makes "one person, one account" enforceable. Almost every other commitment in this document depends on this one.

### Account states

| State | Capabilities | Cost |
|---|---|---|
| **Visitor** (default) | Read anything public: posts, comments, profiles, business pages, news. No account required. | Free |
| **Unverified account** | Identical to Visitor at launch (account exists, can hold preferences). Does not gate additional features beyond Visitor. | Free |
| **Verified Member** | Everything else: post, comment, react, vote, flag, message, follow, create groups, claim businesses, suggest sources. | $5/year |
| **Lapsed Verified Member** | Read-only access to their own account; re-verify at any time to restore full Verified Member status. | Re-verify any time |

### Verification flow

1. Email + password signup → Unverified account (read-only).
2. User initiates verification → Stripe Checkout for $5 (annual) + Stripe Identity session.
3. On Identity success + payment capture → account flips to `verification_level = 2`, expiration set +12 months, member number assigned (if launch window). Idempotent via webhook + outbox.
4. Failure modes:
   - **Payment fails:** no charge, user can retry.
   - **Identity verification fails:** automatic refund minus Stripe fees, account locked from re-attempt for 30 days, appeal path via support.
   - **Webhook delivery fails:** outbox pattern + retry guarantees eventual consistency.

### Stripe Identity data-flow contract

What we store, what we don't, and why. This contract is binding — any change requires an ADR and explicit reference to Constitution §3.4.

**What we store, per verification:**
- `stripe_identity_verification_id` (Stripe's token, no PII)
- `identity_provider` (string; `stripe_identity_v1` at launch — see Principle 21 for the provider-swappability requirement)
- `verified_at` (timestamp)
- `verification_expires_at` (timestamp, +12 months)
- `identity_hash_primary` — when Stripe returns a government ID number, this is `HMAC-SHA256(server_pepper, id_number || country)`. The HMAC pepper lives in the secrets store, never in the database, and rotates annually with a documented re-hash migration.
- `identity_hash_fallback` — when the ID number is not available, this is `HMAC-SHA256(server_pepper, normalized_name || normalized_DOB || country)`. Normalization is lowercase + trim + strip diacritics + ISO-format the DOB.
- `country` (ISO 3166-1 alpha-2, for jurisdiction routing)
- `is_18_or_older` (boolean, for age gate)

**What we never store:**
- The government ID number itself (only its HMAC)
- Document images (passport scan, license photo, etc.)
- The selfie image used for liveness check
- Full date of birth (only the derived `is_18_or_older` boolean and the HMAC-hashed normalized form)
- Full address (only the country code)

Stripe Identity holds the underlying documents on their infrastructure for the period required by their compliance obligations and then deletes them per their published retention policy. FLIPNET never sees them. This is the privacy-preserving verification model the Constitution requires.

**One-account-per-person enforcement** uses two-tier match logic:

1. **Primary match (high confidence):** if a new verification's `identity_hash_primary` collides with an existing verified user's `identity_hash_primary`, the new verification is auto-blocked. ID numbers are globally unique within a country's issuing authority; a collision here is almost certainly the same person trying to create a duplicate account.

2. **Fallback match (low confidence):** if `identity_hash_primary` is unavailable and `identity_hash_fallback` collides with an existing verified user's `identity_hash_fallback`, the new verification is **not** auto-blocked. Two unrelated humans named "James Smith" born "1990-01-01" in "US" produce identical fallback hashes — auto-rejecting them would be a bug, not a security feature. The verification routes to a manual review queue in the superuser dashboard. Reviewer confirms or rejects based on Stripe Identity's underlying record.

Edge cases (legal name changes, document re-issues that change either hash) also flow to manual review.

**Jurisdictional gating at the Stripe Identity layer:**

Until the platform has EU-region infrastructure (Neon Frankfurt + Railway EU), Stripe Identity sessions are restricted to US-issued documents only. This restriction is configured in Stripe Identity itself, not just at the application layer — non-US verification attempts are blocked before Stripe accepts the session, preventing EU/UK/CH personal data from ever touching US-hosted infrastructure. International rollout is tracked as Decision #10 in Part XII; it requires both EU infrastructure and an explicit ADR before the gate lifts.

---

## Part V: Technical Architecture

### Stack overview

| Layer | Technology | Rationale |
|---|---|---|
| Language (backend) | TypeScript on Node.js | Type safety eliminates entire categories of bugs. |
| Backend framework | Fastify | Faster than Express, first-class TypeScript, built-in schema validation. |
| Database | PostgreSQL on Neon | Serverless Postgres with branching and point-in-time recovery. US region at launch; region-pinned to Railway US to avoid cross-region latency. EU migration path documented for international expansion. |
| ORM / query layer | Drizzle ORM | Typed queries from schema, prevents SQL injection by construction, raw SQL escape hatch when needed. |
| Cache | Upstash Redis | Serverless, pay-per-request, no connection-pool problems. |
| Background jobs (transactional) | Postgres `SELECT ... FOR UPDATE SKIP LOCKED` outbox drain | Postgres-native outbox keeps transactional integrity in one system. |
| Background jobs (scheduled) | BullMQ on Redis + `pg_cron` for simple cron | BullMQ for scheduled tasks (RSS polling, digests, expiry checks); `pg_cron` for daily housekeeping that doesn't need queue semantics. |
| Real-time (one-way) | Server-Sent Events (SSE) | Native to the stack, cheap, perfect for notifications and feed updates. |
| Real-time (two-way) | Ably (with documented exit ramp) | Managed WebSocket infrastructure for DMs and presence. DM data model designed transport-swappable from day one. |
| Authentication | Better Auth | Actively maintained; battle-tested session management; no hand-rolled JWT edge cases. |
| Identity verification | Stripe Identity (with documented exit ramp via `identity_provider` abstraction) | Industry standard; integrates with Stripe billing. Persona is pre-evaluated as dormant secondary. See Principle 21. |
| Payments | Stripe (subscriptions + Identity, with documented exit ramp) | Single vendor for verification fee + future patronage subscriptions. Outbox-driven billing operations abstract so a future migration is mostly an outbox replay. See Principle 21. |
| Validation | Zod | Single source of truth for API contracts, TypeScript types, and form validation. |
| Frontend (web) | React 18 + Vite | Modern, fast, well-supported. |
| Frontend (mobile) | React Native via Expo | True native iOS and Android from a shared codebase. |
| Monorepo | pnpm workspaces + Turborepo | Shared business logic between web and mobile; parallel builds. |
| Styling | NativeWind (Tailwind for web + native) | Single styling system across all surfaces. |
| State (server) | TanStack Query | Industry standard for server state with caching and revalidation. |
| State (client) | Zustand | Minimal, simple, no boilerplate. |
| File storage | Cloudflare R2 | S3-compatible with no egress fees. |
| Email (transactional) | Resend | Clean API, good deliverability. |
| Email (lists) | TBD (Buttondown or similar) | Not Resend — they are for transactional only. |
| Search | Postgres FTS at launch → Meilisearch when needed | Do not add a search service until Postgres FTS demonstrably chokes. |
| Hosting (app) | Railway (US region) | Auto-deploy from git; colocated with Neon US to avoid cross-region latency. |
| CDN / DNS / WAF | Cloudflare | Security and performance layer. |
| Monitoring (errors) | Sentry | Industry standard error tracking with performance monitoring. |
| Observability | OpenTelemetry → Grafana Cloud | Traces + metrics + logs in one place. |
| Logging (structured) | Pino → Axiom | Queryable structured logs at scale. |
| Testing (unit) | Vitest | Fast, modern, plays well with TypeScript. |
| Testing (e2e) | Playwright | Real-browser end-to-end testing. |
| CI/CD | GitHub Actions | Required checks on every PR; main branch always deployable. |
| License | AGPL-3.0 | Open source from day one; protects mission-driven code from commercial exploitation. |

### Explicitly not used

- **Vercel hosting** — Railway is the platform; avoid Vercel-specific lock-in.
- **Supabase / Firebase** — explicit ownership of DB and auth, not BaaS.
- **A separate SPA framework** — React + Vite is enough; no Next.js, no separate API gateway.
- **ElasticSearch** — Meilisearch later if needed; ES is overkill.
- **Kafka / RabbitMQ** — Postgres outbox + Redis + BullMQ is sufficient at every scale we will see.
- **JWT in localStorage** — sessions in httpOnly cookies via Better Auth.
- **Behavioral analytics SDKs** (Mixpanel, Amplitude, Segment) — privacy commitment incompatible.
- **Lucia** — entered maintenance-only mode; not suitable as a foundational dependency.

### Repository structure

FLIPNET lives in three repositories under `mrhoovermt`.

**`flipnet-v2`** (public, AGPL-3.0, open from Phase 0). The main codebase.

```
flipnet-v2/
├── apps/
│   ├── web/              # React + Vite — flip-net.com
│   ├── mobile/           # Expo React Native — iOS and Android
│   └── api/              # Fastify backend
├── packages/
│   ├── database/         # Drizzle schema + migrations
│   ├── shared/           # Types, Zod schemas, constants
│   │   └── src/
│   │       └── constitutional-constants.ts   # CODEOWNERS-locked; encodes Constitution §15.2
│   ├── ui/               # Shared UI primitives (NativeWind components)
│   └── governance/       # Audit logging, transparency reporting, board tooling, verifier CLI
│                         # Published as @flipnet/governance to npm
├── governance/           # Repo-level governance artifacts (not code)
│   ├── ip-ledger.md
│   ├── secrets-inventory.md
│   ├── vendors.md
│   ├── domains.md
│   ├── contributors.md
│   └── runbooks/
│       └── pitr-reconciliation.md
├── infrastructure/
│   ├── neon/
│   ├── upstash/
│   └── ably/
├── docs/
│   ├── FOUNDATION.md
│   ├── CONSTITUTION.md
│   ├── ARCHITECTURE.md     # Living technical reference (generated from code where possible)
│   ├── DECISIONS/          # Architecture Decision Records (ADRs)
│   ├── SKILLS/             # CC skill files
│   └── analysis/           # Pre-build agent reviews, post-launch audits
├── scripts/
└── README.md
```

**`flipnet-v2-secrets`** (private). Operational parameters whose publication would help adversaries game the system, while the *methodology* remains public per Constitution §4.6.

```
flipnet-v2-secrets/
├── ethos/
│   ├── coefficients.json
│   └── thresholds.json
├── moderation/
│   ├── flag-thresholds.json
│   └── coord-detection.json
├── abuse/
│   └── heuristics.json
└── README.md
```

The Constitution requires publishing how Ethos and moderation work; it does not require publishing the specific numerical thresholds that make the systems harder to game.

**`flipnet-transparency`** (public, append-only). The audit log anchoring mirror. A weekly worker computes the Merkle root of all audit log entries since the previous anchor, anchors it via OpenTimestamps, and commits the root + proof + entry count with a signed commit. A daily worker also commits the latest entry hash and a chain integrity check between weekly anchors. A verifier CLI ships in the repo. Anyone — including future board members — can independently confirm the audit log has not been silently rewritten.

### Architecture principles

These shape every PR. They are non-negotiable defaults; deviating requires an ADR.

1. **Writes are idempotent.** Every external-facing write accepts an idempotency key. Stripe webhooks, email sends, post creation. Retry without fear.
2. **Outbox pattern for cross-system writes.** When a DB transaction needs to also fire an email, a Stripe call, or a webhook: write the side effect to an `outbox` table inside the same transaction; a worker drains it via `SELECT ... FOR UPDATE SKIP LOCKED`. Never split a commit across systems.
3. **Audit log is append-only AND externally anchored.** Moderation actions, Ethos changes, account state transitions, payment events, governance decisions. Never updated, never deleted. The full anchoring scheme:
   - Each entry computes `entry_hash = SHA-256(prev_hash || RFC8785_JCS_canonicalize(entry_payload))`.
   - A `chain_id` column survives Neon point-in-time restores: a PITR doesn't break the chain, it forks it, and forks are detectable.
   - **DB-level immutability is enforced before the application layer.** A `BEFORE UPDATE OR DELETE` trigger on the `audit_log` table rejects any non-INSERT operation. Row-level security policies deny `UPDATE` and `DELETE` to every role. A dedicated `audit_writer` Postgres role holds INSERT-only permissions; the application's normal connection user cannot reach the audit log to modify it. Cryptographic anchoring catches tampering after the fact; DB triggers prevent it from happening at all. Both layers are required.
   - A daily worker writes a signed commit to the public `flipnet-transparency` repo containing the latest entry hash, entry count since the previous daily commit, and a SHA-256 chain integrity check. This narrows the silent-tamper window from one week (between OTS anchors) to ~24 hours.
   - A weekly worker computes the Merkle root of all entries since the previous OTS anchor, anchors it via OpenTimestamps (free, Bitcoin-backed), and commits the proof to `flipnet-transparency` with a signed commit.
   - A verifier CLI ships in `flipnet-v2/packages/governance/` (published as `@flipnet/governance` to npm); `flipnet-transparency` consumes it as a pinned version. This prevents cross-repo drift — the verifier code is owned by one repo and used by both.
   - **Multi-signature anchoring (2-of-3) is active before the Phase 0 → Phase 1 gate is satisfied.** The three keys are held by: (a) the Founding Chair, (b) a sealed-envelope successor designated in the LLC operating agreement, (c) external counsel of record — the same external trustee named in Constitution §1.3 and §2.4. The Phase 0 audit log is single-key for the first phase only; that audit-log epoch is logged as such and the affected period is publicly disclosed in the transparency dashboard. Engagement of counsel and the resulting key ceremony are hard gates on the Phase 0 → Phase 1 transition.
   - This is what makes "the Stiftung is the architecture" verifiable rather than aspirational.
4. **Schema is additive.** `ALTER TABLE ADD COLUMN IF NOT EXISTS`. Never drop a column in a migration that ships with code still referencing it. Two-step deprecations only. No `DROP COLUMN` within 90 days of column creation.
5. **IDs are UUIDv7.** Sortable like bigints, globally unique, no leak of count.
6. **Reads can be stale; writes must be correct.** Cache aggressively (Redis), invalidate by version, accept that reads may lag a few seconds. Never serve a stale write to its own author.
7. **Background jobs over inline work.** Anything that talks to a third party (Stripe, Resend, R2, RSS) happens in a job, not in a request handler. Request handlers stay fast.
8. **Pagination is cursor-based, never offset-based.** Offset pagination breaks at scale.
9. **Boundaries enforce auth, not handlers.** Middleware decides visitor/unverified/verified once per request. Handlers trust the request object.
10. **Logging includes a trace ID.** Every log line carries the request's trace ID. OpenTelemetry from day one.
11. **Backups are tested.** Neon PITR is enabled; quarterly we restore one to a scratch DB and run a checksum. An untested backup is a wish.
12. **Feature flags exist from day one.** New features land dark, get turned on per-account, then per-cohort, then globally.
13. **All money math uses integer cents.** No floats. Currency is stored as `bigint` representing cents.
14. **All schema changes ship as Drizzle migrations committed to git.** Migrations run automatically on deploy and are tested in sandbox before production.
15. **Foreign keys are always indexed.** Postgres does not do this automatically.
16. **Two-tier deletion model.** GDPR right-to-erasure and audit log permanence are reconciled, not in conflict:
    - **Personal data is hard-deleted.** Email, profile content, photos, DMs, profile.md content, top friends — all wiped on account deletion. No tombstones with PII.
    - **Audit, Ethos, and moderation references are pseudonymized.** When a user deletes their account, their user_id in the audit log, Ethos events, and mod decisions is replaced with `SHA-256(user_id || destroyed_salt)` where the salt is generated per-deletion and immediately destroyed. The reference exists for moderation continuity but cannot be reversed back to the user.
    - **Foreign keys on audit/Ethos/mod tables use `ON DELETE RESTRICT`,** not `SET NULL` or `CASCADE`. The pseudonymization step must happen first; the FK then references the pseudonym row, not the deleted user row.
    - **All other user-action tables use `ON DELETE SET NULL`.** Comments don't disappear from threads when authors leave; they show as "[deleted]".
    - **PITR reconciliation runbook.** When Neon PITR restores the database to a moment before a user deletion, the destroyed salt is gone — the pseudonymization cannot be reproduced from the original user_id. The runbook (`docs/runbooks/pitr-reconciliation.md`) requires: identifying all deletions that occurred between the PITR target time and current time from the audit log, generating fresh per-deletion salts, re-pseudonymizing those references, and logging the reconciliation as a governance event. This must happen before any user traffic resumes after a restore.
17. **Hybrid feed fan-out.** Push for users with fewer than 5,000 followers (write fanout to followers' feed slices in Redis on every post). Pull for users with 5,000 or more followers (read-time merge of latest posts at view time). The threshold is configurable.
18. **The DM data model is transport-swappable.** Whatever real-time provider is in use, persistent storage and API contracts are designed so the transport layer can be replaced without changing message semantics, history, or client code. Concretely:
    - Every message carries a `client_message_id` (UUIDv7, client-generated, UNIQUE per conversation) and a `server_seq` (bigint, monotonically increasing per conversation, server-assigned). The client_message_id makes resends idempotent; the server_seq is the source of truth for ordering.
    - History is read from the FLIPNET REST API only, never from Ably's history API. The transport is a delivery channel, not a storage tier.
    - Message persistence in Postgres happens *before* publication to Ably (outbox pattern). If Ably is unreachable, messages are queued in the outbox and delivered when it returns.
    - This protects against Ably price changes and enables a future migration to self-hosted real-time (Centrifugo, `@fastify/websocket`) without a schema rewrite or history loss.
19. **Constitutional constants are codified in TypeScript.** The irrevocable provisions enumerated in Constitution §15.2 (verification annual cadence, three-vote maximum, premium-feature prohibition, behavioral-ad prohibition, etc.) live in `packages/shared/src/constitutional-constants.ts` as exported constants and predicate functions. The file is `CODEOWNERS`-locked to the Founding Chair (and, once formed, the Stiftung Board). A `featureUnlockedFor()` predicate function gates code paths that must respect a constitutional constraint, so the constraint is a compile-time and runtime check, not a comment. This makes "constitutional commitments are real" mechanically true.
20. **Bulk DM decryption requires multi-party authorization and user notification.** Any operator-initiated decryption of a DM beyond the small-volume case of a single reported message requires 2-of-2 superuser approval (two distinct human operators must approve). Every decryption — single-message or bulk — produces a user-facing notification to the affected user(s) within 15 minutes, except where a court order compels non-disclosure (in which case the delay is itself logged to the audit trail with the court order docket reference). The structural defense against the "future operator as panopticon" failure mode is this notification, not a policy promise.
21. **Critical-path vendors have documented exit ramps.** The Constitution promises perpetuity. Perpetuity cannot rest on a single vendor's continued willingness to serve the platform. For every vendor on the critical revenue, identity, or messaging path, the platform maintains a structural exit ramp:
    - **Identity verification:** the `identity_provider` column on the verification record defaults to `stripe_identity_v1`. A `verification_provider` abstraction layer in code allows a second provider (Persona is the pre-evaluated secondary) to be added behind a feature flag. A dormant Persona account is opened during Phase 0 and kept in good standing.
    - **Payments / billing:** Stripe billing operations are abstracted through the outbox pattern. The migration path to an alternate processor (Paddle, LemonSqueezy, or similar) is mostly a replay of the outbox against a new provider, not a schema rewrite. The `stripe_charge_id` column is renameable to `external_charge_id` with an `external_charge_provider` discriminator if needed.
    - **Real-time transport:** Principle 18 already covers this. The DM transport is swappable.
    - The shared pattern: every critical-path vendor relationship has (a) a column-level discriminator identifying the provider used for that record, (b) an abstraction layer in code, (c) a pre-evaluated secondary provider, and (d) a documented runbook for the migration. Without all four, the vendor is a single point of failure that the perpetuity promise cannot survive.

### Database design

The user model has the following verification levels, encoded as a `verification_level` column:

| Level | State | Capabilities |
|---|---|---|
| 0 | Visitor (no account) | Read public content only. Not stored as a user row. |
| 1 | Unverified account | Can hold preferences and follow public content for personalized reading. Cannot post, comment, react, message. |
| 2 | Verified Member (active) | Full platform participation. Verification expires annually unless renewed. |
| 3 | Lapsed Verified Member | Verification expired. Read-only own account; can re-verify to restore Level 2. |
| 4 | Trusted Member | Verified Member with sustained positive Ethos standing. Eligible for community moderation roles. Specific thresholds in the Ethos Methodology Document. |
| 5 | Governance-Eligible Member | Trusted Member with minimum tenure (one year). Eligible for Board candidacy. |

The `verification_method` column tracks how verification was achieved (Stripe Identity is the only method at launch).

The `verified_at` and `verification_expires_at` columns enforce the annual renewal cycle. A daily background job demotes lapsed accounts.

Sessions are managed by Better Auth. JWTs are not used. Sessions live in Postgres with Redis caching for hot reads. Session refresh is automatic and transparent. Device management is built in.

### Caching strategy

Three layers, used in this order:

1. **In-memory (per-process)** — for things that change rarely and are read constantly (platform config, feature flags). Invalidated via Redis pub/sub.
2. **Redis** — for session data, rate limit counters, hot user data, computed feed slices, OG link previews.
3. **Database** — for everything else.

A user's feed is a precomputed list of post IDs in Redis, regenerated when relevant events occur. The actual feed read is a Redis lookup followed by a single batched Postgres query. This pattern survives to millions of users without modification.

### Real-time strategy

**SSE for one-way events:** notification badges, feed update indicators, live moderation queue updates, live verification status changes.

**WebSockets via Ably for two-way interactions:** direct messages, typing indicators, presence, live community discussions.

Ably handles scaling, reconnection, fallbacks, message ordering, and global edge presence. Per Principle 18, the DM data model is transport-swappable; the migration to self-hosted (Centrifugo or `@fastify/websocket`) is a transport-layer swap, not a rewrite.

### Direct message encryption

DMs are encrypted at rest using a server-side envelope encryption scheme. The scheme is also designed to allow a later migration to end-to-end encryption via the Signal Protocol (libsignal) without changing the message data model.

**At rest:**
- Every DM conversation has a unique conversation key.
- Conversation keys are wrapped (encrypted) by a KMS master key.
- Messages are stored as `ciphertext` + `key_envelope` columns. Plaintext never lives in the database.
- The server can decrypt messages, but does so only for explicit moderation actions (a user-filed report or a court-ordered access). Every decryption is logged to the audit trail and triggers a user-facing notification per Principle 20.

**End-to-end (post-launch):**
- The schema includes `ciphertext` and `key_envelope` columns from day one specifically so the libsignal migration is a key-management change, not a schema rewrite.
- Migration timing is on the roadmap as a real deliverable. When it ships, the Constitutional commitments to user privacy get stronger; nothing else about the DM experience changes.

### API design

- **OpenAPI spec generated from Fastify route schemas.** Frontend consumes typed clients generated from this spec.
- **Zod validation on every endpoint, request and response.** Invalid input rejected before business logic. Invalid output rejected before reaching users.
- **Rate limiting on every endpoint.** Conservative defaults; specific endpoints get specific limits.
- **CSRF token required on every mutation.** Read endpoints are idempotent.
- **Pagination is cursor-based, never offset-based.**
- **Errors return structured error codes, not strings.** Frontend decides how to display them.

### Security posture

- **HTTPS only.** HSTS preload submitted from day one.
- **Strict Content Security Policy.** No inline scripts, no eval, no remote scripts except from explicit allowlist.
- **Server-side sanitization + DOMPurify client-side.** Defense in depth.
- **All file uploads pass through Sharp processing.** Stored with random UUIDs. Original filenames never used in URLs.
- **Type allowlists, size limits, virus scanning** on all uploads.
- **Step-up authentication for admin actions** — password + TOTP re-entry within last 5 minutes.
- **All sensitive operations logged to audit trail.** No exceptions.
- **Secrets managed via Railway secret store and 1Password.** Never in `.env` files committed to git.
- **Weekly Dependabot audit.** Security patches applied within 48 hours.
- **Annual penetration testing** once budget allows.

### CSAM detection and NCMEC reporting

US-presence platforms that accept user-uploaded content are required under 18 USC §2258A to report apparent CSAM to the National Center for Missing & Exploited Children (NCMEC). FLIPNET's compliance pipeline is built into the platform from the start.

- **ESP registration** at report.cybertip.org/espregistration is filed during Phase 0 to absorb the 3–6 week approval latency. The registration is a hard gate on Phase 2's photo upload.
- **PhotoDNA hash-matching** (or Cloudflare's CSAM Scanning Tool as the pre-evaluated secondary pending PhotoDNA access approval) runs on every uploaded image before publication. The pipeline is operational before Phase 2 ships.
- **A `csam_detected` boolean on uploads** blocks publication when true and triggers an automated NCMEC SUSP report via the CyberTipline API.
- **A small T&S review queue** surfaces uploads where the scanner returned an inconclusive result, with a documented review SLA. The full T&S operations program (staffing, escalation, after-hours coverage) is out of scope for the initial launch; the technical pipeline is mandatory because the legal floor cannot wait for operational headcount.

---

## Part VI: Operational Practices

### Environment strategy

Three environments, all real:

1. **Local** — Each developer runs the full stack locally via Docker Compose for Postgres and Redis. Hot reload everywhere. No internet required.
2. **Sandbox** — Deployed at `sandbox.flip-net.com`. Auto-deploys from the `sandbox` git branch. Used for integration testing, multi-device testing, stakeholder previews.
3. **Production** — `flip-net.com` and the mobile apps. Auto-deploys from `main` only after all CI checks pass.

Promotion path: feature branch → sandbox branch → main. Never skip sandbox.

### Migration discipline

- Every schema change ships as a Drizzle migration committed to git.
- Migrations run automatically on deploy.
- Migrations tested in sandbox before reaching production.
- The database is never wiped after the first verified user signs up.
- Rollback migrations exist for every forward migration.

### Deployment discipline

- Main branch always deployable.
- Every commit to main triggers full CI: typecheck, lint, unit tests, e2e tests on critical paths, build verification.
- Failed CI blocks merge.
- Deployments are atomic. If any service fails to start, deployment rolls back.
- Database migrations run before the new application version starts.
- Frontend assets are immutably versioned (no `?v=` cache busting; URLs change per deploy).

### Monitoring and alerting

- **Sentry** catches every error in production with full stack trace and anonymized user context.
- **Grafana Cloud** stores OpenTelemetry traces, metrics, and logs queryable for any time range.
- **Health checks** run every 30 seconds against `/health` endpoints on every service.
- **Alerts** fire to founder's phone via PagerDuty for sustained error rates above baseline, database connection issues, payment processing failures, security events.
- **Weekly review:** Founder reviews Sentry, performance dashboards, and audit log highlights every Monday.

### On-call and incident response

The founder is on-call initially. As the platform grows, this rotates among trusted contributors.

Every incident generates a postmortem in `/docs/incidents/YYYY-MM-DD-name.md`. Postmortems are blameless. They document what happened, why, what was done, and what changes prevent recurrence. Postmortems for incidents that affected users are published on the public transparency page.

---

## Part VII: Financial Model

### Revenue sources

In order of priority:

1. **Verification fees** ($5/user/year) — covers Stripe Identity costs, Stripe billing fees, and contributes a small operational margin. Not a profit center.
2. **Voluntary subscriptions** — supporters can contribute beyond the verification fee. Flat tiers ($5/mo, $20/mo, $100/mo). No premium features. The platform is the same for everyone. Patronage, not pay-to-win.
3. **Contextual advertising** — matched only to the topic of content being viewed, never to user behavior or identity. Implemented well after launch, when traffic justifies it. Revenue per impression is significantly lower than behavioral advertising; that is the point.
4. **Community Distribution Fund grants from foundations and donors** — once the Stiftung exists, mission-aligned grants become a possible revenue source.

The platform never sells data, never runs behavioral ads, never offers paid amplification, and never charges for features that affect user experience. These are constitutional commitments (Constitution Article VII).

### Per-user economics

Every verified user generates the following annual cash flow:

| Line item | Amount |
|---|---|
| Verification fee (gross) | +$5.00 |
| Stripe Identity verification | −$1.50 |
| Stripe billing fee (2.9% + $0.30) | −$0.45 |
| **Net per verified user per year** | **+$3.05** |

As long as net per-user revenue exceeds per-user infrastructure cost, the platform is sustainable at any scale. Infrastructure cost per user drops dramatically as scale increases; net per-user revenue stays constant.

### Cost projections by scale

**Development phase (~0 users):**
- Infrastructure: ~$60/month, mostly free tiers plus existing Cloudflare Pro
- Revenue: $0
- Annual burn: ~$720/yr (founder-funded)

**Quiet launch (~1,000 verified users):**
- Infrastructure: ~$100/month = $1,200/yr
- Net verification revenue: $3,050/yr
- After infrastructure: **+$1,850/yr surplus**

**Real traction (~10,000 verified users):**
- Infrastructure: ~$350/month = $4,200/yr
- Net verification revenue: $30,500/yr
- After infrastructure: **+$26,300/yr surplus**

**Scale (~100,000 verified users):**
- Infrastructure: ~$2,400/month = $28,800/yr
- Net verification revenue: $305,000/yr
- After infrastructure: **+$276,200/yr surplus**

**Long-term scale (~1,000,000 verified users):**
- Infrastructure: ~$15,000/month = $180,000/yr (extrapolated; would likely involve self-hosted Postgres in Switzerland by this point)
- Net verification revenue: $3,050,000/yr
- After infrastructure: **+$2,870,000/yr surplus**

### What the math means

Every user pays for their own infrastructure cost many times over via the verification fee, before any other revenue source kicks in. Verification fees scale linearly with users while infrastructure costs scale sublinearly. There is no scale at which the platform's economics get harder. They get easier.

The contextual advertising layer, the patronage subscription layer, and eventual mission-aligned grants are not necessary for survival. They fund mission expansion: subsidized verification for users in low-income regions, multilingual moderation staff, accessibility infrastructure, security audits, journalist and researcher tools, and the Community Distribution Fund.

If the platform never adds advertising at all, it still works. The verification fee is enough.

### Founder funding

The founder commits to self-funding development costs and any operational shortfalls during the development phase, using personal funds from independent business activities. This commitment is documented but not legally binding because the platform must be allowed to fail if external circumstances make it untenable. The founder will give the platform every reasonable chance to succeed.

The first $10,000 of platform surplus (after operating costs and the legally required reserve) goes into the Stiftung formation fund. No exceptions.

---

## Part VIII: Surface Area

What the platform actually does, feature by feature, at launch.

### 8.1 Profiles

GitHub-readme style, not MySpace.

- **`profile.md`** — every verified user gets a markdown README rendered at the top of their page. Sandboxed: CommonMark + curated subset (images, links, code blocks, tables, emoji). No raw HTML, no inline CSS, no script.
- **Curated embeds** — small allowlist (YouTube, Spotify, Bandcamp, SoundCloud, Vimeo) rendered server-side via oEmbed. No arbitrary iframes.
- **Pinned posts + activity feed** — below README. Chronological. User can pin up to 3.
- **Theme** — accent color + one of N preset fonts. No custom CSS.
- **Blog** — multi-post rich-text (Markdown with WYSIWYG layer). Each post has its own URL.
- **Photo gallery** — albums (user-named folders), images, tagging of other verified members (taggee must approve before tag appears).
- **Top friends** — optional, 1–N, displayed on profile.

Privacy controls per profile: profile visibility, who can DM, who can send friend requests, who can tag, search visibility.

### 8.2 Communities

Subreddit-style with constitutional grounding.

- Any verified member can create a community.
- Community has: slug, name, description, **Community Rules** (short plain-language list per Constitution §5.2), icon, banner, category, NSFW flag, visibility (public/restricted/private).
- Membership: join/leave; restricted communities require mod approval.
- Posts: text + markdown + image attachments. Optional link posts.
- Comments: nested threading, capped depth.
- Voting: upvote/downvote, surfaces via "Hot" sort (chronological is default; ranking is opt-in per Constitution §8.2).
- Moderation: mods can remove, lock, sticky, ban, mute, warn. Modmail for member↔mod conversations.
- Escalation: community mods can escalate severe content to platform (superuser queue).

### 8.3 Business Directory

- Verified members can register or claim a business.
- Business has: name, category, address, hours (with holiday hours), website, phone, logo, banner, gallery, description.
- Ratings: 1–10 from verified members only. Reviews are comments.
- Posts: businesses can post announcements (appear on the business page and in followers' feeds).
- Verification: auto-checks (domain ownership, public records) + manual queue for ambiguous cases.
- No paid tiers at launch. No premium listings (per Constitution §1.5).

### 8.4 News (RSS)

- Curated source list, managed by superusers initially. Verified members can suggest sources.
- List layout: source icon, time, title, view count.
- Click tracking per article (anonymous aggregate counts). No per-user tracking.
- Trending = most clicks in last 24h. No personalization.
- Comments on news articles are verified-only.

### 8.5 Direct Messages

- Verified ↔ verified only. Visitors and unverified cannot send or receive.
- 1:1 only at launch. Group DMs deferred.
- Features: read receipts, typing indicators, image attachments, emoji picker. No GIF panel at launch.
- Block, report, archive.
- Email notification to inactive recipients (10-min throttle).

### 8.6 Ethos (Reputation)

The community moderation reputation system.

- **Two scopes:** global Ethos (cross-community reputation) and per-community Ethos.
- Score moves based on community signals: flags upheld/dismissed, mod actions, time decay (per Constitution Article IV).
- Ethos weights how seriously the system treats flags, and gates eligibility for moderation roles and Board candidacy. Specific thresholds in the public Ethos Methodology Document.
- Algorithm parameters are tunable by superusers and the parameters themselves are public (transparency principle).
- New accounts carry minimal flagging weight until they demonstrate sustained participation (Constitution §4.5).

### 8.7 Founders Acknowledgment

A simple recognition for early supporters. Zero governance, voting, or revenue implications. "Thanks for being early." Nothing more.

The specific structure — whether the recognition is time-bound, count-bound, or blended; the tier definitions; the badge mechanics — is deliberately left open and decided closer to launch based on community size and tempo (see Phase 8 in Part X and Decision #8 in Part XII). Architecturally trivial: the schema captures `founder_tier` and `founder_assigned_at` on verified users; the rest is render logic.

### What's deferred (not deleted)

- **Marketplace / classifieds** — good idea, complex moderation surface, defer until the social core is proven.
- **Service Trade / skill-swap / credits** — same reasoning.
- **Short-form video ("Flips")** — long-term roadmap.
- **CYOA game and other youth engagement features** — long-term.
- **Premium business listings** — explicitly forbidden by Constitution §1.5; not a deferred decision.

These features stay in the long-term vision but the launch roadmap (Phases 0–10) does not include them.

---

## Part IX: Working Practices

### How the team operates

**Jake (Founding Chair / Operator):** Vision, judgment, real-world execution, governance decisions, founder funding, search for board candidates. Final call on every architectural decision. Reviews all CC commits before merge to main.

**Claude (Project — this conversation):** Research, reasoning, architecture, prompt drafting, document writing. Brainstorming partner. Reviews technical plans against the Foundation. Drafts CC prompts when Jake signals it is time.

**Claude Code (CC):** All code execution. Operates with full autonomy within prompt scope. Commits to git when done. Front-loaded permissions and decision rules to eliminate mid-task interruptions.

**Future contractors:** Brought in as needed for specific work (security audit, legal review, mobile QA). Not on retainer. Not equity-compensated (no equity exists).

### CC operating principles

- **Read SKILL.md files before writing code.** Mandatory.
- **Read FOUNDATION.md and CONSTITUTION.md when in doubt.** They are the source of truth.
- **Sandbox first, always.** Verify on `sandbox.flip-net.com` before merging to main.
- **All changes go through PR with CI checks passing.** Even Jake does not push directly to main.
- **Database migrations are ALTER TABLE only after the first production user.** No DROP COLUMN within 90 days of column creation.
- **When in doubt, pause and flag.** Risky or irreversible actions require Jake's explicit confirmation.
- **All commits include a brief rationale in the message.** Future-Jake (and future board members) need to understand why decisions were made.

### Decision documentation

Every significant architectural or governance decision is captured as an Architecture Decision Record (ADR) in `/docs/DECISIONS/NNNN-title.md`. Format: context, decision, consequences, alternatives considered. ADRs are append-only — superseded decisions are marked superseded but never deleted. The full decision history is part of what transfers to the Stiftung.

### Founder voice commitment

The platform's culture in its first year is set by the operator's voice, not by the documents. Every successful community platform had a founder who showed up in writing in the early community, doing the work of culture-setting before culture sets itself by accident. The Founding Chair commits to the following operating cadence:

- **Minimum one public update per week** for the first six months following the first verified-member signup. Format flexible (long post, short post, tweet-length note, journal entry). Length not the point; visible presence is the point.
- **Minimum one public update per month** thereafter, until Stiftung formation or until the Board of Directors releases this commitment.
- **First-100 verified members letter** published before the 100th verified member is reached, addressed to the first cohort, articulating what the operator intends to do and not do, and what the community can hold the operator to.

This commitment lives in the Foundation rather than the Constitution because it is a working practice, not a governance covenant. It is recorded here, in writing, so it can be pointed to later when operational fires would otherwise eat it. The first 90 days of operation are when the platform's culture forms; if the operator is heads-down in CC for that period, the culture forms in a vacuum and the documents become irrelevant to what FLIPNET actually becomes.

The commitment is binding on the Founding Chair specifically. Failure to meet the cadence is not a Constitutional violation, but it is grounds for the LLC-era external trustee's dissent power under Constitution §2.4.

---

## Part X: Roadmap

This is a sequence, not a schedule. No phase has a duration estimate attached. The platform takes as long as it takes. Phases complete when they complete.

### Artifact-based phase gates

Removing dates from the roadmap creates a risk: without external pressure, a phase can sit at 95% complete indefinitely while the founder works on the next interesting thing. To defend against drift without re-introducing arbitrary deadlines, each phase has an **artifact gate** — a concrete, demonstrable proof that the phase is actually done, not merely close to done.

A phase is not complete until its artifact gate is satisfied, and the next phase does not begin until the current phase is complete.

| Phase | Artifact gate |
|---|---|
| 0 — Foundations | A successful end-to-end deploy of a "hello world" route from local → sandbox → main with all CI checks green, AGPL header present, PR template citation enforced, audit log writing on every state change. NCMEC ESP registration filed. Dormant Persona account opened for identity-provider exit ramp. External counsel-of-record engaged; multi-sig key ceremony scheduled. |
| 1 — Verification | Jake verifies his own real-world identity end-to-end on the live system, pays the real $5, and watches the weekly OpenTimestamps anchor for that verification's audit-log entry land in the Bitcoin blockchain via the verifier CLI. Multi-sig anchoring is active (2-of-3 keys provisioned: founder, sealed-envelope successor, external counsel). |
| 2 — Profiles | PhotoDNA hash-matching pipeline operational; every uploaded image scanned before publication; automatic NCMEC SUSP report generation tested end-to-end against the NCMEC sandbox. At least three real verified humans have created functioning `profile.md`-style profiles, including a curated embed, a photo with tag-with-approval, and a blog post with multiple pages. |
| 3 — Communities | Three real communities exist with at least one real post and one real comment each. Moderation flow tested: a real post is flagged, queued, and approved or removed by a real moderator. |
| 4 — Ethos | A real coordinated brigading attempt is simulated against a test community, the system auto-detects it, the auto-enforcement triggers correctly, and a user-facing appeal works end-to-end. |
| 5 — DMs | Two verified users exchange messages, one user reports a message, an operator decrypts it for moderation, the affected user receives the ≤15-minute notification, and the entire flow is reflected in the audit log and OTS anchor. |
| 6 — Business Directory | A real business is registered by a verified member, verified via the auto-check path, posts an announcement, and receives a real review from a different verified member. |
| 7 — News | Three RSS sources are aggregating live, click tracking works, trending updates within 24 hours. |
| 8 — Founders recognition | The schema captures the recognition data; the rendering works on a real profile and a real post. |
| 9 — Governance infrastructure | Transparency dashboard live with real numbers; first quarterly financial report drafted in the format that will be published; Contributor Agreement v1 in place; Whistleblower channel (Hush Line or equivalent) live and tested. |
| 10 — Launch readiness | All Part XI Launch Criteria checked off. |

The artifact gates are the answer to "how do we know a phase is actually done?" They are quality gates, not time gates. They can be satisfied at any pace — but they must be satisfied.

### Phase 0 — Foundations
- Three repos created: `flipnet-v2` (public, AGPL-3.0), `flipnet-v2-secrets` (private), `flipnet-transparency` (public, append-only)
- Monorepo structure (pnpm workspaces + Turborepo) with apps/web, apps/mobile, apps/api, packages/* scaffolded
- Fastify + React (Vite) + Expo wired together; mobile build green even if shipping the web app first
- Drizzle, Neon (Postgres, US region matched to Railway US), Upstash Redis
- Better Auth (sessions in Postgres + Redis cache); CSRF, rate limiting, basic security middleware
- CI: typecheck, lint, test, build, gitleaks, AGPL header check, license audit, drizzle plan, OpenAPI diff
- PR template requires `Foundation: Part N` or `Constitution: Article N` citation; CI grep enforces
- Feature flag system
- Sentry + OpenTelemetry + Grafana Cloud wired (consent-gated initialization stub in place even though no consent UI exists yet)
- `packages/shared/src/constitutional-constants.ts` created, CODEOWNERS-locked to Founding Chair, with `featureUnlockedFor()` predicate available for use throughout the codebase
- `packages/governance/` scaffolded with verifier CLI; published as `@flipnet/governance` to npm; `flipnet-transparency` consumes it as pinned version
- Audit log schema + chain-hash + outbox + idempotency_keys + webhook_events tables
- DB-level audit log immutability live: `BEFORE UPDATE OR DELETE` trigger on `audit_log`, RLS policies denying UPDATE/DELETE, dedicated `audit_writer` Postgres role with INSERT-only permissions
- OpenTimestamps anchoring worker stubbed; `flipnet-transparency` repo wired to receive daily signed commits + weekly OTS anchor commits
- **NCMEC ESP registration filed** at report.cybertip.org/espregistration (free, 3–6 week approval window). Registration must be complete before Phase 2's photo upload goes live; filing it during Phase 0 absorbs the approval latency. This is a federal requirement under 18 USC §2258A.
- **Verification provider abstraction scaffolded:** `verification_provider` abstraction layer in code, `identity_provider` column on verification record. Dormant Persona account opened and kept in good standing as the pre-evaluated secondary for Principle 21.
- **External counsel-of-record engagement begun.** Counsel-shopping for a foundation-law attorney (Swiss-resident preferred but US-resident acceptable for the LLC era) who will serve as: the named trustee in the LLC operating agreement per Constitution §1.3 and §2.4, and the holder of the third key in the 2-of-3 multi-sig anchoring scheme per Principle 3. Engagement and key ceremony are hard gates on the Phase 0 → Phase 1 transition.
- Base design system, accent-color theming
- First "hello world" deployed end-to-end on web and API. Mobile app builds locally even if not deployed yet.

### Phase 1 — Verification
- Signup → Unverified account
- Stripe Checkout + Stripe Identity wired (test mode, then live mode)
- Stripe Identity data-flow contract enforced (token + identity_hash_primary + identity_hash_fallback + country + is_18_or_older only; no images, no PII beyond what's listed)
- Stripe Identity restricted to US-issued documents at the Stripe configuration level until EU infrastructure exists
- `verification_level` flip on webhook (idempotent, via outbox pattern); webhook state machine handles out-of-order payment and identity events via a `verification_pending` substate
- Age gate UX: modal interstitial collecting a birthdate before any account creation; under-13 visitors get a hard reject with zero analytics; 13–17 visitors get view-only access; 18+ proceed to signup
- CCPA "Do Not Sell or Share My Personal Information" link in the footer; functional from day one even though the platform doesn't sell data — California law requires the link to exist regardless
- EU/UK/CH consent banner displays *before* Sentry, OpenTelemetry, or any other observability SDK initializes (not just before tracking — before *initialization*); rejecting consent prevents those SDKs from loading at all for that session
- Annual renewal cycle with grace period (handled by `pg_cron`)
- One-account-per-person enforcement via the two-tier identity_hash match logic
- Verification status visible in account settings
- Refund flow on KYC failure
- Account export and deletion using the two-tier deletion model (personal data hard-deleted; audit/Ethos/mod references pseudonymized via destroyed-salt SHA-256)
- DMCA agent registered at copyright.gov for FLIPNET LLC

### Phase 2 — Profiles
- **CSAM scanning pipeline operational before the first user-uploaded image is made viewable.** Every upload passes through Sharp processing and a PhotoDNA hash-match (or Cloudflare's CSAM Scanning Tool as the secondary option pending PhotoDNA access approval) before the asset is published. A `csam_detected` boolean on uploads blocks publication when true and triggers an automated NCMEC SUSP report via the CyberTipline API. The NCMEC ESP registration filed in Phase 0 must be approved before Phase 2 ships.
- A small T&S superuser queue surfaces any uploads where the scanner returned an inconclusive result, with a documented review SLA.
- `profile.md` editor + sandboxed renderer (CommonMark subset, no raw HTML, no inline CSS, no script)
- Curated embeds via server-side oEmbed (YouTube, Spotify, Bandcamp, SoundCloud, Vimeo)
- Photo gallery with albums + tag-with-approval
- Blog (Markdown, per-post URLs)
- Pinned posts + chronological activity feed
- Privacy controls (profile visibility, DM permissions, friend request permissions, tag permissions, search visibility)

### Phase 3 — Communities
- Community CRUD, membership, posts, nested comments, voting
- Hot / new / top sorts (chronological default; ranked sorts opt-in per Constitution §8.2)
- Moderation tools (remove, lock, sticky, ban, mute, warn)
- Modmail
- Escalation queue to platform superuser

### Phase 4 — Ethos
- Global + per-community score tables (event-sourced from `ethos_events`)
- Replayable from event log
- Flagging, mod queue with Ethos-weighted flags
- Public Ethos Methodology Document; numerical thresholds in `flipnet-v2-secrets`
- Coordinated flagging detection with auto-enforcement enabled
- User-facing appeal path with proper UI
- Superuser tuning UI

### Phase 5 — DMs
- 1:1 threads via Ably WebSockets, transport-swappable data model
- Server-side envelope encryption at rest (per-conversation key wrapped by KMS master key); E2EE via libsignal on the post-launch roadmap
- Image attachments
- Block, report, archive
- Email-on-inactive notification

### Phase 6 — Business Directory
- Business CRUD, claim flow, verification queue
- Ratings (1–10), reviews, posts
- Multi-owner management
- Search + filters

### Phase 7 — News
- RSS polling worker (BullMQ cron)
- Curated source list, source suggestion form
- List view, click tracking, trending

### Phase 8 — Founders recognition
- A simple recognition for early supporters. Specific structure (time window, count cap, blended model, tier definitions) left open and decided closer to launch based on community size and tempo.
- Zero governance, voting, or revenue implications. "Thanks for being early." Architecturally trivial; the schema captures `founder_tier` and `founder_assigned_at` on verified users and the rest is render logic.

### Phase 9 — Governance infrastructure (parallel throughout)
- Audit logging operational from Phase 0; OpenTimestamps anchoring active from Phase 1; daily signed commits to `flipnet-transparency` from Phase 1
- DB-level audit log immutability (triggers + RLS + `audit_writer` role) active from Phase 0
- Verifier CLI published as `@flipnet/governance` from `flipnet-v2/packages/governance/` from Phase 0; `flipnet-transparency` consumes pinned version
- `constitutional-constants.ts` codified in `packages/shared/` with CODEOWNERS lock and `featureUnlockedFor()` predicate from Phase 0
- `governance_decisions` table operational by Phase 1: closed `decision_type` enum, immutable `rationale_md`, FK to `audit_log(seq)`, per-write OTS anchor on each governance decision
- `governance/` directory at repo root tracking IP ledger, secrets inventory, vendor list, domain list, contributor list — populated as the project accumulates them; the file structure makes the eventual Stiftung handoff mechanical rather than archaeological
- Transparency dashboard live by end of Phase 1
- Quarterly financial reporting infrastructure ready by end of Phase 2
- Board search infrastructure (verified-user nominations of mission-aligned candidates) live by end of Phase 4
- Whistleblower channel established per Constitution §13.2 — Hush Line (or equivalent), hosted off FLIPNET infrastructure to prevent self-conflict-of-interest, in place before Phase 10
- Contributor Agreement v1 in place before second human contributor lands (DCO sign-off + AGPL grant + successor-entity enforcement clause authorizing the Stiftung to enforce on contributors' behalf)
- Multi-signature anchoring (2-of-3 between founder, sealed-envelope successor, and external counsel) **active before the Phase 0 → Phase 1 gate is satisfied** — see Architecture Principle 3. The Phase 0 single-key window is publicly disclosed in the transparency dashboard. The external counsel of record is the same trustee named in Constitution §1.3 and §2.4 for compelled-transition and dissent powers; one human, three roles.

### Phase 10 — Launch readiness
- Council audit of the live platform
- External security audit
- Legal review by attorney experienced in non-profit and platform liability
- Compliance review for GDPR, COPPA, CCPA
- Documentation review (terms, privacy, guidelines, transparency reports)
- Backup restore exercise completed
- Load test: 10k concurrent readers, 1k concurrent verified writers, p99 < 500ms on feed
- OpenTimestamps anchoring verified end-to-end via the verifier CLI
- Soft launch to existing waitlist
- Public launch when soft launch demonstrates stability

The commitment is to ship right. No date is attached anywhere in this document on purpose.

---

## Part XI: Launch Criteria

The platform cannot ship until all of these are true:

- [ ] All Phase 0–10 work complete (each Phase's artifact gate satisfied)
- [ ] Quarterly backup restore proven (one full restore exercise)
- [ ] PITR reconciliation runbook tested (a real restore-past-deletion scenario rehearsed in sandbox)
- [ ] Load test passed: 10k concurrent readers, 1k concurrent verified writers, p99 < 500ms on feed
- [ ] DMCA agent registered for the entity owning the platform
- [ ] TOS + Privacy Policy reviewed by external counsel
- [ ] Arbitration + class-action waiver with 30-day opt-out (with working backend)
- [ ] SPF / DKIM / DMARC configured and passing for flip-net.com
- [ ] Stripe Identity in live mode, refund flow tested end-to-end, replay tests pass via `stripe trigger`
- [ ] Stripe Identity data-flow contract verified — no PII beyond the documented columns lives anywhere in the database
- [ ] Stripe Identity restricted to US-issued documents (jurisdictional gate enforced at Stripe layer, not just app layer)
- [ ] Age gate operational; under-13 hard reject, 13–17 view-only, 18+ verification path
- [ ] CCPA "Do Not Sell" footer link present and functional
- [ ] EU/UK/CH consent banner prevents observability SDK initialization on rejection
- [ ] Account deletion + data export tested end-to-end; two-tier deletion model verified
- [ ] Audit log writes verified for all sensitive actions
- [ ] DB-level audit log immutability verified (UPDATE/DELETE attempts rejected by trigger and RLS)
- [ ] OpenTimestamps anchoring verified end-to-end; verifier CLI runs and confirms chain integrity
- [ ] Daily signed commits to `flipnet-transparency` operational
- [ ] `constitutional-constants.ts` CODEOWNERS lock active; `featureUnlockedFor()` predicate gating tested
- [ ] `governance_decisions` table operational; at least one real governance decision recorded with OTS anchor
- [ ] Whistleblower channel (Hush Line or equivalent) live and tested
- [ ] Sentry + OpenTelemetry + Grafana receiving production data (only after EU consent gate)
- [ ] Cutover plan rehearsed in sandbox
- [ ] Maintenance-window comms drafted and scheduled
- [ ] Council post-build audit passed
- [ ] External security audit passed
- [ ] Community Guidelines published and complete
- [ ] Ethos Methodology Document published and complete
- [ ] Contributor Agreement v1 in place (DCO + AGPL grant + successor-entity enforcement clause)
- [ ] `flipnet-v2` public repo open and synchronized with internal development from Phase 0 onward
- [ ] DM bulk-decryption multi-party authorization tested; user notification ≤15 minutes verified end-to-end
- [ ] NCMEC ESP registration approved; PhotoDNA (or Cloudflare CSAM Scanning Tool) hash-matching live in production; CyberTipline SUSP report generation tested end-to-end against the NCMEC sandbox
- [ ] Multi-signature 2-of-3 anchoring active and verified: founder key, sealed-envelope successor key, external counsel key, all in distinct physical custody; key ceremony documented; weekly anchor co-signing rehearsed
- [ ] Identity-provider exit ramp verified: `identity_provider` column populated on every record; Persona dormant account in good standing; provider-swap runbook documented and rehearsed in sandbox
- [ ] Stripe Billing exit ramp verified: outbox-based migration path documented; alternate billing processor pre-evaluated
- [ ] External trustee named in the LLC operating agreement, in writing, with executed agreement covering: Constitution §1.3 compelled-transition power, Constitution §2.4 LLC-era dissent power, Architecture Principle 3 multi-sig third key role

---

## Part XII: Decisions Still Open

Tracked here as they get answered. Do not ship without resolving.

| # | Decision | Default if unresolved |
|---|---|---|
| 1 | Group DMs at launch or deferred | Deferred |
| 2 | Cross-account spam detection beyond Ethos | Manual via superuser queue |
| 3 | Ad system: launch with it or add later | Add later (post-launch) |
| 4 | Stiftung jurisdiction within Switzerland (canton) | Decide with Swiss counsel when Phase 3 of governance arrives |
| 5 | Whether unverified accounts can follow verified users for personalized reading | Yes, default on |
| 6 | Re-verification cadence beyond annual (e.g., re-prove identity every 5 years) | Annual only at launch; revisit |
| 7 | Scholarship sponsorship UI flow | Build alongside verification flow in Phase 1 |
| 8 | Founders recognition structure (time-bound, count-bound, blended) | Decide closer to launch; architecturally flexible |
| 9 | Whether to allow Markdown profiles to embed audio playback inline | TBD; default off until decided |
| 10 | International rollout beyond US — what additional jurisdictions, when, and what the per-jurisdiction compliance burden looks like | US only at launch; revisit when there's demand and capacity |
| 11 | External trustee identity (the same human named in Constitution §1.3, §2.4, and the multi-sig third key) | Selected during Phase 0 counsel-shopping; foundation-law attorney preferred, Swiss-resident strongly preferred for eventual Stiftung continuity but US-resident acceptable during LLC era |
| 12 | Founder compensation during LLC era | Defer until first $5,000 of monthly verification revenue is reached. If unresolved at that point: zero compensation continues; Founding Chair funds operations from external income. If compensation is later drawn, it is bound by a structure of quarterly disclosure, capped at median for comparable non-profit role, recorded as a `governance_decisions` row. |

---

## Part XIII: What This Document Does Not Decide

Deliberately left for later:

- **The marketplace and service trade features** — deferred (Part VIII)
- **The business directory premium tier** — explicitly forbidden by Constitution
- **The "Flips" short-form video feature** — long-term roadmap
- **The CYOA game and youth engagement features** — long-term
- **Specific moderation policies beyond the Ethos system architecture** — framework decided here; specific rules drafted with input from external advisors closer to Phase 3
- **The board search methodology** — general intent documented; specific process designed in Phase 9
- **The Stiftung formation timeline and Swiss legal partner** — Phase 3 (governance) decision

These are deliberate scope discipline, not omissions.

---

## Part XIV: Glossary

- **Visitor** — anyone reading public content without an account.
- **Unverified account** — has an email/password but has not completed identity verification. Equivalent to Visitor at launch.
- **Verified Member** — paid $5/year and passed Stripe Identity. Can do everything.
- **Lapsed Verified Member** — was Verified, verification expired. Read-only own account; can re-verify any time.
- **Ethos** — community moderation reputation. Global + per-community.
- **Outbox** — DB table holding pending side effects, drained by workers.
- **Stiftung** — Swiss foundation; long-term ownership target.
- **Founder** — an early supporter recognized per the launch-time recognition policy (see §8.7 and Phase 8).
- **Superuser** — platform operator with elevated permissions (Jake + designated others), distinct from community moderators and admins.
- **The Promise** — the public-facing summary of the constitutional principles, displayed at `/principles`.

---

## Closing

The platform takes as long as it takes. It costs what it costs. It is built right because it has to be built right. The internet has enough mediocre platforms. It needs at least one that is built like infrastructure — boring, durable, transferable, and worthy of the trust people place in it.

Freedom. Liberty. Independence. Prosperity.

This belongs to everyone.

—Jake Hoover, Founding Chair

---

## Document control

This document is the technical and operational source of truth for FLIPNET. The paired document `CONSTITUTION.md` is the governance covenant. Conflicts between this document and any other document, comment, code, or conversation (except the Constitution on governance and mission matters) are resolved in favor of this document. Changes go through formal amendment via `governance_decisions`.
