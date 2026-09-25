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

<!-- daily-concept-date: 2026-09-11 -->
<!-- daily-concept-index: 11 -->
## 2026-09-11 — Process Creation and Fork

**Core question:** What exactly happens when fork is called?

**Things to check:**

- What is copy-on-write and why does it matter?
- How to avoid zombie processes?
- What is the difference between fork, vfork, and clone?
- How to share file descriptors between processes?

**Exercise:** Write a program that forks a child process. The parent waits for the child, which executes a different code path. Add pipes for inter-process communication.

**My notes:**

-

<!-- daily-concept-date: 2026-09-12 -->
<!-- daily-concept-index: 12 -->
## 2026-09-12 — Pipes and FIFOs

**Core question:** How to communicate between related and unrelated processes?

**Things to check:**

- What are the differences between anonymous pipes and named pipes?
- How to handle blocking vs non-blocking reads/writes?
- What happens when a pipe is closed?
- How to multiplex multiple pipes?

**Exercise:** Implement a simple shell pipeline: cmd1 | cmd2 | cmd3. Use fork, dup2, and pipe to connect stdin/stdout between processes.

**My notes:**

-

<!-- daily-concept-date: 2026-09-13 -->
<!-- daily-concept-index: 13 -->
## 2026-09-13 — Shared Memory

**Core question:** How to share memory between processes efficiently?

**Things to check:**

- What are POSIX shared memory vs System V?
- How to synchronize access to shared memory?
- What happens to shared memory when processes exit?
- How to map files into memory with mmap?

**Exercise:** Implement a producer-consumer pattern using POSIX shared memory with a mutex and condition variable stored in the shared segment.

**My notes:**

-

<!-- daily-concept-date: 2026-09-14 -->
<!-- daily-concept-index: 14 -->
## 2026-09-14 — Message Queues

**Core question:** How to send structured messages between processes?

**Things to check:**

- What are the advantages over pipes?
- How to handle message priorities?
- What are the capacity limits?
- How to choose between System V and POSIX message queues?

**Exercise:** Create a simple chat program where multiple clients send messages to a server using POSIX message queues with message priorities.

**My notes:**

-

<!-- daily-concept-date: 2026-09-15 -->
<!-- daily-concept-index: 15 -->
## 2026-09-15 — Threads and Pthreads

**Core question:** What's the difference between processes and threads?

**Things to check:**

- How to create and join threads?
- What thread attributes are configurable?
- How to pass data to threads safely?
- What are the stack size considerations?

**Exercise:** Write a multi-threaded program that calculates the sum of an array using multiple threads. Each thread processes a chunk of the array. Compare performance with process-based version.

**My notes:**

-

<!-- daily-concept-date: 2026-09-16 -->
<!-- daily-concept-index: 16 -->
## 2026-09-16 — Mutexes and Condition Variables

**Core question:** How to synchronize thread access to shared resources?

**Things to check:**

- What is the difference between mutex and spinlock?
- How to avoid deadlock?
- What is the condition variable pattern?
- What are the pthread mutex attributes?

**Exercise:** Implement a thread-safe queue with mutexes and condition variables. Include proper handling of spurious wakeups.

**My notes:**

-

<!-- daily-concept-date: 2026-09-17 -->
<!-- daily-concept-index: 17 -->
## 2026-09-17 — Atomic Operations

**Core question:** When are atomic operations necessary and sufficient?

**Things to check:**

- What operations can be made atomic in C?
- How to use C11 atomics?
- What are memory barriers and when are they needed?
- What is the difference between atomic and volatile?

**Exercise:** Implement a lock-free counter using C11 atomic operations. Compare with a mutex-protected counter in a multi-threaded benchmark.

**My notes:**

-

<!-- daily-concept-date: 2026-09-18 -->
<!-- daily-concept-index: 18 -->
## 2026-09-18 — Thread-Specific Storage

**Core question:** How to maintain per-thread state?

**Things to check:**

- How to use pthread_key_t and pthread_setspecific?
- What happens to thread-local data on thread exit?
- When to use __thread or thread_local?
- How to cleanup thread-local storage?

**Exercise:** Create a thread-safe logging system where each thread maintains its own log buffer using thread-specific storage, flushing on completion.

**My notes:**

-

