# Daily Backend Concepts

One backend-engineering study prompt is published automatically each day. My notes and implementations are added manually.

<!-- daily-concept-date: 2026-09-01 -->
<!-- daily-concept-index: 1 -->
## 2026-09-01 — Memory Layout of a C Program

**Core question:** What lives in text, data, bss, heap, and stack?

**Things to check:**

- Where are global variables stored?
- What happens to uninitialized static variables?
- How does stack frame layout work?
- How to inspect memory segments at runtime?

**Exercise:** Write a program that prints the addresses of a local variable, a global variable, a static variable, and a dynamically allocated pointer. Map these to their segments.

**My notes:**

-

<!-- daily-concept-date: 2026-09-02 -->
<!-- daily-concept-index: 2 -->
## 2026-09-02 — Idempotency

**Core question:** Can this operation be safely repeated?

**Things to check:**

- What happens when a request is retried?
- Where should the idempotency key be stored?
- How long should the result be retained?
- Can concurrent duplicate requests race?

**Exercise:** Design an idempotent POST /payments endpoint with in-memory key storage and proper mutex locking in C.

**My notes:**

-

<!-- daily-concept-date: 2026-09-03 -->
<!-- daily-concept-index: 3 -->
## 2026-09-03 — Pointer Arithmetic and Array Decay

**Core question:** How do arrays differ from pointers in practice?

**Things to check:**

- When does an array decay to a pointer?
- What is sizeof(array) vs sizeof(pointer)?
- How does pointer arithmetic handle different types?
- What are the pitfalls of multi-dimensional arrays?

**Exercise:** Implement a function that sums a 2D matrix using both array indexing and pointer arithmetic. Compare assembly output.

**My notes:**

-

<!-- daily-concept-date: 2026-09-04 -->
<!-- daily-concept-index: 4 -->
## 2026-09-04 — The Volatile Keyword

**Core question:** When should variables be marked volatile?

**Things to check:**

- How does volatile prevent compiler optimizations?
- When is volatile needed for memory-mapped I/O?
- Does volatile make variables atomic?
- Common misconceptions about volatile

**Exercise:** Write a busy-wait loop that polls a hardware register (simulated with a pointer). Show the difference with and without volatile using compiler explorer.

**My notes:**

-

<!-- daily-concept-date: 2026-09-05 -->
<!-- daily-concept-index: 5 -->
## 2026-09-05 — Bit Manipulation and Bitfields

**Core question:** How to pack and unpack data efficiently?

**Things to check:**

- What are the bitwise operators and their pitfalls?
- When to use bitfields vs manual bit manipulation?
- How does endianness affect bit packing?
- What are the portability issues with bitfields?

**Exercise:** Implement a protocol header parser that extracts fields from a 32-bit word using both bitfields and shift/mask operations. Compare the generated assembly.

**My notes:**

-

<!-- daily-concept-date: 2026-09-06 -->
<!-- daily-concept-index: 6 -->
## 2026-09-06 — The Restrict Keyword

**Core question:** How does restrict enable compiler optimization?

**Things to check:**

- What aliasing assumptions does restrict make?
- When is it safe to use restrict?
- How does restrict interact with pointers to pointers?
- What's the performance impact in practice?

**Exercise:** Implement a vector addition function with and without restrict. Compare performance for large arrays.

**My notes:**

-

<!-- daily-concept-date: 2026-09-07 -->
<!-- daily-concept-index: 7 -->
## 2026-09-07 — Function Pointers and Callbacks

**Core question:** How to implement flexible, runtime-dynamic behavior?

**Things to check:**

- What's the syntax for declaring function pointers?
- How to create arrays of function pointers?
- What are the security implications of function pointers?
- How to pass context to callbacks?

**Exercise:** Implement a generic sorting function that accepts a comparison function pointer. Sort an array of structs by different fields.

**My notes:**

-

<!-- daily-concept-date: 2026-09-08 -->
<!-- daily-concept-index: 8 -->
## 2026-09-08 — Static and Dynamic Linking

**Core question:** What happens between compilation and execution?

**Things to check:**

- How do static libraries differ from shared libraries?
- What is the role of the dynamic linker?
- How to handle symbol resolution conflicts?
- How to create and use a shared library in C?

**Exercise:** Create a static library and a shared library from the same source. Build executables linking each and compare their sizes and behavior.

**My notes:**

-

<!-- daily-concept-date: 2026-09-09 -->
<!-- daily-concept-index: 9 -->
## 2026-09-09 — Signal Handling

**Core question:** How to handle asynchronous events gracefully?

**Things to check:**

- Which signals can be caught and which cannot?
- What functions are async-signal-safe?
- How to avoid race conditions in signal handlers?
- What is the difference between signal and sigaction?

**Exercise:** Write a program that catches SIGINT, prints a message, and continues. Then add a SIGALRM handler that sets a flag polled in the main loop.

**My notes:**

-

<!-- daily-concept-date: 2026-09-10 -->
<!-- daily-concept-index: 10 -->
## 2026-09-10 — File Descriptors and I/O

**Core question:** How does the kernel manage open files?

**Things to check:**

- What's the difference between buffered and unbuffered I/O?
- How do dup, dup2, and fcntl work?
- What are the file descriptor flags?
- How to implement non-blocking I/O?

**Exercise:** Implement a simple program that reads from stdin, writes to stdout, and handles redirection. Then add a custom file copy function using read/write with various buffer sizes.

**My notes:**

- 
