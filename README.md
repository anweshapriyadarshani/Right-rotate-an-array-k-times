# Right-rotate-an-array-k-times
Write a function that rotates a list by k elements. For example, [1, 2, 3, 4, 5, 6] rotated by two becomes [3, 4, 5, 6, 1, 2]. Try solving this without creating a copy of the list. How many swap or move operations do you need?

#include <stdio.h>
 
// Function to right-rotate an array by one position
void rightRotateByOne(int A[], int n)
{
    int last = A[n - 1];
    for (int i = n - 2; i >= 0; i--) {
        A[i + 1] = A[i];
    }
 
    A[0] = last;
}
 
// Function to right-rotate an array by `k` positions
void rightRotate(int A[], int k, int n)
{
    for (int i = 0; i < k; i++) {
        rightRotateByOne(A, n);
    }
}
 
int main(void)
{
    int A[] = { 1, 2, 3, 4, 5, 6, 7 };
    int k = 3;
 
    int n = sizeof(A)/sizeof(A[0]);
 
    rightRotate(A, k, n);
 
    for (int i = 0; i < n; i++) {
        printf("%d ", A[i]);
    }
 
    return 0;
}
