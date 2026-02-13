# Coach App - High-Level Overview

## What is Coach?

Coach is a personal development app that helps users with:
- AI-powered coaching conversations
- Goal tracking
- Habit building
- Daily check-ins
- Journaling
- Custom voice assistants

## How Does It Make Money?

The app uses a **freemium** model:
- **Free version**: Basic features, limited usage
- **Paid subscriptions**: More features, unlimited usage

---

## The Three Subscription Tiers

### 1. Free
- Limited to 2 voices
- 5 journal entries max
- 100 words per message
- Cost: $0

### 2. Member ($6.49/month)
- 25 expert voices
- 50 journal entries
- 500 words per message
- Voice can read your journal
- Weekly summaries
- Priority support

### 3. Ultra ($12.49/month)
- Everything in Member
- Unlimited journal entries
- 2000 words per message
- Create your own custom voices
- Share voices with other Ultra members
- Voice coaching (coming soon)
- Human coach access (coming soon)

---

## How It Works

### When a User Upgrades

1. User taps "Upgrade" in the app
2. App shows available subscription options
3. User picks a plan and pays
4. Apple or Google processes the payment
5. App unlocks the new features instantly

### How the App Knows What to Show

The app checks the user's subscription status before showing features:

```
User tries to create custom voice
        │
        ▼
Is user Ultra member?
   │
   ├── YES → Allow feature
   │
   └── NO → Show "Upgrade to Ultra" message
```

---

## Who's Involved

| Party | Role |
|-------|------|
| **You (Developer)** | Build the app |
| **RevenueCat** | Handle subscriptions, communicate with Apple/Google |
| **Apple App Store** | Process iOS payments |
| **Google Play Store** | Process Android payments |
| **Supabase** | Store user data |

---

## Key Parts of the App

### 1. RevenueCat Service
- Connects to Apple and Google
- Tells the app what the user paid for

### 2. Subscription Service
- Syncs payment info to your database
- Tracks feature limits

### 3. UI Components
- Show upgrade prompts
- Lock/unlock features based on tier

---

## Simple Flow Diagram

```
User Action
     │
     ▼
┌─────────────────┐
│  App checks    │ ← Is user paid?
│  subscription  │
└────────┬────────┘
         │
    ┌────┴────┐
    │         │
  YES        NO
    │         │
    ▼         ▼
Allow     Show upgrade
feature   prompt
```

---

## What's Already Built

- ✅ RevenueCat connection
- ✅ Subscription tier system
- ✅ Upgrade buttons and modals
- ✅ Feature locking for free users
- ✅ Registration with subscription selection

## What Still Needs Work

- Purchase flow completion
- Subscription management screen (cancel, change plan)
- Billing history
- Proper downgrade handling

---

## Summary

Coach makes money through subscriptions. RevenueCat handles all the complicated payment stuff. The app simply asks "is this user paid?" before letting them use premium features.
