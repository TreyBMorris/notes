# Sorting Algorithms

## Bubble Sort
Bubble sort is a sorting algorithm, where the algorithm iterates through a list of numbers, comparing each number to the next number, and swap them accordingly. Python and Java Examples below. The complexity of bubble sort is O(n<sup>2</sup>).
```Python
def bubbleSort(unsorted_list):
    list_length = len(list_to_sort)
    for i in range(list_length):
        for j in range(list_length):
            if list_to_sort[j]>list_to_sort[j+1]:
                list_to_sort[j], list_to_sort[j+1] = list_to_sort[j + 1], list_to_sort[j]
    return list_to_sort

```
```Java
public static void bubbleSort(int arr[], int n)
{
    int i, j, temp;
    boolean numbersSwapped;
    for(i = 0; i < n-1; i++)
    {
        numbersSwapped = false;
        for(j = 0; j < n - i - 1; j++)
        {
            if(arr[j]>arr[j + 1])
            {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
                numbersSwapped = true;
            }
        }
        if(numbersSwapped == false)
        {
            break;
        }
    }
}
```

## Merge Sort
Merge sort is a sorting algorithm that is recursive and splits a given data set in half until one or more lists containing one piece of data, then merges them back together. 

## Quick Sort
Quick sort is a sorting algorithm that is recursive. Quick sort works by using a pivot, low, and high pointer in the list. The pivot is then sorted into the list and the list breaks into smaller lists and continues until the entire list is sorted.

## Radix Sort
Radix sort is a sort algorithm that compares elements using their keys. We assume the keys are in the range from 0 to N-1. We would need N buckets labeled from 0 to N-1. The elements are sorted into their respective buckets with the same key value.

