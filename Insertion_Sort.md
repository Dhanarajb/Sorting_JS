### Insertion Sort
> Insertion Sort is a simple comparison-based sorting algorithm. It works by dividing the input array into two parts: the sorted part and the unsorted part. In each iteration, the algorithm takes one element from the unsorted part and inserts it into its correct position in the sorted part.

#### Here’s how it works:
  - **Divide the array:** Similar to selection sort, we divide the array into two parts: sorted and unsorted.
  - **Insertion:** In each pass, we take an element from the unsorted part and insert it into its correct position in the sorted part.
  - **Shift:** As we find the correct position for the element in the sorted part, we may need to shift elements to make space for the new element.
  - **Repeat:** We repeat this process until the entire array is sorted.

<img width="555" alt="image" src="https://github.com/Dhanarajb/Sorting_JS/assets/88299676/c669ef8a-d4bc-405a-b7e8-cc2e3bc3f535">

```
Insertion Sort requires \(N-1\) passes. 
Total Comparisons are \((N-1) \times N / 2 = O(n²)\) in every case. 
Total Swaps are \(N-1\) in every case. Its time complexity is \(O(n²)\) because comparisons are always \(n²\). 
Insertion Sort's specialty lies in its efficient number of swaps, which is \(N-1\) in every case.
```
```
function insertionSort(arr) {
    const n = arr.length;

    for (let i = 1; i < n; i++) {
        let current = arr[i];
        let j = i - 1;

        while (j >= 0 && arr[j] > current) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = current;
    }

    return arr;
}

// Test cases
const testCases = [
    [],
    [1],
    [3, 2, 1],
    [5, 3, 8, 6, 2, 7, 4],
    [10, 20, 15, 25, 30],
    [1, 2, 3, 4, 5],
    [5, 4, 3, 2, 1]
];

console.log("Test Cases:");
testCases.forEach((arr, index) => {
    console.log(`Test Case ${index + 1}:`);
    console.log("Original array:", arr);
    console.log("Sorted array:", insertionSort(arr.slice())); 
});
```
```
DRY RUN

Input Array: [5, 2, 4, 6, 1, 3]

Pass 1:
Sorted Part: [5], Unsorted Part: [2, 4, 6, 1, 3]
Insert 2 into the sorted part: [2, 5]
Result: [2, 5, 4, 6, 1, 3]

Pass 2:
Sorted Part: [2, 5], Unsorted Part: [4, 6, 1, 3]
Insert 4 into the sorted part: [2, 4, 5]
Result: [2, 4, 5, 6, 1, 3]

Pass 3:
Sorted Part: [2, 4, 5], Unsorted Part: [6, 1, 3]
Insert 6 into the sorted part: [2, 4, 5, 6]
Result: [2, 4, 5, 6, 1, 3]

Pass 4:
Sorted Part: [2, 4, 5, 6], Unsorted Part: [1, 3]
Insert 1 into the sorted part: [1, 2, 4, 5, 6]
Result: [1, 2, 4, 5, 6, 3]

Pass 5:
Sorted Part: [1, 2, 4, 5, 6], Unsorted Part: [3]
Insert 3 into the sorted part: [1, 2, 3, 4, 5, 6]
Result: [1, 2, 3, 4, 5, 6]


Sorted Array: [1, 2, 3, 4, 5, 6]
```
