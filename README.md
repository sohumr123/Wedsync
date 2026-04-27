# Wedding Day — Vendor Coordination App

A premium day-of coordination app for wedding vendors and couples.

## What it does

**For Vendors** (photographers, videographers, DJs, coordinators, planners, etc.):
- View the full day-of timeline with real-time updates
- See who else is on the team and their contact info
- Propose schedule adjustments when things run late
- View the couple's "face sheet" — photos of key guests to recognize on the day

**For Couples** (bride, groom, or partner):
- View the wedding timeline
- Upload photos of important people: family, bridal party, officiant, speech givers, VIP guests
- See all vendors on the team

**For Admins** (lead coordinator):
- Create and manage the wedding timeline
- Approve or reject vendor-proposed schedule adjustments
- Share an invite code with all vendors and the couple

## Features

- **Timeline** — Day-of schedule with LIVE NOW indicator, up-next preview, full event list
- **Team** — Vendor directory grouped by specialty with contact info
- **People** — Face sheet with photos and descriptions for key guests
- **Admin** — Schedule adjustment approvals, event creation, team management
- **Auth** — Email OTP sign-in (no passwords)
- **Real-time** — Timeline auto-refreshes every 30 seconds

## Tech stack

- **Mobile**: Expo SDK 54, React Native, NativeWind, React Query, Better Auth client
- **Backend**: Bun, Hono, Prisma (SQLite), Better Auth

## Roles

| Role | Can do |
|------|--------|
| Admin | Create/edit events, approve changes, manage team |
| Vendor | View timeline, propose adjustments |
| Couple | View timeline, manage important people |

## Getting started

1. Sign in with your email (you'll receive a 6-digit code)
2. Set up your profile — choose Vendor or Couple, and your specialty
3. Create a new wedding (you become the admin) or join with an 8-character invite code
4. Share the invite code with your team
