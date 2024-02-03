#include <iostream>

int main() {
    // Declare variables to store user input
    int value1, value2, value3;

    // Get user input
    std::cout << "Enter three integer values: ";
    std::cin >> value1 >> value2 >> value3;

    // Create integer pointers and allocate dynamic memory with error checking
    int* ptr1 = new(std::nothrow) int(value1);
    int* ptr2 = new(std::nothrow) int(value2);
    int* ptr3 = new(std::nothrow) int(value3);

    // Check for memory allocation success
    if (!ptr1 || !ptr2 || !ptr3) {
        std::cerr << "Memory allocation failed. Exiting...\n";

        // Deallocate memory for successful allocations
        delete ptr1;
        delete ptr2;
        delete ptr3;

        return 1; // Indicate failure
    }

    // Display the contents of variables and pointers
    std::cout << "\nValues entered by the user:\n";
    std::cout << "Value 1: " << value1 << "\n";
    std::cout << "Value 2: " << value2 << "\n";
    std::cout << "Value 3: " << value3 << "\n";

    std::cout << "\nContents of pointers:\n";
    std::cout << "Pointer 1: " << *ptr1 << "\n";
    std::cout << "Pointer 2: " << *ptr2 << "\n";
    std::cout << "Pointer 3: " << *ptr3 << "\n";

    // Deallocate memory using delete operator
    delete ptr1;
    delete ptr2;
    delete ptr3;

    return 0;
}
