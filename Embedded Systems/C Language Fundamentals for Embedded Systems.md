>[!definition]
>Direct hardware access 
 Ability to manipulate memory addresses and registers

>[!definition]
>Static typing
>Compile time checking

>[!definition]
>Procedural Programming
>Function based code organization

>[!overview]
Core Philosophy of C
>1. **Simplicity** -- provide minimal features that can be easily understood
>2. **Efficiency** -- can be compiled to efficient machine code with minimal overhead 
>3. **Portability** -- can be compiled for different architectures with minimal changes
>4. **Low-Level Access** DMA (Direct memory access) and hardware features

>[!information]
>>[!Strengths]
>>
>>Performance
>>Control (DMA, hardware access)
>>Portability
>>Maturity well established language with extensive tooling
>
>>[!Limitations]
>>
>>Safety -- No built in memory safety or bounds checking
>>Complexity
>>Limited high level abstraction
>>Debugging

# Why do we use C

- Unix Heritage
- Compiler Technology
- Hardware Access
- Standardization (ANSI C)

- Minimal Runtime
- Predictable Performance
- Small code Size
- DMA
- Memory Usage
- CPU cycles
- Power Consumption
- Real-Time Capability

- Hardware Register Access
- Memory Mapped I/O
- Interput Handling
- DMA Programming
- Write Boot Code
- Device Drivers
- Time critical application development for real time systems
- Safety Critical systems because C is deterministic

# When is C used

>[!information]
>>[!Use]
>>Resource Constraints
>>Real time requirements
>>Hardware Access
>>Legacy Systems
>>Performance Critical
>
>>[!Alternatives]
>>Rapid Prototyping
>>Safety Critical -- Built in safety features required since C lacks those
>>Complex Abstractions needed
>>Team Productivity

# Concepts

>[!information]
>C is a procedural programming language
>
>1. Function Based -- Code is organized into functions
>2. Top down design -- Programs are designed from high level to low level
>3. Data and code separation -- Data structures are separate from functions
>4. Sequential execution

C uses a static memory model with manual memory management

```C Memory Layout:
┌─────────────────────────────────────────────────────────────┐
│                    Stack (Local Variables)                  │
│                    ↓ Grows downward                         │
├─────────────────────────────────────────────────────────────┤
│                    Heap (Dynamic Memory)                    │
│                    ↑ Grows upward                           │
├─────────────────────────────────────────────────────────────┤
│                    .bss (Uninitialized Data)                │
├─────────────────────────────────────────────────────────────┤
│                    .data (Initialized Data)                 │
├─────────────────────────────────────────────────────────────┤
│                    .text (Code)                             │
└─────────────────────────────────────────────────────────────┘
```

C on embedded systems compiles into multiple object files (translation units) that the linker places into memory regions defined by a linker script

- A source + its headers $\to$ a translation unit $\to$ an object file
- The linker merges objects and libraries resolving external symbols
- The linker script maps sections (`.text`, `.rodata`, `.data`, `.bss`) into Flash/RAM

- map file is your truth for footprint and placement
- `static` at file scope gives internal linkage; keeps symbols local by default
- use sections/attributes only when you must control placement; prefer defaults first

Compilation Process:
```

┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   Source    │ →  │  Preprocess │ →  │   Compile   │ →  │    Link     │
│   Code      │    │   (Macros)  │    │  (Assembly) │    │ (Executable)│
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
```

C uses a static type system with weak typing

>[!definition]
>Static typing -- Types are checked at compile time
>Weak typing -- Implicit type conversions are allowed 
>Explicit casting -- Manual type conversion when needed
>Type safety -- Limited type safety compared to modern languages


# Scope and Lifetime

- File scope -- Variables declared outside functions
- Function scope -- Variables declared inside functions
- Block scope -- Variables declared inside code blocks
- Global scope -- Variables accessible throughout the program

Lifetime rules
- Automatic -- Local variables (stack based)
- Static -- Variables that persist throughout function calls
- Dynamic -- Manually allocated memory (heap-based)
- Global -- Variables that exist for the entire program

# Variables and Data types

