Stack is what you've been using all along. 
Every function gets its own pile, variables are made the normal way (int x = 5;), and they vanish automatically when the function ends. 
Downside: sizes are fixed at compile time (that's why NUM_HORSES had to be const static).
Heap is one big shared space for the whole program. 
You put something there with new, which hands back a pointer that lives on the stack: 
    int* p = new int; then *p = 5;. 
    Arrays work too: int* arr = new int[5];.
Anything you new you must delete before the pointer goes away: delete p; for a single thing, delete[] arr; for an array.
Forget it and you get a memory leak — the program still compiles and runs fine, which is what makes it sneaky.
valgrind --leak-check=full ./a.out finds leaks. 
Compile with -g first. "All heap blocks were freed" is what you want to see. 
He suggests adding a valgrind target to the makefile.


MEMORY MANAGEMENT
