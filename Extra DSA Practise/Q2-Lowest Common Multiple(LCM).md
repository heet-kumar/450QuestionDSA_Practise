# Least Common Multiple (LCM)

You are given an array of positive integers, arr, of size array_length. You are asked to build set Swhich consists of LCMof every pair of adjacent elements in arr. Your task is to find largest element in set S.
For Example, for the array {1,2,3,4} set S = { lcm(1,2),lcm(2,3),lcm(3,4) } = {2,6,12}. The largest element is 12.

**Note :**
- The array only contains positive integers.
- Adjacent element may not be circular, i.e. they may not wrap around the end of the array.

## Input format:
- The first line of the array donate the size of the array.
- next line contains the space seperated integers denoting the value of the array.

## Output format:
- The output contains an integer denoting the largest element the set S as specified in the problem.

## Code Constraints
- 4 <= array_length <=10^5
- 1 <= arra[i] <= 1500

## Example 1:
- Input:
  - 4
  - 1,3,2,4
- Output: 6
- Explaination: 
   - Set S = {lcm(1,3),lcm(3,2),lcm(2,4)} = {3,6,4}
   - Largest Element = 6

## Example 2:
- Input:
  - 5
  - 7,3,2,9,12
- Output: 36
- Explaination: 
   - Set S = {lcm(7,3),lcm(3,2),lcm(2,9),lcm(9,12)} = {21,6,18,36}
   - Largest Element = 36
