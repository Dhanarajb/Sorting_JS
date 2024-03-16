### Bubble Sort:
> Bubble Sort is a comparison based Sorting Algorithm.
  - It works by checking its adjacent element whether, it is in sorted order or not.
  - It is an Inplace Sorting algorithm as we don’t need any extra data structure while sorting.
  - It is stable (the sequence of repeating elements does not change).

<img width="784" alt="image" src="https://github.com/Dhanarajb/Sorting_JS/assets/88299676/fefede4f-3e85-4185-82a9-320e14246e7a">

```
No of Required Passes = (n-1)
Total Comparisons = (n-1) + (n-2) + (n-3) + .............1 = ( (n-1) * n )/2 = O(n2) { Every Case}
Total Swaps :
minimum = 0 {elements are in sorted order}

maximum = (n-1) + (n-2) + (n-3) + .............1 = ( (n-1) * n )/2 = O(n2)

Time Complexity = maximum(Comparison, Swaps)

= O(n2) {Every Case}

Space Complexity : O(1)

```

```
function bubbleSort(scores) {
    const n = scores.length;
    for (let i = 0; i < n - 1; i++) { 
        for (let j = 0; j < n - i - 1; j++) { 
            if (scores[j] > scores[j + 1]) {
                const temp = scores[j];
                scores[j] = scores[j + 1];
                scores[j + 1] = temp;
            }
        }
    }
}

const studentScores = [87, 65, 92, 78, 90, 82];
console.log("Original scores:", studentScores);

bubbleSort(studentScores);

console.log("Sorted scores:", studentScores);
```
