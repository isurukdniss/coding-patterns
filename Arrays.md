## Merge Two Sorted Arrays

### Approach

- Use three pointers

### Implementation

```csharp
public int[] MergeSortedArrays(int[] nums1, int[] nums2)
{
    // Calculate the total length of the merged array
    int totalLength = nums1.Length + nums2.Length;
    // Create an array to store the merged elements
    int[] merged = new int[totalLength];
    // Pointers for nums1, nums2, and merged array
    int i = 0, j = 0, k = 0;

    // Merge the arrays by comparing elements
    while (i < nums1.Length && j < nums2.Length)
    {
        if (nums1[i] < nums2[j])
        {
            // Take the smaller element from nums1 and add it to the merged array
            merged[k++] = nums1[i++];
        }
        else
        {
            // Take the smaller element from nums2 and add it to the merged array
            merged[k++] = nums2[j++];
        }
    }

    // Copy any remaining elements from nums1 to the merged array
    while (i < nums1.Length)
    {
        merged[k++] = nums1[i++];
    }

    // Copy any remaining elements from nums2 to the merged array
    while (j < nums2.Length)
    {
        merged[k++] = nums2[j++];
    }

    // Return the merged array
    return merged;
}

```

### Time and Space complexity

Time Complexity: `O(m+n)`
Space Complexity: `O(m+n)`
