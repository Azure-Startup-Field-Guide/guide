# 1. Apply and activate without creating an identity trap

> **Verified in the August 16, 2026 repository audit against current official
> Microsoft documentation.**

## The recommendation

Use the personal Microsoft account requested by the Microsoft for Startups
application flow, but treat it as the activation identity, not as the final
company operating model.

## Before you begin

Have these items ready:

- a personal consumer email associated with a Microsoft account;
- the company's legal name and address;
- a phone number and payment card for verification;
- the correct billing country or region; and
- an investor referral code, if your investor or accelerator provided one.

The current application documentation states that work, school, and company
domain accounts are not accepted for the sign-up steps. It also warns that the
billing country or region cannot be changed later in the existing profile.

> **Stop before redemption:** confirm both the billing country or region and the
> personal Microsoft account. Current program FAQs state that the billing
> country or region cannot be directly changed on an existing billing profile
> and startup credits cannot be transferred to a different Microsoft account.

## Apply

1. Start at [Microsoft for Startups](https://www.microsoft.com/en-us/startups).
2. Follow the
   [official application guide](https://learn.microsoft.com/en-us/startups/microsoft-for-startups/application).
3. Sign in with the intended personal Microsoft account.
4. Use the investor referral code if you have one; otherwise follow the path
   without a code.
5. Complete Azure account creation and record which Microsoft account you used.

Do not publish the activating account in a repository, ticket, or team chat.
Store ownership information in your company's password manager or access
register.

## Confirm the result

In the Azure portal:

1. Open **Subscriptions**.
2. Confirm that the sponsored subscription appears.
3. Confirm that the expected Microsoft account is the owner.
4. Open **Cost Management + Billing** and verify the billing context.

The official FAQ says credit balances can take several hours to appear after
successful activation. If they do not appear, do not create parallel accounts
or repeatedly redeem the offer. Use the support path in
[Get help](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/first-48-hours/05-get-help).

## Common failures

| Symptom | What to check |
| --- | --- |
| Company email is rejected | The application requires a personal consumer Microsoft account |
| Credits are not visible immediately | Allow for the documented processing delay, then verify the billing profile |
| "Already redeemed" | The Microsoft account may have redeemed another Azure credit offer |
| Existing pay-as-you-go subscription has no credits | Verify whether it uses the same billing profile as the sponsored subscription |
| Wrong country or region | Stop and contact support before building; do not assume it can be edited in place |

## Next

Do not deploy yet. Continue to
[2. Establish company identity](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/first-48-hours/02-company-identity).

## Official sources

- [How to Apply to Microsoft for Startups](https://learn.microsoft.com/en-us/startups/microsoft-for-startups/application)
- [Microsoft for Startups FAQ](https://learn.microsoft.com/en-us/startups/microsoft-for-startups/mfs-faqs)
- [Properly Setting Up Your Azure Account](https://learn.microsoft.com/en-us/startups/build/azure-getting-started/set-up-account)
