# Layered Grid-based Blockchain Network

I once saw a picture of Bitcoin nodes connected randomly and scattered across the network.  
This made me think: *what if instead of being scattered, the nodes were organized in layers, like rows and columns?*

---

## 1. Transaction Validation Inside Rows
Each row, if it sends a transaction to itself, will have the validation done by the people (miners) in that same row.  
The process starts from the first miner in that row, who does part of the mining and validation.  
Then the next miner (for example, the one in the 5th column) continues the task, and so on, until the last miner in the row completes it.  

In this way:  
- All nodes inside a row are connected and work together.  
- Electricity consumption decreases significantly.  
- The transaction speed (TPS) becomes much higher.  
- The mining process works similar to a mining pool, but depends on the number of miners in each row.  

---

## 2. Helper Miners Between Rows
Now we have two problems, but I also have solutions.  
- **Problem 1:** If there are no miners inside a row → the system will ask for help from the rows above. Based on the column number of the sender and receiver, it moves from left to bottom to find miners.  
These helper miners can move diagonally or linearly and we call them **helper miners** because they assist with validation.  

- **Future Development:** We can classify people (miners) based on their "floor" or level — the bottom ones are the oldest, and the top ones are the newest. This allows future development to solve more problems.  

- **Cross-row Transactions:** If someone sends money from top to bottom (or between rows/columns), the transaction will pass through miners along the path. It starts from the leftmost available miner and continues until validation is complete.  
Again, this ensures miners are helping each other from all directions.  

---

## 3. Block Structure in This Algorithm
Blocks are similar to Bitcoin in being chained, but not linearly.  
Here, blocks are categorized by **rows and columns**, and each has coordinates **(x, y).**  

Each block contains two hashes:  
1. The hash of the block below it in its column.  
2. The hash of the block behind it in its row.  

Blocks in the first row and first column are the foundation blocks and have predefined values.  

👉 This means each block has **two chains.** If one block is tampered with, it’s like a building collapsing — both height and length are weakened.  
So, an attacker would have to break **two difficult chains at once,** making attacks far more difficult.  

---

## 4. Reward Mechanism
Miners receive rewards based on:  
- The number of miners in a row,  
- Their specific role in validation.  

If a miner does not participate, they cannot mine.  
This prevents inflation and ensures fairness.  

Rewards are calculated as the average contribution of all miners in that row.  
Rewards are **not created coins,** but come only from transaction fees.  

Each miner has a **digital piggy bank,** where fees are gradually collected.  
At the end of the month, miners receive the accumulated fees — just like in real life.  

**Additional Rule for Helper Miners:**  
- If an idle miner is assigned as a **helper miner** to assist another miner,  
  a portion of the transaction reward from the assisted miner is allocated to the helper miner.  
- This ensures that even previously idle miners receive compensation for their contribution.  

✅ This results in **lower energy consumption, faster transactions, and higher security.**  
It solves the **blockchain trilemma** without sacrificing decentralization, security, or scalability.  

---

## 5. Possible Problems and Solutions

### Problem 1: Miners leaving the network
If miners resign and the mining population decreases:  
- The system automatically lowers puzzle difficulty but also lowers rewards.  
- This keeps the network stable.  
- It can also temporarily remove low-activity users to reduce search time for miners (like an emergency alarm).  

### Problem 2: Idle Miners
Since the system assigns tasks from left to right, some miners may not receive work.  
In this case:  
- They automatically become helper miners.  
- Idle miners can also self-register as "helpers" so system resources are not wasted.  

### Problem 3: Coordination of Nodes and Blocks
We can set a column limit (e.g., 100 columns) to make coordination more manageable.  

### Problem 4: Parent and Mother Nodes
We can create **one "mother node" and one "father node"** across the network.  
These act as supervisors, ensuring miners start tasks correctly and maintain coordination.  

### Problem 5: Accumulation Attack
To prevent the control of rows and unnecessary energy usage:  
- Every miner must pass an **identity verification (KYC)** before joining the system.  
This increases security.  

### Problem 6: Attacks on Parent/Mother Nodes
- Nodes are constantly changing (increasing or decreasing).  
- Parent and mother nodes also rotate continuously.  
- This makes it much harder for attackers to target them.  

---
