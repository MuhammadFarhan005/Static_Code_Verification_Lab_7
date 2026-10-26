# Static Verification Review Checklist

| Category | Result | Defect |
| :--- | :--- | :--- |
| **1. Initialization** | issue | Uninitialized local variable `sum` accumulated in `averageAttack()`. |
| **2. Pointers** | issue | Null pointer dereferences, Use-After-Free in `defeatMonster()`, mismatched deallocation (`delete` vs `delete[]`) in `readBoss()`, and memory leak of `bonus` in `main()`. |
| **3. Arrays /Buffers** | issue | Out-of-bounds write in `spawnMonster()` (exceeding `MAX_MONSTERS`), and buffer overflow vulnerability in `readBoss()` via unbounded `std::cin`. |
| **4. Loops** | issue | Off-by-one loop condition (`i <= monsterCount`) in `totalMonsterHealth()`. |
| **5. Arithmetic** | issue | Unsigned arithmetic comparison flaw in `attackMonster()`, integer truncation in `calculateDamage()`, and potential division by zero in `averageAttack()`. |
| **6. Control Flow** | issue | Assignment operator used in conditional logic (`id = id`) inside `findMonster()`, and missing return path for non-void function `playerRank()`. |
| **7. Function Calls** | issue | Returning reference to stack-allocated local variable in `getMonsterLabel()`, and function calls passing invalid IDs without prior null checks. |
| **8. Classes** | issue | Violation of the Rule of Three/Five causing double-free on shallow copy (`Game copy = game;`), and failure to update pointer array/count upon object deletion in `defeatMonster()`. |
