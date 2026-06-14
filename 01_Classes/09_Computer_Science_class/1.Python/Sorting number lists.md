# Example of sorting
```python
def bubble_sort_with_counts(original_list):
    """
    Sorts a copy of the list using Bubble Sort.
    Tracks and returns the total number of swaps.
    """
    # Create a new list copy to avoid modifying the original list
    arr = list(original_list)
    n = len(arr)
    swap_count = 0
    
    # Traverse through all array elements
    for i in range(n):
        # Last i elements are already in place
        for j in range(0, n - i - 1):
            # Swap if the element found is greater than the next element
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swap_count += 1
                
    return arr, swap_count


def insertion_sort_with_counts(original_list):
    """
    Sorts a copy of the list using Insertion Sort.
    Tracks and returns the total number of shifts (element movements).
    """
    # Create a new list copy to avoid modifying the original list
    arr = list(original_list)
    shift_count = 0
    
    # Traverse from 1 to len(arr)
    for i in range(1, len(arr)):
        key = arr[i]
        
        # Move elements of arr[0..i-1] that are greater than key
        # to one position ahead of their current position
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            shift_count += 1
            j -= 1
            
        # Place the key into its correct position
        arr[j + 1] = key
        
    return arr, shift_count


# Example Usage
if __name__ == "__main__":
    test_list = [29, 10, 14, 37, 13]
    
    print(f"Original List: {test_list}\n")
    
    # Run Bubble Sort
    bubble_sorted, total_swaps = bubble_sort_with_counts(test_list)
    print("--- Bubble Sort Results ---")
    print(f"New Sorted List: {bubble_sorted}")
    print(f"Total Bubble Swaps: {total_swaps}\n")
    
    # Run Insertion Sort
    insertion_sorted, total_shifts = insertion_sort_with_counts(test_list)
    print("--- Insertion Sort Results ---")
    print(f"New Sorted List: {insertion_sorted}")
    print(f"Total Insertion Shifts: {total_shifts}\n")
    
    # Verification that the original list stayed unchanged
    print(f"Verified Original List is Untouched: {test_list}")

```