>[!concept]
>Where does the object live and when does it die
>
>Rather than memorizing types, think in terms of storage duration and lifetime:
>Who owns the object, where is it placed in memory, when is it initialized/destroyed
>
>On MCU's these choices affect RAM usage, startup cost, determinism, and safety

>[!information]
>Why does this matter for embedded systems
>
>- Static objects may be zero initialized by the startup code and can live in Flash (if `const`) reducing ram
>- Automatic (stack) objects are fast and deterministic to allocate but are uninitialized by default
>- Dynamic (heap) objects increase flexibility but can hurt predictability and fragment memory

**Takeaways**
- Only static storage duration is guaranteed zero-init. Stack local are indeterminant until assigned
- `static` inside a function behaves like a global with function scope
- `const` data may reside in non-volatile memory; don't cast away `const` to write to it

>[!definition]
>What are variables
>
>Variables are named storage locations in memory that can hold data. In C, variables must be declared before use, specifying their type and optionally initializing them with a value

>[!concept]
>Declaration vs Definiton
>
>- Declaration -- Tells the compiler about a variable's type and name
>- Definition -- Actually allocates memory for the variable 
>- Initialization -- Assigns an initial value to the variable

>[!concept]
>Variable attributes
>
>- Type -- Determines the size and interpretation of data
>- Name -- Identifier used to access the variable
>- Value -- Data stored in the variable 
>- Address -- Memory location where variable is stored

## Data type categories

Integer types:
- Signed -- Can represent negative and positive values
- Unsigned -- Can only represent positive values
- Size variants -- Different bit widths for different ranges

Floating point types:
- Singles precision -- 32-bit floating point numbers
- Double precision -- 64-bit floating point numbers
- IEEE 754 -- Standard format for floating point representation

Character types:
- char -- Usually 8-bit character or small integer
- Character Encoding -- ACII, UTF-8, or other encodings
- String representation -- Arrays of characters
## Variable declaration and initialization

Best practices
``` c
// ✅ Good: Explicit initialization
uint32_t counter = 0;
uint8_t status = 0xFF;
float temperature = 25.5f;

// ❌ Bad: Uninitialized variables
uint32_t counter;  // Contains garbage data
```

Constants

``` C
// Compile-time constants 

#define MAX_BUFFER_SIZE 1024
#define PI 3.14159f

// Runtime constants
const uint32_t TIMEOUT_MS = 5000;
const float VOLTAGE_REFERENCE = 3.3f;

// Enum constants
typedef enum {
    LED_OFF = 0,
    LED_ON = 1,
    LED_BLINK = 2
} led_state_t;
```

# Functions

>[!concept]
>Keep work small, pure when possible and observable
>
>In embedded, function design drives predictability and testability
>Prefer small, single purpose functions with explicit inputs/outputs. Avoid hidden dependencies (globals) except for well defined hardware interfaces behind an abstraction

**Why it matters**
- Smaller functions improve stack usage estimation and inlining opportunities
- Pure functions are easier to unit test off-target
- Explicit interfaces reduce coupling to hardware and timing

**Takeaways**
- Separate policy from mechanism for testability and reuse
- Minimize global state; pass data via parameters and return values
- Consider `static inline` for very small helper functions

>[!definition]
>Function
>
>Functions are reusable blocks of code that preform specific tasks. They are the primary mechanism for code organization and reuse in C programming

>[!concept]
>Function components
>
>- Declaration -- Function prototype (signature)
>- Definition -- Function implementation (body)
>- Parameters -- Input data passed to the function
>- Return Value -- Output data returned from the function
>- Scope -- Variables and code accessible within functions

>[!concept]
>Function Types
>
>- Library functions -- built in functions (printf, malloc, ...)
>- User-defined functions -- Functions written by the programmer
>- Main function -- Entry point of the program
>- Callback function -- Functions passed as parameters

**How should we design functions**
- Single responsibility
	- Each function should do one thing
	- Functions should be focused and cohesive
- Parameters
	- Use parameters for input and returns for output
	- Avoid global variables
- Error handling
	- Return error codes for failure conditions
	- Use consistent error handling patterns
