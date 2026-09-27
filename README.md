# VidyaOS — Architecture & API Flow

Complete architecture and API design for **VidyaOS**, a School Management System for **Guru Nanak Public School, Hambran, Ludhiana, Punjab**.

## Live document

Once GitHub Pages is enabled, the interactive document is viewable at:

**https://dilnazgrewal.github.io/vidyaos-architecture/**

## What's inside

The main document ([`index.html`](index.html)) contains 5 diagrams, each annotated with the exact API calls:

1. **System Overview** — the 6-layer architecture with both data paths labeled
2. **Frontend Layer** — which API each feature module calls
3. **Backend Layer** — Path A (direct SDK) vs Path B (API routes) in detail, plus RLS
4. **Database Layer** — 30 tables in 9 modules and the calls that hit them
5. **Deployment Layer** — where each API physically runs

## PDFs

- [`VidyaOS-Architecture-API-Flow.pdf`](VidyaOS-Architecture-API-Flow.pdf) — the diagrams above, print-ready
- [`VidyaOS-Architecture-API-Guide.pdf`](VidyaOS-Architecture-API-Guide.pdf) — journey-based guide with full code for each operation

## Tech stack

| Layer | Choice |
|-------|--------|
| Framework | Next.js 14 (App Router) + TypeScript |
| UI | shadcn/ui + Tailwind CSS |
| State | TanStack Query v5 |
| Forms | React Hook Form + Zod |
| Backend | Supabase (PostgreSQL + Auth + Storage + Realtime + Edge Functions) |
| Hosting | Vercel |

**Running cost: ~₹42/month** (domain only; everything else on free tiers).

## The two data paths

- **Path A — Direct SDK** (~80%): browser talks straight to Supabase; RLS filters every row by the user's JWT.
- **Path B — API Routes** (~20%): browser calls a Vercel serverless function that uses the service-role key for complex/sensitive work (account creation, bulk import, PDF generation).
