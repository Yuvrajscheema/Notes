
>[!concept]
>A [[C Language Fundamentals for Embedded Systems#Pointers| pointer]] is just an address; correctness depends on the lifetime and effective type of the object it points to. Hardware access requires `volatile`; high-performance memory access benefits from no-aliasing assumptions

- Use volatile for memory mapped registers and ISR shared flags
- Be mindful of strict aliasing; stick to the same effective type or `memcpy`
- Prefer `restrict` only when you can prove non-aliasing

>[!definition]
>- Direct memory access -- Hardware register manipulation
>- Efficient data structures -- Lined lists, trees, graphs
>- Function callbacks -- Event-driven programming
>- Memory safety -- Preventing pointer related bugs

# What are pointers

>[!definition]
>Pointers are variables that store memory addresses 
>They provide indirect access to data stored in memory allowing programs to manipulate memory locations directly
>Pointers are essential for hardware access, dynamic memory management and efficient data structures

Address and Value
- Address -- A unique number that identifies a memory location
- Value -- The data stored at a specific memory address
- Pointer variable -- A variable that stores a memory address

## Characteristics

Indirect access
- Pointers can provide indirect access to data
- They can be modified to point to different memory locations
- They can enable dynamic memory allocation and deallocation
- They allow efficient passing of large data structures

Type safety
- Pointers have types that indicate what they point to
- Type checking helps prevent programming errors
- Void pointers provide generic pointer functionality
- Type casting allows conversion between pointer types

Memory management
- Pointers enable dynamic memory allocation
- They can cause memory leaks if not properly managed
- They require careful bounds checking
- They can lead to segmentation faults if misused

# Why are pointers important

Hardware access
- Register manipulation -- Direct access to hardware registers
- Memory mapped I/O -- Access to peripheral devices
- DMA programming -- Direct memory access  operations
- Interrupt handling -- Low-level interrupt service routines

Performance benefits
- Efficient data passing -- Pass large structures by reference
- Dynamic memory -- Allocate memory as needed
- Data structures -- Implement linked lists, trees, graphs
- Function callbacks -- Enable event driven programming

System control
- Boot code -- System initialization and startup
- Device drivers -- Hardware abstraction layer
- Real-time systems -- Time critical operations
- Safety critical systems -- Deterministic behaviour

When to use pointers
- Hardware access -- Need to access hardware registers
- Dynamic memory -- Memory requirements vary at runtime
- Large data -- Need to pass large structures efficiently 
- Data structures -- Implementing complex data structures
- Function callbacks -- Event driven programming

When not to use pointers
- Simple data -- Small simple data types
- Safety critical -- Where pointer errors are unacceptable
- Beginner code -- When learning basic concepts
- High-level abstractions -- When using higher level language

### **Applications**

Hardware register Access
``` c
// Access GPIO registers
// Use 'volatile' on memory-mapped registers so reads/writes are not optimized away
volatile uint32_t* const GPIOA_ODR = (volatile uint32_t*)0x40020014;
*GPIOA_ODR |= (1 << 5);  // Set bit 5
```

Dynamic data structures
```c
// Linked list node
typedef struct node {
    int data;
    struct node* next;
} node_t;
```

Function callbacks
```c
// Event handler system
typedef void (*event_handler_t)(uint32_t event);
event_handler_t handlers[MAX_EVENTS];
```


## Pointer types and use

__Data pointers__

Basic data pointers

- Point to variables and data structures
- Have specific types matching the data they point to
- Enable efficient data manipulation
- Support pointer arithmetic 

Const pointers

- Pointer to const -- Pointer to data that cannot be modified
- Const pointer -- Pointer that cannot be changed to point elsewhere
- Const pointer to const -- Neither pointer nor data can be modified

```c
// Pointer to const data
const int* ptr1;           // Can't modify *ptr1
int const* ptr2;           // Same as ptr1

// Const pointer
int* const ptr3;           // Can't modify ptr3

// Const pointer to const data
const int* const ptr4;     // Can't modify ptr4 or *ptr4
```

**Function pointers**

- Point to functions rather than data
- Enable callback mechanisms
- Support event driven programming
- Allow dynamic function selection

Function pointer types
- Simple function pointers -- Point to functions with specific signatures
- Callback function pointers -- Used for event handling
- Method pointers -- Point to object methods (C++)
- Generic function pointers -- Use void pointers for parameters
## Void pointers

Characteristics
- Generic pointers that can point to any data type
- Cannot be dereferenced directly
- Must be cast to specific type before use
- Useful for generic data structures

Uses
- Generic functions -- Functions that work with any data type
- Memory allocation -- malloc returns void pointer
- Data structures -- Generic containers
- Hardware access -- Raw memory manipulation

## Basic operations


# Memory addresses

## Memory Organization

Address space
- Linear address space -- Sequential memory addresses
- Memory segments -- Different regions for different purpose
- Address width -- Determined by processor architecture
- Memory alignment -- Requirements for efficient access

```
Memory Hierarchy:
┌─────────────────────────────────────────────────────────────┐
│                    CPU Registers                            │
│                  (Fastest, Smallest)                        │
├─────────────────────────────────────────────────────────────┤
│                    Cache Memory                             │
│                   (Fast, Small)                             │
├─────────────────────────────────────────────────────────────┤
│                    Main Memory (RAM)                        │
│                   (Slower, Larger)                          │
├─────────────────────────────────────────────────────────────┤
│                    Flash Memory                             │
│                  (Slowest, Largest)                         │
└─────────────────────────────────────────────────────────────┘
```


## Address types

Physical addresses

- Direct addresses in physical memory
- Used by hardware for memory access
- Managed by memory management unit (MMU)
- Required for DMA operations

Virtual addresses

- Addresses used by software on hosted/OS systems with an MMU
- Translated to physical addresses by MMU
- Provide memory protection and isolation
- Enable paging and advanced protection
- Many microcontrollers (e.g. ARM Cortex-M) lack an MMU; they only use physical addresses

Memory mapped addresses

- Addresses that map to hardware registers
- Used for I/O operations
- May have special access requirements
- Can be volatile (change without software action)

Address alignment

- Data alignment -- Data types must be aligned to specific boundaries
- Performance impact -- Misaligned access can be slower
- Hardware requirements -- Some processors require alignment
- Cache Effects -- Alignment affects cache performance

Alignment example

```
Alignment Requirements:
┌─────────────────┬─────────────┬─────────────────┐
│   Data Type     │   Size      │   Alignment     │
├─────────────────┼─────────────┼─────────────────┤
│   uint8_t       │   1 byte    │   1 byte        │
│   uint16_t      │   2 bytes   │   2 bytes       │
│   uint32_t      │   4 bytes   │   4 bytes       │
│   uint64_t      │   8 bytes   │   8 bytes       │
└─────────────────┴─────────────┴─────────────────┘
```

