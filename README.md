# MyToken (MTK) — ERC-20 Token Project  
Beginner Blockchain Project | Ethereum | Remix IDE | Solidity

---

## 📌 Overview
MyToken (MTK) is a simple, educational ERC-20 token implemented in Solidity and deployed using Remix IDE.  
This project covers:

- Writing a smart contract using Solidity (v0.8.x)
- Understanding ERC-20 token standard functions
- Deploying via Remix JavaScript VM
- Testing transfers, allowances, and error conditions
- Generating verification screenshots for submission

The token created is fully compatible with any ERC-20 supporting environment.

---

## 📌 Token Details

| Property | Value |
|---------|--------|
| **Name** | MyToken |
| **Symbol** | MTK |
| **Decimals** | 18 |
| **Total Supply** | 1,000,000 MTK (1e6 × 1e18 units) |
| **Deployer** | Account[0] from Remix VM |

**Total supply provided to constructor:**
1000000000000000000000000


---

## 📌 Contract File: `MyToken.sol`

Place this file inside:
contracts/MyToken.sol
---

# 📌 Step-by-Step Instructions (with Required Screenshots)

Follow these steps exactly in Remix IDE.

---

## **STEP 1 — Create MyToken.sol**

1. Open Remix: https://remix.ethereum.org  
2. In the File Explorer → open **contracts** folder  
3. Click **+ (New File)**  
4. Name it: `MyToken.sol`  
5. Paste the full contract code  
6. Press **Ctrl + S** to save  

📸 **Screenshot Name:**  
`02_code_pasted_MyToken.sol.png`

---

## **STEP 2 — Compile the Contract**

1. Click **Solidity Compiler**  
2. Select compiler version: **0.8.19** (or any 0.8.x)  
3. Click **Compile MyToken.sol**  
4. Wait for green success checkmark  

📸 **Screenshot Name:**  
`03_compiled.png`

---

## **STEP 3 — Deploy the Contract**

1. Go to **Deploy & Run Transactions**  
2. Environment → **JavaScript VM**  
3. Constructor input:1000000000000000000000000

📸 **Take screenshot BEFORE clicking Deploy.**

📸 **Screenshot Name:**  
`04_constructor_value_before_deploy.png`

4. Click **Deploy**  
5. Contract will appear under **Deployed Contracts**

📸 **Screenshot Name:**  
`05_deployed_contract.png`

---

## **STEP 4 — Verify Token Metadata & Deployer Balance**

Under the deployed contract:

- Click **name()** → returns `MyToken`
- Click **symbol()** → returns `MTK`
- Click **decimals()** → returns `18`
- Click **totalSupply()** → returns `1000000000000000000000000`
- Copy **Account[0]** address  
- Call `balanceOf(address)` → should equal totalSupply  

📸 **Screenshot Name:**  
`06_token_info_and_balance.png`

---

## **STEP 5 — Transfer Test (1 Token)**

1. Select **Account[0]** (deployer)  
2. Expand **transfer** function  
3. `_to` = Account[1]  
4. `_value` = `1000000000000000000` (1 MTK)  
5. Click **transact**  
6. Check Transfer event + updated balances  

📸 **Screenshot Name:**  
`07_transfer_success.png`

---

## **STEP 6 — Approve & transferFrom (Allowance Flow)**

### **A — Approve**

1. Switch to **Account[0]**  
2. Call `approve(spender, value)`  
   - `_spender` = Account[2]  
   - `_value` = `2000000000000000000` (2 MTK)  
3. Approval event appears  

### **B — transferFrom**

1. Switch to **Account[2]** (approved spender)  
2. Call `transferFrom(owner, to, value)`  
   - `_from` = Account[0]  
   - `_to` = Account[3]  
   - `_value` = `1000000000000000000` (1 MTK)  
3. Check Transfer event  
4. Allowance should now be **1 MTK left**  

📸 **Screenshot Name:**  
`08_approve_transferFrom.png`

---

## **STEP 7 — Edge-Case Tests (Should Fail)**

Perform these tests:

### ❌ Transfer to zero address

transfer(0x0000000000000000000000000000000000000000, 1000000000000000000)

Expected error: **Cannot transfer to zero address**

### ❌ Transfer more tokens than balance

Expected error: **Insufficient balance**

📸 **Screenshot Name:**  
`09_failed_test.png`


## ✔ What This Project Demonstrates

- ERC-20 standard implementation  
- Transfer & approval mechanics  
- Solidity smart contract best practices  
- Testing using Remix VM  
- Event logs + revert conditions  
- Understanding of token balances and allowances  



