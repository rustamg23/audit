# StakingRewardV3 Security Audit Report

## Introduction

### Project overview

### Scope of the Audit
The scope of the audit includes the following smart contracts at:
https://github.com/keep3r-network/StakingRewardsV3/blob/13ecc6966ae1a413f62224382bfd4d64b1a22351/contracts/StakingRewardsV3-1.sol
The audited commit identifier is `13ecc6966ae1a413f62224382bfd4d64b1a22351`

## Security Assessment Methodology

Only one auditor analyzes this contract according to the methodology described below:

### 1. Project architecture review.

# An attempt to imagine project documentation.
# General code review.
# Reverse research and study of the architecture of the code based on the source code only.
```
Stage goals:
# Building an independent view of the project's architecture and identifying logical flaws in the code.
```

### 2. Checking the code against the checklist of known vulnerabilities.

* Manual code check for vulnerabilities from the company's internal checklist.
* The company's checklist is constantly updated based on the analysis of hacks, research and audit of the clients’ code.
* Checking with static analyzers (i.e Slither).

```
Stage goal: 
Eliminate typical vulnerabilities (e.g. reentrancy, gas limit, flashloan attacks etc.)
```

### 3. Checking the code for compliance with the desired security model.

* Detailed imagination of the project documentation and discuss with colleagues.

```
Stage goal: 
Detection of inconsistencies with the desired model
```

### 4. Bug fixing & re-check.
* Client fixes or comments on every issue.
* Upon completion of the bug fixing, the auditors double-check each fix and set the statuses with a link to the fix.

```
Stage goal:
Preparation of the final code version with all the fixes
```

### 5. Preparation of the final audit report and delivery to the customer.

## Findings Severity breakdown

### Classification of Issues

* CRITICAL: Bugs leading to assets theft, fund access locking, or any other loss funds to be transferred to any party.
* MAJOR: Bugs that can trigger a contract failure. Further recovery is possible only by manual modification of the contract state or replacement.
* WARNINGS: Bugs that can break the intended contract logic or expose it to DoS attacks.
* COMMENTS: Other issues and recommendations reported to/ acknowledged by the team.

Based on the feedback received from the Customer's team regarding the list of findings discovered by the Contractor, they are assigned the following statuses:

### Findings' breakdown status

* FIXED: Recommended fixes have been made to the project code and no longer affect its security.
* ACKNOWLEDGED: The project team is aware of this finding. Recommendations for this finding are planned to be resolved in the future. This finding does not affect the overall safety of the project.
* NO ISSUE: Finding does not affect the overall safety of the project and does not violate the logic of its work
* NEW: Waiting for project team's feedback on the finding discovered

## Report

## CRITICAL
# the modifier update(uint tokenId) {...} is too long. The modifier should only be used for checks.

## MAJOR
# Reentrancy, amount0 and amount1 are not zeroed and can be summed forever:
 * earned0 += amount0; (#84)
 * earned1 += amount1; (#85)
# Multiplication on the result of a division:
 * return rewardPerLiquidityStored + ((lastTimeRewardApplicable() - lastUpdateTime) * rewardRate * PRECISION / totalLiquidity); (#73)
 * uint _reward = (_liquidity * (rewardPerLiquidity() - tokenRewardPerLiquidityPaid[tokenId]) / PRECISION); (#103)
 * uint _earned = _reward * _secondsInside / _maxSecondsElapsed; (#104)
 * rewardRate = amount / DURATION; (#217)
 * rewardRate = (amount + _leftover) / DURATION; (#222)


## WARNING
# Constructor lacks a zero-check on:
 * reward = _reward; (#56)
 * pool = _pool; (#57)
  
## COMMENT
 * The Approve() function is not specified in the contract, but it must be used for the deposit() function.

## Results
 * 9 vulnerabilities and 1 wish

### Conclusion
 * This is a well-protected smart contract, but it needs some security update.
