# LEETCODE-Strings-670
Let's perform a dry run of the `maximumSwap` method using an example. 

### Code Breakdown:
- The function takes an integer `num` as input and returns the maximum number you can get by swapping two digits at most once.
- `char[] s`: The digits of the number `num` are converted into a character array `s`.
- `int[] lastIndex`: This array stores the last index of each digit (0–9) in the number.
- The outer loop iterates over each digit in the number, and the inner loop checks if a higher digit (starting from 9) appears later. If such a digit is found, a swap is performed to maximize the number.

### Example: `num = 2736`

Initial state:
- `num = 2736`
- `s = ['2', '7', '3', '6']`
- `lastIndex = [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]` (empty initially)

#### Step 1: Fill `lastIndex` array:
Loop through each digit and update `lastIndex` with the last occurrence of each digit.

- After processing index 0 (`'2'`): `lastIndex[2] = 0`
- After processing index 1 (`'7'`): `lastIndex[7] = 1`
- After processing index 2 (`'3'`): `lastIndex[3] = 2`
- After processing index 3 (`'6'`): `lastIndex[6] = 3`

`lastIndex` becomes:
- `lastIndex = [0, 0, 0, 0, 0, 0, 3, 1, 0, 0]` (key digits have their last indices stored)

#### Step 2: Find the maximum swap:
- Start iterating over `s`:
  - At `i = 0`, `s[0] = '2'`:
    - The inner loop starts with `d = 9` down to `3` (checking for larger digits than `'2'`).
    - Found: `d = 7`, and `lastIndex[7] = 1` which is greater than `i`.
    - Swap `s[0]` and `s[1]`: 
      - New `s = ['7', '2', '3', '6']`
      - Return `7236`.

So the result of the dry run for input `num = 2736` is `7236`.
