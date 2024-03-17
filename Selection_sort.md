### Selection Sort:
> Selection Sort is another Comparison based Sorting Algorithm.
> Imagine you have a bunch of numbers jumbled up, and you want to put them in order from smallest to largest using a method called selection sort.

#### Here's how it works:
  - You divide your bunch of numbers into two parts: sorted and unsorted.
  - In each pass, you look through the unsorted part to find the smallest number.
  - Once you find the smallest number, you swap it with the first number in the unsorted part.
  - Now, you consider the first number as sorted and move on to the next pass, starting from the second number in the unsorted part.
  - You keep doing this until the entire bunch is sorted.

<img width="559" alt="image" src="https://github.com/Dhanarajb/Sorting_JS/assets/88299676/03c3a2b5-f5b9-41c3-aaa3-f73eba9105ee">

```
Selection Sort Requires N-1 Passes.
Total Comparisons = ( (N-1) * N ) /2 = O(n2) { Every Case},
Total Swaps = N-1 { Every Case}
Time Complexity = O(n2) {because comparisons are always n2.}
Selection Sort speciality is No of swaps are N-1 in every case.
```
```
function selectionSort(arr) {
    const len = arr.length;
    
    for (let i = 0; i < len - 1; i++) {
        let minIndex = i;
        
        for (let j = i + 1; j < len; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        
        if (minIndex !== i) {
            [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
        }
    }
    
    return arr;
}

const array = [64, 25, 12, 22, 11];
console.log("Original Array: ", array);
console.log("Sorted Array: ", selectionSort(array));
```
DRY RUN
```
Initial Array: [64, 25, 12, 22, 11]

Pass 1:

Start with i = 0.
Find the minimum element from index i = 0 to end of the array.
Minimum element is 11 at index 4.
Swap arr[0] and arr[4].
Array becomes [11, 25, 12, 22, 64].

Pass 2:

Start with i = 1.
Find the minimum element from index i = 1 to end of the array.
Minimum element is 12 at index 2.
No need to swap as the minimum is already at arr[1].
Array remains [11, 12, 25, 22, 64].

Pass 3:

Start with i = 2.
Find the minimum element from index i = 2 to end of the array.
Minimum element is 22 at index 3.
No need to swap as the minimum is already at arr[2].
Array remains [11, 12, 22, 25, 64].

Pass 4:

Start with i = 3.
Find the minimum element from index i = 3 to end of the array.
Minimum element is 25 at index 3.
No need to swap as the minimum is already at arr[3].
Array remains [11, 12, 22, 25, 64].
Sorted Array: [11, 12, 22, 25, 64]
```
