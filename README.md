# LeetCode Questions & Algorithms

## LeetCode 238: Product of Array Except Self:
Sol) Left and Right Products 
     Left: [1,2,3,4] => [1,1,2,6]
     Right: [1,2,3,4] => [24,12,4,1]
     Output: Left * Right => [24,12,8,6]
     Note: Left Index, loop is 1 to 3(1,2,3) and Right Index, loop is 2 to 0(2,1,0)
## LeetCode 53: Maximum Sum Subarray:
Sol) Kadane's Algorithm
     Eg: [-2,1,-3,4,-1,2,1,-5,4]
     => loopCounter from 0 to i - 1
     => set max and current to index 0, "-2" in this case
     => current = current + arr[loopCounter + 1]
     => if current < arr[loopCounter + 1], then current equals arr[loopCounter + 1]
     => if max < current, max = current
## LeetCode 152: Maximum Product Subarray
Sol) Kadane's Algorithm with currMin and currMax
     => initialize max as nums[0] for single array cases
     => nums[i] = 1, then currMin and currMax = 1
     => currMax = max of(n * currMax, n * currMin, n)
     => currMin = min of(n * currMax, n * currMin, n), (Careful: should be of this iteration, take a tmp at the start for currMax)
     => max = max of(currMax, max)
## LeetCode 371: Sum of Two Integers without +/-
Sol) 
Algorithm by example:
     =>      1011 (11)
     => (xor)1001 (9)
     -----------------
     =>      0010 (new a value)
     =>           1011 (11)
     => (and << 1)1001 (9) [note: do and gate and shift 1]
     ---------------------
     =>          10010 (new b value)

     => Do the same operation again: a = a ^ b, b = (a & b) << 1, till b = 0. 
     => Answer: 10100(20) [Note: b-value becomes 0 if we don't have a carry, otherwise it changes]
     
## LeetCode 242: Valid Anagram
Sol) Algorithm:
     => Convert both to character arrays
     => Check if length is equal first, then
     => Sort them, and then check if each character is equal => arr[i] = arr1[i]
## LeetCode 153: Find Minimum in Rotated Sorted Array
Sol) Use Arrays.sort(nums) => return nums[0], [Note: Check how sort works]
## LeetCode 39: Search in Rotated Sorted Array
Sol) Do it normally, [Note: Check Merge Sort]
## LeetCode 11: Container With Most Water
Sol) Algorithm: Two Pointer Technique [Note: if equal, discard either height but be consistent]
     => [1,8,6,2,5,4,8,3,7] => Area = 1 * (pointer2 - pointer1) = 1 * 8 = 8
     => discard smaller height => Area = 7 * (pointer2 - pointer1) = 7 * 7 = **49**
     => discard smaller height => Area = 3 * (pointer2 - pointer1) = 3 * 6 = 18
     => discard smaller height => Area = 8 * (pointer2 - pointer1) = 8 * 5 = 40
     => discard smaller height => Area = 4 * (pointer2 - pointer1) = 4 * 4 = 16
     => discard smaller height => Area = 5 * (pointer2 - pointer1) = 5 * 3 = 15
     => discard smaller height => Area = 2 * (pointer2 - pointer1) = 2 * 2 = 4
     => discard smaller height => Area = 6 * (pointer2 - pointer1) = 6 * 1 = 6
     => 49 is the largest area
## LeetCode 15: 3sum:
Sol) Algorithm: Brute Force => Make three loops and check the sum for each elements 3 times. Continue the loop when indices are equal to one another.
Algorithm: Pointer technique
=> Go through every element by making a loop
=> Make a second loop and then select a left pointer
and a right pointer
=> Example: [-1,0,1,3,-1,-4]
=> Sort: [-4,-1,-1,-,1,3]
=> Select -1 first, then loop from index[1] to index[length]
=> if sum < 0 increase lp by 1
=> if sum > 0 decrease rp by 1
=> else append to list if already not in the list
=> return list
## LeetCode 268. Missing Number:
=> sort the array
=> if i does not equal to num[i], return i
=> else just return len(nums) => example [0,1] is [0,n] where n = 2.
=> since 2 is equal to len(nums)
=> Other solution: Sum of [0,n] - sum of array
=> One more solution: Using xor gate. T
=> 5 xor 5 = 0. Similarly, 5 xor 5 xor 3 = 3
## LeetCode 191. Number of 1 Bits:
=> Use the bin function to convert to a String
=> Use the count function to count the occurrences of '1'
=> To convert to Binary:
=> Example: 11 (Keep doing 11/2, 5/2 and so on)
=> 11 % 2 = 1
=> 5 % 2 = 1
=> 2 % 2 = 0
=> 1 % 2 = 1
=> Reverse the string to get: 1011
## LeetCode 338. Counting Bits:
=> Make an empty list
=> make an array using range (0, n + 1)
=> Count the number of 1s using the bin() function
=> Make sure to understand how bin function works
=> add the count of 1s to the empty list 
=> Return the list
## LeetCode 190. Reverse Bits:
=> Convert int to a string using "{:32b}".format(number)
=> Extra exercise: Do the 32 string thing as an exercise
=> Go from 0 to n indices
=> Use the binary formula
=> Example: 101 = 2^0 x 1 + 2^1 x 0 + 2^2 x 1 = 5
=> Since the count starts from the rightmost bit. Sum will be the number of the reversed bit