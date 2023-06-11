#include <stdio.h>
#include <stdlib.h>
#include <omp.h>
#define MAX_SIZE 100000
void merge(int arr[], int left[], int right[], int left_size, int right_size) {
    int i, j, k;
    i = j = k = 0;
    while(i < left_size && j < right_size) {
        if (left[i] <= right[j]) {
            arr[k] = left[i];
            i++;
        }
        else {
            arr[k] = right[j];
            j++;
        }
        k++;
    }

    while (i < left_size) {
        arr[k] = left[i];
        i++;
        k++;
    }

    while (j < right_size) {
        arr[k] = right[j];
        j++;
        k++;
    }
}

void merge_sort(int arr[], int size) {
    if (size <= 1) {
        return;
    }

    int mid = size / 2;
    int left[mid], right[size - mid];

    #pragma omp parallel sections
    {
        #pragma omp section
        {
            for (int i = 0; i < mid; i++) {
                left[i] = arr[i];
            }
            merge_sort(left, mid);
        }

        #pragma omp section
        {
            for (int i = mid; i < size; i++) {
                right[i - mid] = arr[i];
            }
            merge_sort(right, size - mid);
        }
    }

    merge(arr, left, right, mid, size - mid);
}

int main() {
    int arr[MAX_SIZE];
    int size;

    printf("Enter number of elements: ");
    scanf("%d", &size);

    printf("Enter %d integers:\n", size);
    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }

    double start = omp_get_wtime();

    merge_sort(arr, size);

    double end = omp_get_wtime();

    printf("Sorted array:\n");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    printf("Time taken: %f seconds\n", end - start);

    return 0;
}