# Control Structures
>[!concept]
>Prefer early returns and shallow nesting
>
>Deep nesting can increase cyclomatic complexity and code size
>Early returns keep critical paths obvious and reduce stack pressure in error paths

- Shallow nesting improves readability and timing analysis
- Use switch for dense dispatch; avoid fall through unless deliberate and documented
- In ISR-adjacent code, keep branches short and avoid loops without clear bounds

>[!definition]
>What are control structures
>
>Control structures determine the flow of the program execution
>They allow programs to make decisions, repeat operations, and organize code execution

__Decision Making__
- Conditional Execution -- Execute code based on conditions
- Boolean Logic -- True/False conditions for decisions
- Nested decisions -- Complex decision trees
- Default actions -- Fallback behaviour when conditions aren't met
Looping
- Iteration -- Repeating operations multiple times
- Loop control -- Starting, continuing, and stopping loops
- Loop variables -- Variables that control loop execution
- Infinite loops -- Loops that run indefinitely 
Flow control 
- Sequential execution -- Code executed in order 
- Branching -- Jumping to different sections of code
- Early exit -- Exiting branches or loops early
- Exception handling -- Managing error conditions

# Memory management

>[!definition]
>Memory management in C involves allocating, using and freeing memory recources
>Unlike higher level languages, C requires manual memory management giving programmers direct control but also responsibility for memory safety

Memory types
- Stack memory -- Automatic memory allocation for local variables
- Heap memory -- Manual memory allocation using malloc and free
- Static memory -- Global and static variables
- Constant memory -- Read only data and code
Memory Lifecycles
- Allocation -- Requesting memory from the system
- Usage -- Reading and writing to allocated memory 
- Deallocation -- Returning memory to the system
- Reuse -- Memory can be reallocated after deallocation
Memory safety
- Bounds checking -- Ensuring memory access is within allocated regions
- Use after free -- Accessing memory after its been freed
- Memory leaks -- Failing to free allocated memory
- Double free -- freeing the same memory twice

>[!concept]
>Stack vs Heap
>
>>[!definition]
>>Stack Memory
>>
>>Automatic allocation -- Variables allocated automatically
>>LIFO Order -- Last in First out allocation pattern
>>Fast Access -- Direct memory access
>>Limited size -- Stack size is typically small
>>Scope based Memory freed once scope ends
>
>>[!definition]
>>Heap memory
>>
>>Manual allocation -- Explicit allocation with malloc/calloc
>>Flexible size -- Can allocate large amounts of memory
>>Slower access -- Indirect memory access
>>Manual deallocation -- Must explicitly free memory
>>Fragmentation -- Can be fragmented over time

# Pointers

>[!definition]
>Pointers are variables that store memory addresses
>They provide indirect access to data and are fundamental to C programming, especially in embedded systems where direct memory manipulation is common

Address and value
- Address -- Memory location where data is stored
- Value -- Data stored at the memory location
- Pointer variable -- Variable that stores the address
- Dereferencing -- Accessing the value at the address
Pointer types
- Data pointers -- Point to variables and data structures
- Function pointers -- Point to functions
- Void pointers -- Generic pointers that can point to any type
- Null pointers -- Special pointer value indicating no address
Pointer arithmetic
- Increment/Decrement -- Move to next/previous memory location
- Addition/Subtraction -- Move by multiple memory locations
- Comparison -- Compare memory addresses
- Array relationship -- Arrays and pointers are closely related
**Function Pointers**
``` C
// Function pointer type
typedef void (*callback_t)(uint32_t);

// Function that takes a callback
void process_data(uint32_t data, callback_t callback) {
    // Process data
    if (callback != NULL) {
        callback(data);
    }
}

// Callback function
void data_handler(uint32_t data) {
    printf("Received: %u\n", data);
}

// Usage
process_data(42, data_handler);
```

# Arrays and Strings

