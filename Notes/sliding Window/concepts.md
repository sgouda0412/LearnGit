sliding window problems -> fixed or variable size  [array and string] 
substring and subarray problem based on some conditions
finding subarrays with a specific sum, finding the longest substring with unique characters, or solving problems that require a fixed-size window to process elements efficiently
Finding Maximum/Minimum ****Subarray****, ****Substrings**** which satisfy some specific condition.


### Fixed size SWP
```python
def fixed_size_sliding_window(arr, k):
    # Check if the array length is less than the window size
    if len(arr) < k:
        return []

    # Initialize the result list
    result = []

    # Compute the result for the first window (first k elements)
    window_sum = sum(arr[:k])
    result.append(window_sum)

    # Use a loop to slide the window and compute the result for each window
    for i in range(k, len(arr)):
        # Slide the window by 1 element:
        # subtract the element that is going out of the window and add the element coming into the window
        window_sum += arr[i] - arr[i - k]
        result.append(window_sum)

    return result
-----------------------------------------------------------------
    def maximumSumSubarray (self,arr,k):
        # code here 
        if len(arr) < k:
            return []
        result = []
        window_sum = sum(arr[:k])
        result.append(window_sum)
        
        for i in range(k, len(arr)):
            window_sum += arr[i] - arr[i - k]
            result.append(window_sum)
        return max(result)
```


### Variable Sized SWP
