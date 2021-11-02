# Akropolis Security Audit Report

###### tags: `Akropolis`

## Introduction

### Project overview

### Scope of the Audit
The scope of the audit includes the following smart contracts at:
https://github.com/akropolisio/akropolis/tree/6dd43f4cee728bad1ebaa7d43ecc24aea46fbd7d/contracts/vakro/AdelVAkroVestingSwap.sol
https://github.com/akropolisio/akropolis/tree/6dd43f4cee728bad1ebaa7d43ecc24aea46fbd7d/contracts/vakro/MinterRole.sol
https://github.com/akropolisio/akropolis/tree/6dd43f4cee728bad1ebaa7d43ecc24aea46fbd7d/contracts/vakro/VestedAkroSenderRole.sol
https://github.com/akropolisio/akropolis/tree/6dd43f4cee728bad1ebaa7d43ecc24aea46fbd7d/contracts/vakro/VestedAkro.sol
https://github.com/akropolisio/akropolis/tree/6dd43f4cee728bad1ebaa7d43ecc24aea46fbd7d/contracts/yearnV2/vault-savings/VaultSavingsV2.sol
The audited commit identifier is `6dd43f4cee728bad1ebaa7d43ecc24aea46fbd7d`

## Security Assessment Methodology

A group of auditors are involved in the work on the audit who check the provided source code independently of each other in accordance with the methodology described below:

### 1. Project architecture review.

* Reviewing project documentation.
* General code review.
* Reverse research and study of the architecture of the code based on the source code only.
* Mockup prototyping.

```
Stage goals:
* Building an independent view of the project's architecture and identifying logical flaws in the code.
```

### 2. Checking the code against the checklist of known vulnerabilities.

* Manual code check for vulnerabilities from the company's internal checklist.
* The company's checklist is constantly updated based on the analysis of hacks, research and audit of the clients’ code.
* Checking with static analyzers (i.e Slither, Mythril, etc).

```
Stage goal: 
Eliminate typical vulnerabilities (e.g. reentrancy, gas limit, flashloan attacks etc.)
```

### 3. Checking the code for compliance with the desired security model.

* Detailed study of the project documentation.
* Examining contracts tests.
* Examining comments in code.
* Comparison of the desired model obtained during the study with the reversed view obtained during the blind audit.
* Exploits PoC development using brownie.

```
Stage goal: 
Detection of inconsistencies with the desired model
```


### 4. Consolidation of interim auditor reports into general one.

* Cross check: each auditor reviews the reports of the others.
* Discussion of the found issues by the auditors.
* Formation of a general (merged) report.

```
Stage goals: 
* Re-check all the problems for relevance and correctness of the threat level
* Provide the client with an interim report
```

### 5. Bug fixing & re-check.
* Client fixes or comments on every issue.
* Upon completion of the bug fixing, the auditors double-check each fix and set the statuses with a link to the fix.

```
Stage goal:
Preparation of the final code version with all the fixes
```

### 6. Preparation of the final audit report and delivery to the customer.

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

### CRITICAL

### MAJOR

### WARNING

### COMMENT

## Results

### Executive summary

### Conclusion
