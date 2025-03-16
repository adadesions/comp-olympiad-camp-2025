# Sequential Search (Linear Search)

## Concept

Sequential search is the simplest search algorithm that checks each element of a collection one by one until the target element is found or the collection ends.

## Algorithm

```cpp
#include <iostream>
#include <vector>

// Returns index of target if found, otherwise -1
int sequentialSearch(const std::vector<int>& arr, int target) {
    for (int i = 0; i < arr.size(); i++) {
        if (arr[i] == target) {
            return i;  // Return index if found
        }
    }
    return -1;  // Return -1 if not found
}

int main() {
    std::vector<int> arr = {5, 9, 3, 7, 2, 8};
    int target = 7;
    int result = sequentialSearch(arr, target);
    
    if (result != -1) {
        std::cout << "Element found at index " << result << std::endl;
    } else {
        std::cout << "Element not found in array" << std::endl;
    }
    
    return 0;
}