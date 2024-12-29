# COIN100 (C100) Documentation

## Table of Contents
1. [Introduction](#introduction)  
2. [Problem Statement](#problem-statement)  
3. [Solution: COIN100 (C100) Token](#solution-coin100-c100-token)  
4. [Key Principles and Features](#key-principles-and-features)  
   - 4.1. [Fairness and Equal Treatment of Holders](#fairness-and-equal-treatment-of-holders)
   - 4.2. [Global Rebase Mechanism](#global-rebase-mechanism)
   - 4.3. [Fixed Pricing During Presale](#fixed-pricing-during-presale)
   - 4.4. [Fee-Based Treasury and Liquidity Growth](#fee-based-treasury-and-liquidity-growth)
   - 4.5. [Multiple Liquidity Pool Support](#multiple-liquidity-pool-support)
   - 4.6. [Simplified Public Sale Mechanics](#simplified-public-sale-mechanics)
5. [Tokenomics](#tokenomics)  
   - 5.1. [Initial Parameters](#initial-parameters)
   - 5.2. [Distribution (Treasury Allocation & ICO)](#distribution-treasury-allocation--ico)
   - 5.3. [Rebase Formula](#rebase-formula)
   - 5.4. [Market Dynamics and Price Stability](#market-dynamics-and-price-stability)
   - 5.5. [Liquidity Provider Rewards](#liquidity-provider-rewards)
   - 5.6. [Fee-Based Treasury](#fee-based-treasury)
6. [Technical Architecture](#technical-architecture)  
   - 6.1. [Polygon Network](#polygon-network)
   - 6.2. [C100 Token Contract](#c100-token-contract)
   - 6.3. [Public Sale Contract](#public-sale-contract)
   - 6.4. [Scaling and GonsPerFragment](#scaling-and-gonsperfragment)
   - 6.5. [Rebase Mechanism](#rebase-mechanism)
   - 6.6. [Rebase Ratio Limits (New)](#rebase-ratio-limits-new)
   - 6.7. [Enhanced Public Sale Features (New)](#enhanced-public-sale-features-new)
7. [Governance](#governance)  
   - 7.1. [Transition from Owner to Governor](#transition-from-owner-to-governor)
   - 7.2. [Future Governor Contract](#future-governor-contract)
   - 7.3. [Community Involvement](#community-involvement)
8. [Security](#security)  
   - 8.1. [Ownership Controls](#ownership-controls)
   - 8.2. [Pause/Unpause Mechanisms](#pauseunpause-mechanisms)
   - 8.3. [Reentrancy Guards](#reentrancy-guards)
   - 8.4. [Audits and Best Practices](#audits-and-best-practices)
   - 8.5. [Token Rescue and Burning](#token-rescue-and-burning)
9. [Roadmap](#roadmap)  
10. [ICO Plan (Simplicity-Focused)](#ico-plan-simplicity-focused)  
    - 10.1. [ICO Parameters](#ico-parameters)
    - 10.2. [During the ICO](#during-the-ico)
    - 10.3. [Post-ICO Finalization and Burning Unsold Tokens](#post-ico-finalization-and-burning-unsold-tokens)
    - 10.4. [Maintaining the Index Post-ICO](#maintaining-the-index-post-ico)
    - 10.5. [Liquidity Provider Participation During ICO](#liquidity-provider-participation-during-ico)
    - 10.6. [Public Sale Enhancements (New)](#public-sale-enhancements-new)
11. [FAQ](#faq)
12. [Contact Information](#contact-information)
13. [Conclusion](#conclusion)

---

## Introduction
COIN100 (C100) is a decentralized cryptocurrency index fund built on the Polygon network. It represents the top 100 cryptocurrencies by market capitalization, mirroring the performance of the overall crypto market. Inspired by traditional index funds like the S&P 500, C100 provides diversified, market-wide exposure to the crypto industry without requiring active portfolio management from investors.

COIN100 (C100) offers a seamless, fair, and transparent way to invest in the top 100 cryptocurrencies. Through a robust rebasing mechanism aligned with market capitalization, fee-based treasury and liquidity growth, multiple liquidity pool support, and secure access controls, it aims to become a trusted and stable representation of the crypto market’s collective growth. With a clear path towards decentralized governance and community-driven evolution, C100 empowers investors to participate in a diversified crypto index without the complexities of active portfolio management. Join the community, contribute to liquidity provisioning, and help shape the future of decentralized index investing.

## Problem Statement
The crypto market can be volatile and fragmented. Investors seeking broad exposure face challenges in selecting and maintaining a balanced portfolio of top assets. Without a simple mechanism to track the aggregate performance of the top 100 cryptocurrencies, investors may either miss growth opportunities or take on unnecessary risk.

## Solution: COIN100 (C100) Token
C100 addresses these challenges by:
- Offering a token that represents a proportional share of the top 100 crypto market cap.
- Automatically adjusting each holder’s balance through global rebases as the top 100 market cap changes.
- Implementing a fixed pricing mechanism during presale and liquidity pool-based pricing post-presale.
- Introducing fee-based treasury and liquidity growth mechanisms.
- Supporting multiple liquidity pools to maximize liquidity and decentralization.
- Simplifying public sale mechanics to ensure broad accessibility and ease of participation for all investors.
- **(New)** Enhancing the public sale with vesting schedules, purchase caps, delays, and multi-token payment options.

## Key Principles and Features

### 4.1. Fairness and Equal Treatment of Holders
Every holder’s balance scales proportionally with changes in the total market cap. No single participant is advantaged or disadvantaged during rebases.

### 4.2. Global Rebase Mechanism
On each rebase call, the total supply adjusts to reflect the updated top 100 crypto market cap. All balances scale equally, maintaining each holder’s fractional ownership.

### 4.3. Fixed Pricing During Presale
During the presale period, C100 tokens are sold at a fixed rate of 1 C100 = 0.001 USDC (example rate). This ensures price stability and predictability for early investors.

### 4.4. Fee-Based Treasury and Liquidity Growth
C100 introduces a 2% transaction fee, split equally between the treasury (1%) and the approved liquidity pools (1%). This mechanism supports continuous growth and funding for development, marketing, and liquidity provisioning.

### 4.5. Multiple Liquidity Pool Support
C100 supports multiple liquidity pools (C100/USDC) managed by the admin to maximize liquidity, enhance decentralization, and ensure resilience. This allows liquidity to be distributed across various DEXs, providing flexibility for liquidity providers and improving price stability.

### 4.6. Simplified Public Sale Mechanics
The public sale is streamlined to accept only USDC (and/or other tokens) at a fixed rate, reducing complexity and enhancing user experience. This ensures broad accessibility and ease of participation for all investors.

## Tokenomics

### 5.1. Initial Parameters
- **Total Supply:** Equal to the initial top 100 crypto market cap (denominated in C100 units).
- **Initial Price:** Fixed at approximately 0.001 USDC per C100 token during presale (example).
- **(New)** Vesting & Purchase Caps: The public sale may include vesting schedules, purchase limits, and delay periods (see [Section 10.6](#public-sale-enhancements-new)).

### 5.2. Distribution (Treasury Allocation & ICO)
- **Treasury Allocation:** 100% of the initial supply is allocated to the treasury for distribution during the ICO and liquidity provisioning.
- **ICO Allocation:** The treasury manages the sale of C100 tokens during the ICO, allowing widespread distribution and community participation.

### 5.3. Rebase Formula
ratio = M_new / M_old New Supply = Old Supply * ratio
Every holder’s balance is multiplied by the same ratio. This ensures fair and transparent tracking of the market cap changes.

### 5.4. Market Dynamics and Price Stability
If the market cap doubles, all balances double, maintaining the same fractional ownership. As the community matures and markets become more efficient, the token price should remain stable around its baseline in response to these proportional adjustments.

### 5.5. Liquidity Provider Rewards
Liquidity providers are incentivized through a fixed reward system. A dedicated 1% fee from each transaction is allocated to all approved liquidity pools, ensuring deep liquidity pools, reducing slippage, and fostering a robust trading environment.

### 5.6. Fee-Based Treasury
A 1% transaction fee is collected and sent to the treasury address. This mechanism supports the growth and sustainability of the project by funding development, marketing, audits, and other strategic initiatives.

## Technical Architecture

### 6.1. Polygon Network
Deployed on Polygon for low gas fees and high throughput, ensuring efficient and cost-effective transactions for users.

### 6.2. C100 Token Contract
Implements ERC20 standards with a rebasing mechanism, ownership control, pause/unpause functionalities, fee splitting between treasury and multiple liquidity pools, rebase ratio limits, and integration points for future governance.

### 6.3. Public Sale Contract
Handles the initial distribution of C100 tokens. Investors purchase C100 with USDC (and potentially other whitelisted tokens) at a fixed rate during the ICO period. Unsold tokens are burned at the end, ensuring only the circulating supply reflects real participants.

### 6.4. Scaling and GonsPerFragment
Balances are tracked in a large integer unit called “gons.” The global `gonsPerFragment` variable determines how these translate into user balances. On rebase, adjusting `gonsPerFragment` updates everyone’s balance proportionally in O(1) complexity.

### 6.5. Rebase Mechanism
The rebase mechanism adjusts the total supply based on the new market capitalization and current price. During presale, a fixed price is used, and post-presale, the price is determined by averaging prices from multiple approved liquidity pools (C100/USDC). This ensures accurate and real-time supply adjustments aligned with market conditions.

### 6.6. Rebase Ratio Limits (New)
To prevent extreme jumps in supply, the C100 token contract enforces **maxRatio** and **minRatio** during a rebase. For example:
- **maxRatio = 2e18** (+100% limit on a single rebase)
- **minRatio = 0.5e18** (–50% limit on a single rebase)

Any attempted rebase ratio outside these bounds will revert, ensuring stability and protecting holders from drastic supply changes.

### 6.7. Enhanced Public Sale Features (New)
The new **`C100PublicSale`** contract introduces:
- **Multiple Payment Tokens:** Buyers can purchase C100 using approved ERC20 tokens at defined rates.
- **Vesting Schedules:** Purchased tokens are locked for a certain duration (e.g., 12 months) and claimable after the vesting period.
- **Purchase Caps:** Each wallet can only buy up to a set maximum of C100 tokens during the sale, preventing large whales from dominating.
- **Purchase Delays:** After buying, users must wait a certain time (e.g., 5 minutes) before buying again, mitigating bot abuse.
- **Finalize and Burn:** After the sale ends, any truly unsold tokens are burned, preserving supply integrity.
- **Claim Function:** Once the vesting period is over, users call `claimTokens()` to retrieve their purchased C100.
- **Admin Rescue:** Tokens accidentally sent to the sale contract (except C100 itself or whitelisted payment tokens) can be rescued by the admin, ensuring safety.

## Governance

### 7.1. Transition from Owner to Governor
Initially, the treasury manages the contract. Over time, a governor contract can be introduced. The governor can propose and vote on changes (parameters, treasury usage, etc.), enabling community-driven evolution.

### 7.2. Future Governor Contract
By deploying a governor contract and timelock controller, the project gradually moves towards full decentralization. Governance token holders can vote on upgrades, new features, or parameter changes (e.g., adjusting the rebase frequency, fees, or liquidity rewards).

### 7.3. Community Involvement
The community will shape the project’s future by proposing:
- Adjusting parameters (fees, rebase frequency)
- Allocating treasury funds for development, marketing, or liquidity
- Introducing new features or improvements
- Managing liquidity provider reward percentages

## Security

### 8.1. Ownership Controls
The `onlyAdmin` modifiers ensure that only authorized parties (treasury or governor) can make critical changes, safeguarding the contract against unauthorized modifications.

### 8.2. Pause/Unpause Mechanisms
The contract can be paused in emergencies, preventing transfers and safeguarding against exploits during uncertain times.

### 8.3. Reentrancy Guards
NonReentrant modifiers protect against complex reentrancy attacks, ensuring safe execution of functions like buying tokens or rebasing.

### 8.4. Audits and Best Practices
Smart contract auditing and community code reviews enhance trust and security. Following industry standards, best practices, and thorough testing before mainnet deployment is crucial.

### 8.5. Token Rescue and Burning
Admins can rescue non-C100 tokens sent to the contract and burn unsold C100 tokens post-ICO. Additionally, tokens can be burned from the treasury to manage supply and support market stability. Approved liquidity pools are protected from rescue operations to ensure their integrity.

## Roadmap

### Phase 1: Launch
- **Smart Contract Development**
  - Core token contract implementation
  - Public sale contract development
  - Security features integration
- **Security Audits**
  - Multiple independent audits
  - Bug bounty program
  - Community code review
- **Initial Community Building**
  - Social media presence establishment
  - Community channels setup
  - Educational content creation
- **Public Sale Launch**
  - ICO initiation
  - Liquidity pool creation
  - Initial market making

### Phase 2: Growth
- **Exchange Listings**
  - DEX integrations with multiple platforms
  - CEX partnerships
  - Market maker relationships
- **Marketing Campaigns**
  - Brand awareness initiatives
  - Influencer collaborations
  - Educational webinars
- **Community Expansion**
  - Ambassador program
  - Regional community groups
  - Content creator network
- **Partnership Development**
  - Strategic alliances
  - Integration partnerships
  - Cross-protocol collaborations

### Phase 3: Evolution
- **Governance Integration**
  - Deploy governor contract and timelock controller
  - Enable community voting on proposals
- **Automated Rebase System**
  - Implement automated rebase triggers via oracles
  - Introduce fail-safe mechanisms
- **Enhanced Market Analytics**
  - Real-time tracking dashboard
  - Performance metrics
  - Market insight tools
- **Additional Trading Pairs**
  - New liquidity pools across different DEXs
  - Cross-chain bridges
  - Synthetic asset integration

### Phase 4: Maturity
- **Full Decentralization**
  - Complete transition to community governance
  - Multi-signature treasury management
- **Advanced Security Features**
  - Multi-sig implementations
  - Emergency response system
  - Enhanced audit coverage
- **Cross-chain Integration**
  - Layer 2 solutions
  - Multiple blockchain support
  - Unified liquidity management

## ICO Plan (Simplicity-Focused)

### 10.1. ICO Parameters
- **Duration:** 12 months (example).
- **Accepted Currency:** USDC and/or other approved ERC20 tokens.
- **Rate:** Fixed at 1 C100 = 0.001 USDC (example) or set by the admin’s defined rate.
- **Liquidity Provider Reward:** A portion (e.g., 1%) of each transaction fee allocated to approved liquidity pools.

### 10.2. During the ICO
- **Purchases:** Investors buy C100 directly from the public sale contract using USDC (or other whitelisted tokens) at a fixed or specified rate.
- **Rebase Operations:** Admins periodically call rebase to keep C100 supply aligned with the top 100 market cap.
- **Liquidity Provision:** Liquidity providers contribute to approved C100/USDC liquidity pools and earn rewards based on their contribution.

### 10.3. Post-ICO Finalization and Burning Unsold Tokens
At the end of the ICO:
- **No More Purchases:** ICO phase concludes, preventing further token sales.
- **Burn Unsold Tokens:** Any truly unsold tokens are burned, ensuring the supply reflects only actively held tokens.

### 10.4. Maintaining the Index Post-ICO
After the ICO:
- **Continuous Rebasing:** Continue periodic rebases to adjust supply based on market cap changes.
- **Automated Upkeep:** Transition to automated rebase operations using oracles and governance decisions.
- **Governance Enhancements:** Introduce advanced features such as treasury management, automated liquidity rewards, and fee adjustments through community proposals.

### 10.5. Liquidity Provider Participation During ICO
- **Incentives:** During the ICO, liquidity providers are rewarded with a portion of the transaction fees.
- **Participation:** Anyone can become a liquidity provider by adding C100 and USDC to the approved DEXs.
- **Rewards Distribution:** Rewards are distributed proportionally based on the amount of liquidity each provider contributes, ensuring fair compensation for contributions.

### 10.6. Public Sale Enhancements (New)
In the updated **C100PublicSale** contract, several **new features** improve fairness and security:

1. **Vesting Period**  
   - All purchased C100 tokens are locked for a predefined duration (e.g., 12 months). Investors must wait until the vesting cliff to claim their tokens, reducing immediate sell pressure.

2. **Per-User Purchase Cap**  
   - A maximum limit is set for each wallet’s total C100 purchases during the sale, preventing excessively large accumulations by single participants.

3. **Purchase Delay**  
   - After each purchase, a user must wait a specified period (e.g., 5 minutes) before buying again, discouraging rapid, bot-based accumulations.

4. **Multiple ERC20 Payments**  
   - The public sale contract can whitelist several payment tokens (e.g., USDC, DAI, or WETH) with custom rates. Each token is carefully configured with a price ratio that determines how much C100 a buyer receives per token.

5. **Finalize and Burn**  
   - After the public sale ends, the contract’s `finalize()` function burns any unsold tokens. Only tokens genuinely sold or vested remain, ensuring supply integrity.

6. **Claim Function**  
   - Investors claim their locked tokens after the vesting duration has elapsed. Any unclaimed tokens remain locked until the user calls the claim function.

7. **Admin Rescue**  
   - The contract owner or future governance can rescue tokens accidentally sent to the sale contract (excluding the main C100 token or whitelisted payment tokens), ensuring clarity and asset safety.

---

## FAQ

1. **Q:** What is COIN100 (C100)?  
   **A:** It’s a decentralized index fund token on Polygon, tracking the top 100 cryptos by market cap.

2. **Q:** How does C100 track the top 100 crypto market cap?  
   **A:** Through a global rebasing mechanism. As the total market cap changes, the supply and balances adjust proportionally.

3. **Q:** Is C100 an ERC20 token?  
   **A:** Yes, it follows the ERC20 standard with additional rebasing logic.

4. **Q:** On which network is C100 deployed?  
   **A:** Polygon (POL) network.

5. **Q:** Why Polygon?  
   **A:** Low fees, fast transactions, and high scalability.

6. **Q:** What is the initial supply of C100?  
   **A:** Equal to the initial top 100 crypto market cap (denominated in C100 units).

7. **Q:** What is the reference price at launch?  
   **A:** Fixed at 0.001 USDC per C100 token during the presale.

8. **Q:** What does rebase mean?  
   **A:** Rebase changes everyone’s balances proportionally to reflect changes in total market cap.

9. **Q:** Who initiates the rebase initially?  
   **A:** Admins can call the rebase function to adjust supply based on market cap updates.

10. **Q:** Will there be automated rebasing eventually?  
    **A:** Yes, once governance and oracles are established, rebasing can be automated.

11. **Q:** What happens if the market cap doubles?  
    **A:** All token balances double, maintaining the same fractional ownership.

12. **Q:** What if the market cap halves?  
    **A:** All balances reduce proportionally, preserving fractional ownership.

13. **Q:** Is there a fixed time interval for rebases?  
    **A:** Yes, rebases occur based on a predefined rebase frequency, initially set to daily.

14. **Q:** How is fairness ensured?  
    **A:** Every holder’s balance changes by the same ratio on rebases, ensuring no favoritism.

15. **Q:** Does the treasury receive special treatment in rebases?  
    **A:** No, the treasury’s tokens also rebase equally like all other holders.

16. **Q:** What happens to the 100% supply at launch?  
    **A:** All tokens are allocated to the treasury for distribution during the ICO and liquidity provisioning.

17. **Q:** Is there an ICO?  
    **A:** Yes, the treasury manages the ICO to distribute tokens to the community.

18. **Q:** What if not all tokens sell in the ICO?  
    **A:** Unsold tokens are burned at the end of the ICO, ensuring the supply accurately reflects active participants.

19. **Q:** Why burn unsold tokens?  
    **A:** To maintain supply integrity and ensure fairness among active holders.

20. **Q:** Can I buy C100 after the ICO?  
    **A:** Yes, on DEXs where liquidity is provided by the treasury and liquidity providers.

21. **Q:** Will there be a stable price?  
    **A:** The presale has a fixed price, and post-presale pricing is determined by the approved liquidity pools, aiming for stability through market forces.

22. **Q:** Does C100 pay dividends?  
    **A:** Not directly. The value accrues by tracking the market cap of the top 100 cryptos.

23. **Q:** How do I store C100?  
    **A:** In any Polygon-compatible ERC20 wallet.

24. **Q:** How do I track the top 100 market cap changes?  
    **A:** Admins manually update the market cap during rebases, with plans to automate via oracles in the future.

25. **Q:** Is the contract audited?  
    **A:** Yes, the team conducts multiple independent audits and encourages community code reviews.

26. **Q:** Can C100 be paused?  
    **A:** Yes, the admin can pause the contract in emergencies.

27. **Q:** Why pause the contract?  
    **A:** To prevent malicious exploitation during unexpected issues.

28. **Q:** What is `gonsPerFragment`?  
    **A:** An internal scaling factor that efficiently adjusts balances during rebases.

29. **Q:** Does rebase affect my token count in my wallet?  
    **A:** Yes, your balance number changes proportionally to reflect market cap adjustments.

30. **Q:** Can I lose my fraction of ownership?  
    **A:** No, your fraction relative to total supply remains constant unless you trade.

31. **Q:** What if someone doesn’t trust the admins’ data?  
    **A:** Eventually, governance and oracles will automate and decentralize updates, reducing trust issues.

32. **Q:** Could governance change the fee parameters?  
    **A:** Yes, once governance is established, it can vote on parameters like fees and treasury allocations.

33. **Q:** Will there be a treasury?  
    **A:** Yes, a fee-based treasury is introduced, funded by transaction fees split between the treasury and approved liquidity pools.

34. **Q:** How do treasury fees work?  
    **A:** A portion of transaction fees (1%) is sent to the treasury wallet, supporting project growth and strategic initiatives.

35. **Q:** What is the benefit of a treasury?  
    **A:** It funds development, marketing, audits, and liquidity incentives, ensuring the project's sustainability.

36. **Q:** Is there a whitelist or KYC?  
    **A:** No. Anyone on Polygon can buy C100; it’s permissionless.

37. **Q:** Can I sell C100 anytime?  
    **A:** Yes, on any DEX where liquidity is available.

38. **Q:** Is C100 inflationary?  
    **A:** Rebase adjusts supply proportionally based on market cap changes, maintaining representational integrity.

39. **Q:** Does market cap growth dilute existing holders?  
    **A:** No, growth increases everyone’s balance proportionally.

40. **Q:** If the index grows, do I earn more tokens?  
    **A:** Yes, your token balance increases on rebase events reflecting market cap growth.

41. **Q:** Can governance remove the treasury’s rights?  
    **A:** Yes, if coded accordingly, governance can manage treasury permissions and allocations.

42. **Q:** What if governance makes bad decisions?  
    **A:** Governance is controlled by token holders. It’s community-driven, and responsible voting mitigates risks.

43. **Q:** Can I propose changes without being the governor?  
    **A:** Typically, proposals require a minimum token amount to participate, as defined by the governance contract.

44. **Q:** Will the token’s name or symbol change?  
    **A:** Unlikely. It’s set at deployment.

45. **Q:** How do I add C100 to my wallet interface?  
    **A:** Import the token’s contract address into your Polygon-compatible wallet.

46. **Q:** Are rebases taxable events?  
    **A:** Consult a tax professional. Tax treatment may vary by jurisdiction.

47. **Q:** Is there a minimum or maximum investment?  
    **A:** No strict limits by the contract. Market liquidity and token price determine practical limits.

48. **Q:** What if I buy right before a rebase?  
    **A:** Your purchase includes the upcoming rebase changes. You neither gain nor lose unfairly.

49. **Q:** Do I need to claim my rebased tokens?  
    **A:** No. Rebase updates balances automatically.

50. **Q:** How often will rebases occur initially?  
    **A:** Based on the predefined rebase frequency, initially set to daily.

51. **Q:** Will there be an official oracle integration?  
    **A:** Yes, plans include automating rebases with oracles as governance evolves.

52. **Q:** Can governance integrate Chainlink oracles?  
    **A:** Yes, governance can approve contracts and integrate reliable oracles to automate rebasing.

53. **Q:** Are there smart contract upgrade plans?  
    **A:** With governance, changes can be proposed and voted on, potentially including upgrades.

54. **Q:** What if Polygon network faces issues?  
    **A:** The token resides on Polygon. Any network-wide issues affect all tokens equally.

55. **Q:** Is there a limit to how large the top 100 crypto market cap can grow?  
    **A:** Practically no. As it grows, C100 supply and balances grow proportionally.

56. **Q:** How do I know the top 100 composition?  
    **A:** Initially off-chain data. In the future, oracles or references can be introduced on-chain.

57. **Q:** Does composition of the top 100 matter for holders?  
    **A:** Not directly. You always hold a fraction of the total cap, regardless of composition changes.

58. **Q:** What if the top 100 changes (some coins leave, others enter)?  
    **A:** The index’s total cap changes are reflected at the next rebase. No direct action needed by holders.

59. **Q:** Can I use C100 in DeFi (lending, staking)?  
    **A:** Potentially yes, if DeFi protocols support C100.

60. **Q:** Is there a whitepaper available?  
    **A:** This documentation serves as a comprehensive whitepaper, with detailed docs available for the community.

61. **Q:** Will the contract be verified on PolygonScan?  
    **A:** Yes, for transparency and trust.

62. **Q:** How do I participate in governance voting?  
    **A:** Acquire enough C100 to vote, and interact with the governor contract once deployed.

63. **Q:** Can governance freeze rebases?  
    **A:** If coded, yes, governance might pause or adjust rebase conditions.

64. **Q:** Is there a maximum supply cap?  
    **A:** No hard cap. Supply floats with market cap.

65. **Q:** Could C100 track a different index in the future?  
    **A:** Governance could propose changing index parameters if such flexibility is allowed.

66. **Q:** Does the token have a logo?  
    **A:** Initially, a simple logo. The community can decide on rebranding later.

67. **Q:** Are there any partnerships?  
    **A:** Partnerships may be pursued. Check announcements for updates.

68. **Q:** Will liquidity be locked?  
    **A:** Admin or governance may decide on liquidity locking for added trust and security.

69. **Q:** Does C100 rely on a single entity?  
    **A:** Initially treasury-managed, aiming to evolve into fully decentralized governance.

70. **Q:** Can C100 survive if the treasury disappears?  
    **A:** Once governance is established, yes. The project can run autonomously.

71. **Q:** How can I suggest improvements?  
    **A:** Join Discord, Reddit, or submit proposals once governance is live.

72. **Q:** Can I fork C100?  
    **A:** The code is open-source. Others can fork, but trust, community, and liquidity matter.

73. **Q:** Will large holders influence votes heavily?  
    **A:** Yes, governance is token-weighted. More tokens mean more voting power.

74. **Q:** Could governance adjust transaction fees?  
    **A:** Yes, if proposals pass, governance can adjust fee parameters.

75. **Q:** Where do fees go?  
    **A:** Fees are split between the treasury (1%) and all approved liquidity pools (1%).

76. **Q:** How is treasury managed?  
    **A:** By governance votes on how to allocate or use funds.

77. **Q:** Can I redeem my tokens for underlying assets?  
    **A:** No direct redemption. C100 is synthetic exposure, not a claim on underlying coins.

78. **Q:** What if the top 100 index calculation method changes?  
    **A:** Governance could adapt the model if needed.

79. **Q:** How frequently is market cap data updated?  
    **A:** Admins call the rebase function based on the predefined frequency, initially daily.

80. **Q:** Does holding C100 require any special steps?  
    **A:** No, just hold it in a Polygon-compatible wallet.

81. **Q:** Is there a minimum gas token needed?  
    **A:** Yes, POL (or MATIC, depending on the chain rename) for gas fees on Polygon.

82. **Q:** Can I bridge C100 to other chains?  
    **A:** Potentially in the future if bridges support it.

83. **Q:** Will listing on centralized exchanges happen?  
    **A:** Up to exchanges’ interest. The community can encourage listings.

84. **Q:** Does C100 track stablecoins in the top 100?  
    **A:** If stablecoins are in the top 100 by market cap, they are included. It’s a neutral index.

85. **Q:** Are smart contract addresses known at launch?  
    **A:** Yes, published once deployed and verified.

86. **Q:** Will there be a testnet version?  
    **A:** Likely, for community testing before mainnet.

87. **Q:** Does the token support EIP-2612 (permit)?  
    **A:** Not initially. Could be added by governance if desired.

88. **Q:** Is there a referral program?  
    **A:** Not currently. Community can propose incentive programs later.

89. **Q:** How is liquidity provided initially?  
    **A:** Treasury adds initial liquidity to approved DEXs, possibly at the fixed presale rate.

90. **Q:** Can I track C100 price on aggregators?  
    **A:** Yes, once listed, price data will appear on coin trackers.

91. **Q:** Is C100 correlated with Bitcoin/Ethereum alone?  
    **A:** It’s correlated with the entire top 100 cryptos, not just one coin.

92. **Q:** Can I short C100?  
    **A:** Only if a DeFi platform offers derivatives. C100 doesn’t provide native shorting.

93. **Q:** Does C100 have a roadmap for oracle integration?  
    **A:** Yes, plans include automating rebases with oracles as governance evolves.

94. **Q:** What if no one calls rebase?  
    **A:** Then the index isn’t updated. Market price may drift from the reference. Governance and oracles are planned to handle this.

95. **Q:** Will the team remain anonymous?  
    **A:** The team may reveal themselves over time. Governance reduces reliance on team identity.

96. **Q:** Is the code open source?  
    **A:** Yes, allowing transparency and community audits.

97. **Q:** How do I get support?  
    **A:** Via email, Discord, Reddit, or other community channels as listed in Contact Information.

98. **Q:** Why trust C100 over other tokens?  
    **A:** C100 provides broad, fair, and transparent index exposure with a clear path to decentralization and community governance.

99. **Q:** How are liquidity providers rewarded?  
    **A:** Liquidity providers receive a fixed 1% fee from each transaction, allocated proportionally across all approved liquidity pools.

100. **Q:** What is the fee structure for transactions?  
     **A:** A total of 2% fee per transaction is applied, split equally between the treasury (1%) and the approved liquidity pools (1%).

101. **Q:** How is the fixed price during presale maintained?  
     **A:** During the presale period, a fixed rate of 1 C100 = 0.001 USDC is enforced, ensuring price stability for early investors.

102. **Q:** Can the fixed presale price be changed?  
     **A:** No, the presale price is fixed to ensure consistency and predictability during the sale period.

103. **Q:** How is the rebase frequency determined?  
     **A:** The rebase frequency is predefined and can be adjusted by governance in the future to meet community needs.

104. **Q:** Can the liquidity pool be changed after deployment?  
     **A:** Yes, admins or governance can set or update approved liquidity pool addresses as needed.

105. **Q:** How are fees allocated if there are no approved liquidity pools?  
     **A:** If no approved liquidity pools are set, all LP fees are allocated to the treasury to prevent loss.

106. **Q:** What ensures the security of fee allocations?  
     **A:** The contract uses OpenZeppelin’s `SafeERC20` for secure token transfers, `EnumerableSet` for managing approved pools, and incorporates reentrancy guards.

107. **Q:** How are unsold tokens handled post-ICO?  
     **A:** Unsold tokens are burned, reducing the total supply and maintaining supply integrity.

108. **Q:** Can the treasury be updated after deployment?  
     **A:** Yes, admins can update the treasury address to a new address as needed.

109. **Q:** What if an approved liquidity pool becomes compromised?  
     **A:** Governance can remove the compromised pool and add a secure, trusted pool to ensure continued fee allocation integrity.

110. **Q:** How are token burns executed?  
     **A:** Admins can burn tokens from the treasury by transferring them to the burn address.

111. **Q:** Can transaction fees be disabled?  
     **A:** Currently, transaction fees are enabled by default, but future governance can adjust fee parameters.

112. **Q:** What measures are in place to prevent abuse of the burn function?  
     **A:** Only authorized admins or governance can execute burns, ensuring controlled and transparent supply management.

---

## Contact Information
For further inquiries, support, or to engage with the COIN100 team, please reach out through the following channels:

- **Website:** [https://coin100.link](https://coin100.link)  
- **Email:** [mayor@coin100.link](mailto:mayor@coin100.link)  
- **Github:** [coin100-dao](https://github.com/coin100-dao)  
- **Discord:** [Join Our Discord](https://discord.com/channels/1318664310490398770/1318664310490398773)  
- **Reddit:** [r/Coin100](https://www.reddit.com/r/Coin100)  
- **X:** [@Coin100token](https://x.com/Coin100token)  
- **Telegram:** [@Coin100token](https://t.me/coin100token)  
- **Coin100 Polyscan:** [C100](https://polygonscan.com/token/0x3c5034f0b8e9ecb0aa13ef96adf9d97fb0107eec)  
- **Coin100 PublicSale Polyscan:** [C100 public sale](https://polygonscan.com/address/0xaf4fc2742cea373ec18f17a601e64a74aeebb0cc)

---

## Conclusion
COIN100 (C100) offers a robust and transparent mechanism for investors to gain diversified exposure to the top 100 cryptocurrencies. Through its rebasing supply model, fee-based treasury and liquidity growth, multiple liquidity pool support, and streamlined public sale mechanics—now **enhanced** by vesting schedules, purchase caps, multi-token payment support, and min/max rebase ratio limits—C100 stands as a reliable and scalable index fund in the decentralized finance ecosystem. With a clear governance roadmap and community-driven initiatives, C100 is poised to evolve and adapt, ensuring long-term stability and value for its holders. Join the COIN100 community today and be part of the future of decentralized index investing.

---
