1. compiler make the .obj file, for each .cpp file, and the linker bind these
  file together, and makes the .exe or .dll file.

2. we can make the preprocess file, to see the input of the file, 
  for example we can see #if statement, #include statement, #define statement

3. In visual studio, we have Solution configuration(release and debug) and Solution plattform
  (86x or 64x)

4. If you right click on your project in the solution explorer, you can go to properties:
    [ATTENTION] 
      in the window make sure to choose the right Configuration and plattform
    
    in the window in Configuration properties/ General we can change the Configuration type
    from Application(.exe) to other things like Dynamic Library(.dll) or Static library(.lib)

5. The compiler settings are located in C++ tab of the properties of the project,

6. Each cpp files get compiled to .obj file, header files don't compile, when we compile 
  each file, then the linker, links all the .obj files, and for example makes the .exe file

7. In visual studio we can compile each file with ctrl + f7 (header files don't get 
  compiled, just cpp files get compiled)

8. in properties window of the project in C/c++ tab in preprocessor section, we can 
enable making the preprocess file. (it make .i file)

9. In c/c++ in Output Files, we can set the Assembler Output.

10. To make the code optimize in Debug mode, you also have to in Code Generation tab 
  makes the Basic Runtime Checks to Default.

11. in Configuration properties in General tab, if we choose Configuration type to 
  the .exe file, we should know that every .exe file needs an entry point(
    in linker in advanced tab)

12. The only difference between type of variables is the size of them 

13. You can use #pragma once in order to use .h files only once

14. When you run your program in DEBUG MODE you can set break points in the visual 
  studio, and your able to run three options: step into, step over, step out...
  and there are three windows to check your memory: Authos, Local, Watch

15. You can all memory in debug menu, in window tab in memory one, and you can find the 
  varibale by checking its address (&a)


[ATTENTION]
16. Every to digit in hexidecimal format in  memory window is byte

[Very important]
17. if We set breakpoint in the program, we can right click in a line, and go to 
    View Disassembly, in this section, you can see the assembly code beside your code

18. In visual studio, we can make filters in our project, filters are just like folders
  but they are not actually folders, they are just the representation of the folders

19. You can change the Directory of your Output files and intermediate files: 
    in properties window of the project, and in Configuration properties tab, 
    
    Output Directory: $(SolutionDir)bin\$(Platform)\$(Configuration)\
    Intermediate Directory: $(SolutionDir)bin\intermediates\$(Platform)\$(Configuration)

20. pointer is just a memory that stores the address of the variables, types are meaningless
    just help to the compiler:

    int var = 5;
    int* ptr = &var;

  to access the data in we use *ptr
    *ptr = 9;
  
  we can have pointer to pointer, and store the address of pointer, because of after all 
    pointers are variables:

    int** newPtr = &ptr;

21. References in c++:

    int& ref = a;      //// ref is not a varibale and it is not going to store in memory
                        // it is just the alias of the variable

[ATTENTION]
int*   or  int&   is some how like we are defining new type, and this type is 
    pointer and reference

22. making a classes :

  class Player
  {
  public:
    int x, y;
    int speed;
    void Move(int xa, int ya)
    {
      x += xa * speed;
      y += ya * speed;
    }
  };

  int main()
  {
    Player player;
    player.x = 5;
  }

23. We normally use struct for the simple data structures, and there is no difference 
  between struct and class, just the semantic difference that is inside the programmer 
  style.

24. Static has three meaning, when we use it inside of the class or structs, when we use it 
    outside of the class or structs, and static in local scope:

      a. outside of class or struct:

            static means it only belongs to the translation unit, not other files.

      b. inside of the class or struct:

            The static variable are in the shared memory that is shared between all the 
            instances, and in static functions, we can't use the data, or methods that 
            belongs to one instance, so we can only use static data, or functions

      c. static local variable: 

            static local variables are the varibales that are local to the scope, and 
            it has the life time of the whole program. 

            for example making the singleton, first make the constructor private:
            The first time the method runs, make the instance, and other times, just return
            this instance;

            class Singleton {
              static Singleton& Get()
              {
                static Singleton instance;
                return instance;
              }
            };

25. Enums:
    /// Remember, Example is just an integer, and in c++ the Example is not a namespace
    // for example, by defining this enum, we define 3 integer:
    // and we can use it just like 4 > A

      enum Example
      {
        A, B, C
      }

26. Constructor: 

[ATTENTION] If we want to use the properties of the class outside the class and we don't 
            initialize them, we're going to get an error.

