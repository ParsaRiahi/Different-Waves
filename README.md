# Different-Waved
Sine, Saw, Square and Triangle waves

#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <math.h>


void printArray (float array[], int size)
{
    int j;
    for(j = 0; j < size; j = j + 1)
    {
        printf("at %d array is %.3f \n", j, array[j]);    
    }
}

int main(void)
{
    int size;
    int i;
    float *array;

    printf("\nenter the size of the array\n");
    scanf("%d",&size);

    array = malloc(sizeof(int) * size);

    srand(time(0));

    for(i = 0; i < size; i = i + 1)
    {
        array[i] = sin(i * 2 * M_PI / size);
    }
    printf("Sine Osc\n");
    printArray(array, size);

    
    for(i = 0; i < size; i = i + 1)
    {
        array[i] = 2.0 * (i / (float)size) - 1.0;
    }
    printf("Saw Osc\n");
    printArray(array, size);

    for(i = 0; i < size; i = i + 1)
    {
        if(i < (size / 2))
        {
        array[i] = 1.0;
        }
        else
        {
            array[i] = -1.0;
        }
    }
    printf("Square Osc\n");
    printArray(array, size);  

    for (int i = 0; i < size; i = i + 1) 
    {
    array[i] = 2.0 * fabs((i / (float)size) - 0.5) - 1.0;
    }
    printf("Triangle Osc\n");
    printArray(array, size); 

    free(array);
    return 0;
}