>[!concept]
>Arrays are blocks; pointers are addresses with intent
>
>An array name in an expression decays to a pointer to its first element. The array itself has a fixed size and it lives where it was defined [[C Language Fundamentals for Embedded Systems#Concepts| Data]].
>A pointer is just an address that can point anywhere and can be restated

- Knowing when decay happens prevents bugs of `sizeof` and parameter passing
- Arrays placed in flash as a `static const` look like ordinary arrays but are read only and may require `volatile` when mapped to hardware

__Takeaways__
- Arrays are not pointers; they decay to pointers at most expression boundaries
- sizeof inside a function yields the size of the pointer
- Prefer passing `(ptr, length)` pairs, or wrap in struct to preserve size information

>[!definition]
>What are arrays?
>
>Arrays are collections of elements of the same type stored in contiguous memory locations
>They provide efficient access to multiple related data items

Array Characteristics
- Contiguous Memory -- Elements stored in adjacent memory locations
- Indexed Access -- Elements accessed by numeric index
- Fixed Size -- Size determined at declaration (in C)
- Type Homogeneity -- All elements must be the same type
Array Operations
- Traversal -- Accessing all elements in sequence
- Searching -- Finding specific elements
- Sorting -- Arranging elements in order
- Modification -- Changing element values
Array Limitations
- Fixed Size -- Cannot change size after declaration
- No Bounds Checking -- C doesn't check array bounds
- Memory Waste -- May allocate more memory than needed
- No built in operations -- No built in search, sort, etc

**String Concepts**

String Representation
- Null-terminated -- String ends with a `'\0'` char
- Character Arrays -- Strings are arrays of characters
- Length Calculation -- Must count characters to find length
- Memory Management -- Must allocate sufficient space
String Operations
- Concatenation -- Combining strings
- Comparison -- Comparing string contents
- Searching -- Finding substrings
- Copying -- Duplicating strings

# Structures and Unions

>[!definition]
>Structures are user defined data types that group related data items of different types into a single unit. They provide a way to organize complex data in embedded systems

Structure Components
- Members -- Individual data items in the structure
- Layout -- How members are arranged in memory
- Alignment -- Memory allocation requirements
- Size -- Total memory occupied by the structure
Structure Usage
- Data organization -- Group related data together
- Function parameters -- Pass multiple related values
- Return values -- Return multiple values from functions
- Memory mapping -- Map structures to hardware registers
Structure Design
- Cohesion -- Members should be logically related
- Size optimization -- Minimize memory usage
- Alignment -- Consider memory alignment issues

__Unions__

Characteristics
- Shared Memory -- All members share the same memory location
- Single Value -- Only one member can be active at a time
- Memory efficiency -- Uses only the size of the largest member
- Type Flexibility -- Can represent different data types
Applications
- Type conversions -- Convert between different data types
- Memory efficiency -- Save memory when only one type is needed
- Hardware access -- Access hardware registers in different ways
- Protocol implementation -- Handle different message types

# Preprocessor directives

Keep macros minimal and local. Prefer `static inline` functions for type safety, debug-ability and better compile analysis unless you truly need token pasting/stringification or compile time branching

>[!definition]
>What are preprocessor directives
>
>Preprocessor directives are instructions to the C preprocessor that are processed before compilation
>They provide text substitution, conditional compilation, and file inclusion capabilities

Text substitution
- Macros -- Text replacement before compilation
- Constants -- Define compile-time constants
- Function-like macros -- Macros that take parameters
- Stringification -- Convert parameters to strings
Conditional Compilation
- Platform-specific Code -- Different code for different platforms 
- Debug code -- Include debug code only in debug builds
- Feature flags -- Enable/Disable features at compile time
- Header Guards -- Prevent multiple inclusion of headers
File management
- Header Inclusion -- Include declarations from other files
- File organization -- Separate interface from implementation
- Dependency management -- Manage file dependencies
- Modular design -- Organize code into modules

# Best practices

## Code organization

- Modular design -- Break code into logical modules
- Function size -- Keep functions small and focus
- Naming conventions -- Use consistent naming 
- Documentation -- Document complex code sections

# Memory Management

- Initialization -- Always initialize variables
- Bounds checking -- Check array bounds
- Memory cleanup -- Free allocated memory
- Null pointers -- Check for NULL before dereferencing

# Error Handling

- Return values -- Use return values for error indication
- Error codes