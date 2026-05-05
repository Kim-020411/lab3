# Experiment 3

## Implementation and Debugging using GDB

---

## Objective

The objective of this experiment is to implement a singly linked list in C and debug the program using GDB. The aim is to understand dynamic memory allocation, pointer linking, segmentation fault detection, and step-by-step debugging.

---

## Background Study

A linked list is a linear data structure in which each element is called a node. Each node contains two parts:

1. Data field  
2. Pointer field that stores the address of the next node  

In a singly linked list, each node points to the next node, and the last node points to `NULL`.

GDB (GNU Debugger) is used to debug C programs. It allows step-by-step execution, setting breakpoints, and inspecting variables.

A segmentation fault occurs when a program tries to access an invalid memory location. In linked lists, this often happens when a `NULL` pointer is accessed.

---

## Experiment Description

In this experiment, a linked list was implemented using a `createNode()` function. The program created nodes with values 10, 20, and 30.

While adding the fourth node, a segmentation fault occurred at line 30:

```c
head->next->next->next->data = createNode(40);
```
## Observations

1. During execution, the program encountered a segmentation fault at line 30.  

2. Using GDB, it was observed that the pointer `head->next->next->next` was `NULL`.  

3. Attempting to access the `data` field of a `NULL` pointer caused the segmentation fault.  

4. The statement  
   `head->next->next->next->data = createnode(40);`  
   was incorrect because it attempted to assign a pointer value to an integer field.  

5. GDB commands such as `print head`, `print *head`, and `backtrace` helped in identifying the exact location and cause of the error.  

6. After correcting the statement to  
   `head->next->next->next = createnode(40);`,  
   the linked list was successfully created and printed without errors.

## Result

The singly linked list was successfully implemented using dynamic memory allocation.  
The segmentation fault encountered during execution was identified and corrected using GDB.  
After fixing the pointer assignment, the program produced the correct output:

`10 -> 20 -> 30 -> 40 -> NULL`

---

## Conclusion

This experiment provided a clear understanding of linked list implementation and pointer manipulation in C.  
It highlighted the importance of correct pointer usage and memory handling to avoid runtime errors such as segmentation faults.  

The use of GDB proved to be highly effective in debugging, allowing step-by-step execution and inspection of variables.  
Overall, the experiment demonstrated how debugging tools can be used to efficiently identify and fix errors in programs.
