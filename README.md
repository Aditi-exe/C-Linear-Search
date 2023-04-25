# Linear Search in C

Search algorithms are a set of rules or procedures used to find a specific item or information from a collection of data. In computer science and information retrieval, search algorithms are widely used in various applications such as search engines, databases, recommendation systems, and more.

There are several types of searching algorithms, some of which are listed below:
- Linear Search
- Binary Search
- Depth-First Search (DFS)
- Breadth-First Search (BFS)
- Dijkstra's Algorithm
- Binary Search Tree (BST)
- Hash Tables
- Greedy Algorithms
- Pattern Matching Algorithms
- Metaheuristic Algorithms


## Linear Search in more detail

Linear search is a simple search algorithm that sequentially checks each element in a collection of data until the target item is found or the end of the collection is reached. It has a time complexity of O(n), where n is the number of items in the collection. Linear search is commonly used for small collections or when the data is not sorted, but it may not be efficient for large collections as the search time grows linearly with the size of the collection. Linear search can be implemented using a loop or recursion, and it is easy to understand and implement, making it a basic and commonly used search algorithm.

If a key K = 8 is to be searched in an array, the following process will have to be followed:

![Working of linear search](https://utkarsh1504.github.io/DSA-Java/static/e3fa513b23c9d1e51f3c6f58ef6a9bfc/c1b63/linear-search.png)

An implementation of linear search in C using a function is given below:

```
#include <stdio.h>

// Function to perform linear search
int linearSearch(int arr[], int n, int key) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == key) {
            return i;  // Return the index of the key if found
        }
    }
    return -1;  // Return -1 if key not found
}

int main() {
    int arr[] = {12, 34, 45, 67, 78, 89, 90};
    int n = sizeof(arr) / sizeof(arr[0]);  // Size of the array
    int key = 67;  // Key to search for

    int index = linearSearch(arr, n, key);  // Call linearSearch function

    if (index != -1) {
        printf("Key %d found at index %d\n", key, index);
    } else {
        printf("Key %d not found in the array\n", key);
    }

    return 0;
}
```

In this example, the linearSearch function takes an integer array arr, its size n, and a key value to search for. It iterates through the array using a for loop and compares each element with the key value. If the key value is found, it returns the index of the key value. Otherwise, it returns -1 indicating that the key value was not found in the array.
The main function demonstrates how to use the linearSearch function by calling it with a sample array and key value, and then prints the result.

The program in this repository demonstrates the implementation of a linear search algorithm without using a separate function.

### Code:

```
// implementing linear search

#include <stdio.h>
#include <stdlib.h>

int main()
{
	int arr[10] = {39, 7, 40, 40, 40, 345, 76, 22, 39, 319};
	//int arr[10] = {rand(), rand(), rand(), rand(), rand(), rand(), rand(), rand(), rand(), rand()};

	int n;
	int count = 0;
	
	// array to store the indices at which the entered element is found (if it is found)
	int index[10] = {-1, -1, -1, -1, -1, -1, -1, -1, -1, -1};
	
	int i;
	
	printf("Enter a number: ");
	scanf("%d", &n);
	printf("\n");
	
	for(i = 0; i < 10; i++)
	{
		if(arr[i] == n)
		{
			index[i] = i;
			count++;
		}
	}
	
	if(count >= 1)
	{
		printf("Element found at index / indices: ");
		
		for(i = 0; i < 10; i++)
		{
			if(index[i] != -1)
			{
				printf("%d ", index[i]);
			}
		}
		printf("\n");
	}
	else
	{
		printf("Element not found.\n");
	}
	
	
	
	/*
	if(count >= 1)
	{
		printf("Element found at index: %d\n", index);
		//printf("Element found at %d indices.\n\n", count);
	}
	else
	{
		printf("Element not found.");
	}
	*/
	
	/*
	// finding the indices at which the element is found
	int *indices = (int*)calloc(count, sizeof(int));
	
	for(i = 0; i < 10; i++)
	{
		if(arr[i] == n)
		{
			indices[i] = i;
		}
	}
	
	printf("Indices at which the entered element was found: ");
	
	for(i = 0; i < 10; i++)
	{
		if(indices[i] >= 0 && indices[i] <= 9)
		{
			printf("%d ", indices[i]);			
		}
	}
	*/
	
	return 0;
	
}
```

### Output:

![linearSearch.c output](https://github.com/Aditi-exe/C-Linear-Search/blob/main/linearSearch1.PNG)


