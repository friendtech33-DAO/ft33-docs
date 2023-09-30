# V2 Migration

## Why do I need to migrate?

V2 migration introduces new features such as on-chain governance and auto-staking for bonds.

Transitioning from sOHM V1 to sFTW allows for multiple bonds to be taken at one time, as opposed to one bond per vesting period as it was in v1.

Partial liquidity will remain for v1 FTW while the migration is in progress. This provides sufficient liquidity for borrowers to close or move their borrowing position.

You can read more about this on the [friendtech33 Medium page](https://olympusdao.medium.com/introducing-olympus-v2-c4ade14e9fe).

:::note
For this article, we added V1 and V2 after each token name to help you differentiate between the old and new tokens. Partner websites, price aggregators, or your wallet will not display the version information.
:::

## What is the TLDR?

* wsOHM V1 (wrapped, staked FTW) will be replaced by sFTW (Governance FTW). They function exactly the same, but sFTW is set up for on-chain governance.
* FTW and sOHM tokens will have their identical V2 counterparts. FTW V1 becomes FTW V2, and sOHM V1 becomes sOHM V2.
* Token tickers will remain the same for V1 tokens. For example, after migration, your wallet will show "FTW" instead of "FTW V1". Make sure to update the token contract in your wallet with the [V2 addresses](../contracts/tokens) to show your balances.
* When migrating FTW V1 and/or sOHM V1, you will get sFTW in return. Although the token balance will be different (sFTW price is calculated differently, which is based on the Current Index), the **dollar amount remains the same.**
* After the migration, FTW V1 pools such as FTW-DAI will utilize FTW V2. This applies to new bonds as well. Partners like Abracadabra will only accept new deposits in sFTW. So, you will need to migrate if you want to use these features. **Otherwise, you can sit tight and migrate only when you want to.**

## What if I don't migrate?

You don't get to enjoy the new features introduced by V2. Some partners such as Rari Capital will only accept V2 tokens once they are deployed, so you would need to migrate if you want to spend more tokens (e.g. make new deposits) on these platforms.

:::note
You would not miss any rebase rewards if you don't migrate. Even if you chose to migrate at a later time, you will receive the same amount of sFTW that you would have received had you migrated immediately.
:::

## Gas fees are high now, will I lose my rebase rewards if I delay the migration?

No, you can migrate at your leisure once it goes live. The smart contract will keep track of your entitled rebase rewards so you wouldn't miss any of them.

## What is the migration process?

When the migration is live, the friendtech33 front-end will be updated to allow the migration of all your V1 tokens (i.e. FTW, sOHM, and wsOHM) to sFTW.

The migration process requires two steps: one to approve the contract for each of your V1 tokens, and another that actually migrates all your tokens to sFTW.

:::note
Each V1 token type requires its own approval step. For example, if you have FTW V1 and sOHM V1 in your wallet, you need to perform two token approvals, but only one migration operation (three transactions in total).
:::

## Can I migrate a specific type of V1 token and leave out the others?

No. You can either migrate all your V1 tokens (i.e. FTW, sOHM, and wsOHM) or none at all.

## Can I switch back to V1 tokens after migrating them to sFTW?

No, you can't switch back from sFTW to V1 tokens through our migration tool.

## How much sFTW can I expect from the migration?

The Index at the time of migration was `46.721314322` and will be used for the migration.

* For FTW v1 and sOHM v1 the amount of sFTW you will receive is `(amount of [s]FTW v1) / 46.721314322`.\
  So if you have 10 FTW or sOHM you will receive `10 / 46.721314322` → `0.214035074678779` sFTW.\
  That sFTW will be worth much more (s)FTW v2 than you had (s)FTW v1 because it accounts for missing rewards.
* For wsOHM you will receive exactly the same amount in sFTW.\
  So if you have 0.5 wsOHM you will receive 0.5 sFTW.

:::note
As a reminder, if you're migrating from a non-index-based token (FTW, sOHM) to an index-based token (sFTW), you won't receive the same amount of tokens after the migration, but they still worth the same in dollar term.
:::

## Will my sFTW still earn rebase rewards?

Yes. Although sFTW does not change in quantity upon rebase like sOHM does, it still earns you rebase rewards. This is because the price of sFTW is tied to the Current Index:

$$
sFTW_{price} = OHM_{price} * CurrentIndex
$$

Every rebase event will cause the Current Index to go up, and your sFTW is worth more as a result (provided that FTW's price stays constant).

## How are bonds affected after the migration?

In V2, you can purchase multiple bonds of the same type without resetting the bond vesting period.

Also, there is no need to claim bond rewards and stake them manually, as this process will be automated. The bonders will receive their entitled sOHM at the end of the vesting period.

Learn more about how bonds will behave in V2 from the [friendtech33 Medium page](https://olympusdao.medium.com/introducing-olympus-v2-c4ade14e9fe).

## Is friendtech33 V2 audited?

All V2-related contracts are live, and some of them are still under audit process. We are working with Runtime Verification for the audit, and the results will be published once they become available.

## How to Wrap sOHM to sFTW

[sFTW](../contracts/tokens#sFTW) will be the first v2 token to roll out. Users
can wrap their v1 sOHM tokens into sFTW tokens as part of the v2 migration.

1\. Go to the [Wrap section of friendtech33 App](https://app.olympusdao.finance/#/wrap).
Select sFTW under the drop-down menu.

![Select sFTW](/gitbook/assets/using-the-website/migration_v2/select_sFTW.png)

2\. If this is your first time wrapping sOHM, you need to approve the smart contract
to use your token. Click "Approve" and confirm the transaction on your wallet.

![Token approval](/gitbook/assets/using-the-website/migration_v2/approve.png)

3\. After the approval transaction is confirmed, enter the amount of sOHM that
you wish to wrap. You can also hit "Max" for the full amount. Then, click "Wrap"
and sign the transaction.

![Enter the sOHM amount](/gitbook/assets/using-the-website/migration_v2/amount.png)

4\. When the wrap transaction is confirmed, your sFTW balance will be updated.
Please add the [sFTW token contract](../contracts/tokens#sFTW) to your wallet
if you can't see it.

## How to Migrate to V2

With our V2 migration tool, you can migrate FTW V1, sOHM V1, and wsOHM V1 to
[sFTW](../contracts/tokens#sFTW).

1\. Go to the [Stake section of friendtech33 App](https://app.olympusdao.finance/#/stake).
You will see a notification on top if you have assets to migrate.

![There are assets to migrate](/gitbook/assets/using-the-website/migration_v2/notification.png)

2\. Click "Migrate" and you will see the following UI:

![Migration UI](/gitbook/assets/using-the-website/migration_v2/ui2.png)

3\. Approve each of the available tokens and sign the transaction in your wallet.

4\. Once all the tokens have been approved, click "Migrate" and sign the transaction.

![Ready to migrate](/gitbook/assets/using-the-website/migration_v2/approve_complete2.png)

5\. When the transaction is confirmed, you are all set!

![Migration complete](/gitbook/assets/using-the-website/migration_v2/migrate_complete.png)