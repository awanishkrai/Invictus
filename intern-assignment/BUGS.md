# Bugs found

Add one section per issue. Bug 1 is filled in to show the format — fix it, then write what you changed. Copy the blank template for the rest.

Keep this file in the repo and **commit it** with your fixes.

---

## Bug 1

**How to reproduce:** Open the app. The expense list says “Newest first”. The first row is Wine (7 Mar). Board game (15 Mar) is further down.

**What is wrong:** The list is showing oldest expenses first. Newest should be at the top.

**What I changed:*I made the sorting logic different*

---





## Bug 2: Balance Calculation Error When Payer is NOT in Split
Location: src/lib/balances.js, lines 16-19

**How to reproduce :** Add an expense where someone pays but is NOT included in the split. For example, create an expense of $100 paid by Aisha but split only between Ben and Carlos. Check Aisha's balance.

**What is wrong**: When the payer is not in the splitWith list, the code subtracts the share twice from the payer's balance. This double-deducts and produces an incorrect balance.

**What I changed**: The logic on lines 16-19 is flawed. I removed this piece of code

