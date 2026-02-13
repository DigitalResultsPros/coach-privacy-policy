# RevenueCat Integration Guide

## What is RevenueCat?

RevenueCat is a tool that makes it easy to handle subscriptions in mobile apps. Instead of dealing with Apple and Google separately, you use RevenueCat as a middleman. It talks to both app stores and gives you one place to manage everything.

---

## Why Use RevenueCat?

### The Problem
If you want to charge for your app through the App Store or Google Play, you need to:
- Learn Apple's complex rules and Google's different rules
- Write code to talk to both stores separately
- Handle subscriptions renewing, expiring, failing
- Deal with refunds and cancellations

### The Solution
RevenueCat does all that for you. You write code once, and RevenueCat handles the rest.

---

## How Subscriptions Work in Coach

### The Basic Flow

1. User taps "Upgrade" in the app
2. App asks RevenueCat "what plans are available?"
3. RevenueCat returns the options (Member, Ultra)
4. User picks one and pays
5. RevenueCat tells Apple/Google to process payment
6. Payment goes through → RevenueCat gives user access
7. App unlocks premium features

### What Happens After

- Subscription renews automatically each month
- RevenueCat handles cancellations
- If payment fails, RevenueCat lets the app know

---

## The Three Tiers

| Tier | Price | What You Get |
|------|-------|--------------|
| Free | $0 | Basic features, limited usage |
| Member | $6.49/mo | More voices, journal access, summaries |
| Ultra | $12.49/mo | Everything plus custom voices, sharing |

---

## What We Built

### What's Done
- Connected the app to RevenueCat
- Set up the three subscription tiers
- Created upgrade prompts when free users try premium features
- Added subscription selection to sign-up
- Made the app lock features based on tier

### What Needs Work
- Testing the full purchase flow
- Adding a screen where users can cancel or change plans
- Showing billing history
- Handling what happens when someone downgrades

---

## How the App Knows You're Paid

When you try to use a feature (like creating a custom voice), the app:

1. Asks RevenueCat "what tier is this user?"
2. RevenueCat checks with Apple/Google
3. Returns "unpaid", "member", or "ultra"
4. App decides whether to let you in or show an upgrade message

This happens fast - users don't notice it.

---

## Making Money

### Revenue Split
- Apple takes 15% of subscriptions (after first year, it's 30%)
- Google takes 15% (also 30% first year)
- You keep the rest

### Example
If 100 users pay $6.49/month for Member:
- $649/month total
- Apple/Google take ~$97 (15%)
- You keep ~$552/month

---

## Testing

Before launching, we test by:
1. Using RevenueCat's "sandbox" mode (fake purchases)
2. Creating test accounts
3. Trying all upgrade and downgrade scenarios

---

## What's Next

1. Finish testing the purchase flow
2. Build a settings page for subscriptions
3. Add billing history for users
4. Set up automatic receipts/emails
5. Handle failed payments gracefully

---

## Summary

RevenueCat is the bridge between your app and the app stores. It handles all the complicated payment stuff so you can focus on building features. The Coach app uses it to manage Member and Ultra subscriptions, locking and unlocking features based on what users pay.
