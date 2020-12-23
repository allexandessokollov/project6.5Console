//---------------------------------------------------------------------------

#pragma hdrstop

//---------------------------------------------------------------------------
#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#pragma argsused


const int MAX_MATRIX_SIZE = 7;
int const MAX_RANDOM_VALUE = 20;


void fillMatrixKeyboard(int *arr[], int nSize, int mSize);
void fillMatrixRandomly(int *arr[], int nSize, int mSize);
int findQuantutyOfElem(int *arr[], int nSize, int mSize);


int main(){

    int nMatrixSize, mMatrixSize, choice;


    do{
        printf("Enter matrix size N x M\n");
        printf("N and M should be more than 0 and less than %d!\n", MAX_MATRIX_SIZE);

        scanf("%d %d", &nMatrixSize, &mMatrixSize);

    } while (nMatrixSize < 0 ||
      mMatrixSize < 0 ||
      nMatrixSize > MAX_MATRIX_SIZE ||
      mMatrixSize > MAX_MATRIX_SIZE);

    int **matrix = new int*[nMatrixSize];

    for(int i = 0; i < nMatrixSize; i++){

        matrix[i] = new int[mMatrixSize];
    }

    printf("Enter 1 to fill array using keyboard and 2 for random\n");
    scanf("%d", &choice);

    switch(choice){
        case 1:
            fillMatrixKeyboard(matrix, nMatrixSize, mMatrixSize);
            break;
        case 2:
            fillMatrixRandomly(matrix, nMatrixSize, mMatrixSize);
            break;
    }

    for(int i = 0; i < nMatrixSize; i++){

        for(int j = 0; j < mMatrixSize; j++){

            printf("%d  ", matrix[i][j]);
        }
        printf("\n");
    }

    printf("answer is: %d", findQuantutyOfElem(matrix, nMatrixSize, mMatrixSize));


    puts("\n\n\nPress any key ... ");
    getch();
    getch();


    for(int i = 0; i < mMatrixSize; i++)
    {
        delete []matrix[i];
    }
    delete []matrix;

    return 0;
}
//---------------------------------------------------------------------------

void fillMatrixKeyboard(int *arr[], int nSize, int mSize){

    for(int i = 0; i < nSize; i++){

        for(int j = 0; j < mSize; j++){
            printf("Enter element %d %d \n", i, j);
            scanf("%d", &arr[i][j]);
        }
    }

}


void fillMatrixRandomly(int *arr[], int nSize, int mSize){

    for(int i = 0; i < nSize; i++) {

        for(int j = 0; j < mSize; j++){
            arr[i][j] = random(MAX_RANDOM_VALUE);
        }
    }
}

int findQuantutyOfElem(int *arr[], int nSize, int mSize){

    int counter = 0;

    for(int i = 0; i < nSize; i++){

        for(int j = 1; j < mSize - 1; j++){

            if(arr[i][j] < arr[i][j - 1] && arr[i][j] < arr[i][j + 1]){
                counter++;
            }
         }

    }

    return counter;
}
