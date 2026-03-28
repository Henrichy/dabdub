# Referral Analytics Implementation Plan (#491)

## Steps to Complete:

### 1. Create new files
- [x] backend/src/referrals/referral-analytics.service.ts (all methods: getFunnelStats, getTopReferrers, getCohortComparison, getRewardSpend, getUserReferralStats)
- [x] backend/src/referrals/dto/referral-analytics.dto.ts (DTOs for responses)
- [x] backend/src/referrals/referral-analytics.processor.ts (BullMQ daily job 'compute-referral-analytics')
- [ ] backend/src/referrals/referral-analytics.service.spec.ts (unit tests)

### 2. Update existing files
- [x] backend/src/referrals/referrals.module.ts (import CacheModule, new service/processor)
- [x] backend/src/referrals/referrals.controller.ts (add public GET /track?ref=code for click tracking)
- [ ] backend/src/referrals/referral.service.spec.ts (add tests for interactions)
- [x] backend/src/admin/admin.controller.ts (add GET /admin/referrals/analytics, /admin/referrals/cohort, /admin/referrals/users/:userId)
- [x] backend/src/admin/admin.module.ts (inject ReferralModule or service)

### 3. Branch, commit, tests
- [ ] git checkout -b blackboxai/fix-491-referral-analytics
- [ ] npm test (ensure unit tests pass)
- [ ] cargo test (if contracts affected, unlikely)
- [ ] git add . &amp;&amp; git commit -m "fix(#491): implement referral analytics funnel, top referrers, cohorts, spend tracking + daily cache job"

### 4. Create PR
- [ ] gh pr create --title "fix(#491): Referral analytics — tracking funnel performance" --body "Implements all AC: FunnelStats, click tracking, top referrers, cohort comparison, reward spend, user stats, admin endpoints, daily BullMQ cache job. Tests added. Ready for review." --base main

**Progress: 0/15 complete**

