# [905. Sort Array By Parity][LeetCode]

Given an array `A` of non-negative integers, return an array consisting of all the even elements of `A`, followed by all the odd elements of `A`.

You may return any answer array that satisfies this condition.

**Example 1:**

```
Input: [3,1,2,4]
Output: [2,4,3,1]
The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.
```


**Note:**

1. `1 <= A.length <= 5000`
2. `0 <= A[i] <= 5000`


## 思路


```
class Solution {
    public int[] sortArrayByParity(int[] A) {
        if(A.length == 1)
            return A;
        
        int even=-1, odd=A.length, cur=0;
        while (cur < odd) {
            if (A[cur] % 2 == 0) {
                even++;
                cur++;
            } else if (A[cur] % 2 == 1) {
                odd--;
                int temp = A[odd];
                A[odd] = A[cur];
                A[cur] = temp;
            }
        }
        return A;
    }
}
```


[LeetCode]: https://leetcode.com/problems/sort-array-by-parity/

