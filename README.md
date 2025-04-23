#include <stdio.h>

int main() {
    int size = 3;
    int A[size][size], B[size][size];
    int sum[size][size], diff[size][size], product[size][size];
    float division[size][size]; // Using float for division

    // Input Matrix A
    printf("Enter elements of Matrix A (%dx%d):\n", size, size);
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            printf("A[%d][%d]: ", i, j);
            scanf("%d", &A[i][j]);
        }
    }

    // Input Matrix B
    printf("Enter elements of Matrix B (%dx%d):\n", size, size);
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            printf("B[%d][%d]: ", i, j);
            scanf("%d", &B[i][j]);
        }
    }

    // Matrix Addition, Subtraction, Element-wise Division
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            sum[i][j] = A[i][j] + B[i][j];
            diff[i][j] = A[i][j] - B[i][j];
            if (B[i][j] != 0)
                division[i][j] = (float)A[i][j] / B[i][j];
            else
                division[i][j] = 0.0; // Handle division by zero
        }
    }

    // Matrix Multiplication
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            product[i][j] = 0;
            for (int k = 0; k < size; k++) {
                product[i][j] += A[i][k] * B[k][j];
            }
        }
    }

    // Print Results
    printf("\nSum of A and B:\n");
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++)
            printf("%4d", sum[i][j]);
        printf("\n");
    }

    printf("\nDifference of A and B:\n");
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++)
            printf("%4d", diff[i][j]);
        printf("\n");
    }

    printf("\nProduct of A and B:\n");
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++)
            printf("%4d", product[i][j]);
        printf("\n");
    }

    printf("\nElement-wise Division of A by B:\n");
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++)
            printf("%6.2f", division[i][j]);
        printf("\n");
    }

    return 0;
}