<!-- daily-concept-date: 2026-09-19 -->
<!-- daily-concept-index: 19 -->
## 2026-09-19 — Non-Blocking I/O and Select

**Core question:** How to monitor multiple file descriptors?

**Things to check:**

- How to set non-blocking mode on file descriptors?
- What are the limitations of select?
- How to handle EAGAIN and EWOULDBLOCK?
- What is the difference between select, poll, and epoll?

**Exercise:** Implement a simple TCP server that handles multiple clients using select. Handle read/write events without blocking.

**My notes:**

-

<!-- daily-concept-date: 2026-09-20 -->
<!-- daily-concept-index: 20 -->
## 2026-09-20 — Epoll and Event-Driven Programming

**Core question:** How to handle thousands of connections efficiently?

**Things to check:**

- What are edge-triggered vs level-triggered events?
- How to use epoll_create, epoll_ctl, and epoll_wait?
- How to manage connection state in event loops?
- What are the performance advantages of epoll?

**Exercise:** Write an echo server using epoll that handles many concurrent connections. Include proper handling of partial reads/writes.

**My notes:**

-

<!-- daily-concept-date: 2026-09-21 -->
<!-- daily-concept-index: 21 -->
## 2026-09-21 — TCP Socket Programming

**Core question:** How to establish reliable network connections?

**Things to check:**

- What is the TCP three-way handshake?
- How to handle connection establishment failures?
- What are socket options and when to use them?
- How to handle TCP_NODELAY and Nagle's algorithm?

**Exercise:** Implement a TCP client-server application where the server echoes back a message. Handle connection resets, timeouts, and partial sends gracefully.

**My notes:**

-

<!-- daily-concept-date: 2026-09-22 -->
<!-- daily-concept-index: 22 -->
## 2026-09-22 — UDP and Datagram Sockets

**Core question:** How to handle connectionless, unreliable communication?

**Things to check:**

- What are the differences between TCP and UDP?
- How to handle packet loss and reordering?
- How to implement reliability on top of UDP?
- When is UDP preferred over TCP?

**Exercise:** Implement a UDP-based file transfer protocol with retransmission and acknowledgments. Handle packet loss simulation.

**My notes:**

-

<!-- daily-concept-date: 2026-09-23 -->
<!-- daily-concept-index: 23 -->
## 2026-09-23 — Unix Domain Sockets

**Core question:** How to communicate between processes on the same host?

**Things to check:**

- What are the performance advantages?
- How to pass file descriptors over Unix sockets?
- What are the security implications?
- How to use SOCK_SEQPACKET?

**Exercise:** Implement a privileged daemon that receives file descriptors over Unix domain sockets from unprivileged clients and performs operations on them.

**My notes:**

-

<!-- daily-concept-date: 2026-09-24 -->
<!-- daily-concept-index: 24 -->
## 2026-09-24 — Timer Management

**Core question:** How to implement timeouts and periodic tasks?

**Things to check:**

- How to use timerfd_create?
- What are the differences between settimer and timer_create?
- How to implement a timing wheel?
- How to handle system time changes?

**Exercise:** Implement a connection timeout system for a network server using a timer wheel. Each connection times out after N seconds of inactivity.

**My notes:**

-

<!-- daily-concept-date: 2026-09-25 -->
<!-- daily-concept-index: 25 -->
## 2026-09-25 — Memory Pool Allocation

**Core question:** How to manage memory efficiently for high-performance applications?

**Things to check:**

- What are the advantages over malloc/free?
- How to implement a slab allocator?
- How to handle variable-size allocations?
- How to avoid fragmentation?

**Exercise:** Implement a fixed-size memory pool that allocates and frees blocks efficiently. Include thread-safety and demonstrate reuse patterns.

**My notes:**

-

<!-- daily-concept-date: 2026-09-26 -->
<!-- daily-concept-index: 26 -->
## 2026-09-26 — Cache and Alignment

**Core question:** How does memory layout affect performance?

**Things to check:**

- What is cache line size and why does it matter?
- How to align structures for cache efficiency?
- What is false sharing and how to avoid it?
- How to use __attribute__((aligned))?

**Exercise:** Write a benchmark that compares performance of an array of structs where fields are ordered for cache efficiency vs poorly ordered. Measure cache misses.

**My notes:**

- 
