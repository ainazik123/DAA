First Bad Version

1. Problem

Find the first bad version when all versions after it r also bad.

2. Approach

I use binary search.I check the middle version with `isBadVersion()`.If it is bad,I search the left half.If it is good,I search the right half.

3. Time Complexity:O(log n)

Each step removes about half of the remaining versions.

4. Space Complexity:O(1)

Only a few variables r used.

5. Reflection/Improvement

Binary search is already efficient.A linear search would take O(n),while this solution takes O(log n).
