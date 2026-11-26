#include <stdio.h>

int main() {
    int choice, id;
    int available = 1;

    do {
        printf("\n===== LIBRARY MANAGEMENT =====");
        printf("\n1. Add Book");
        printf("\n2. Display Book");
        printf("\n3. Issue Book");
        printf("\n4. Return Book");
        printf("\n5. Exit");

        printf("\nEnter your choice: ");
        scanf("%d", &choice);

        switch(choice) {

            case 1:
                printf("Enter Book ID: ");
                scanf("%d", &id);
                printf("Book Added Successfully!\n");
                break;

            case 2:
                printf("Book ID: %d\n", id);
                if(available == 1)
                    printf("Status: Available\n");
                else
                    printf("Status: Issued\n");
                break;

            case 3:
                if(available == 1) {
                    available = 0;
                    printf("Book Issued Successfully!\n");
                }
                else {
                    printf("Book Already Issued!\n");
                }
                break;

            case 4:
                available = 1;
                printf("Book Returned Successfully!\n");
                break;

            case 5:
                printf("Thank You!\n");
                break;

            default:
                printf("Invalid Choice!\n");
        }

    } while(choice != 5);

    return 0;
}
