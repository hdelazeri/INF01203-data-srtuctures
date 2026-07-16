# INF01203 — Data Structures (TADs)

Coursework for **INF01203** (Estruturas de Dados): classic abstract data types (TADs) implemented in C.

Each structure is a standalone console project in the Visual Studio solution [`TADs.sln`](TADs.sln). Every project has a header (API), an implementation file, and a `main.c` demo that exercises the operations.

## Requirements

- A C compiler (Visual C++, gcc, or clang)
- Optional: Visual Studio 2019 or later to open and build `TADs.sln`

## Repository layout

| Folder | Sources | Element type (`Info`) |
|--------|---------|------------------------|
| [Singly Linked List](Singly%20Linked%20List/) | `SLL.h` / `SLL.c` / `main.c` | `int` |
| [Doubly Linked List](Doubly%20Linked%20List/) | `DLL.h` / `DLL.c` / `main.c` | `int` |
| [Circular Singly Linked List](Circular%20Singly%20Linked%20List/) | `CSLL.h` / `CSLL.c` / `main.c` | `int` |
| [Circular Doubly Linked List](Circular%20Doubly%20Linked%20List/) | `CDLL.h` / `CDLL.c` / `main.c` | `int` |
| [Stack](Stack/) | `Stack.h` / `Stack.c` / `main.c` | `int` (linked) |
| [Queue](Queue/) | `Queue.h` / `Queue.c` / `main.c` | `int` (linked, first/last) |
| [Binary Tree](Binary%20Tree/) | `BinaryTree.h` / `BinaryTree.c` / `main.c` | `char` |
| [Binary Search Tree](Binary%20Search%20Tree/) | `BST.h` / `BST.c` / `main.c` | `int` |
| [AVL Tree](AVL%20Tree/) | `AVL.h` / `AVL.c` / `main.c` | `int` (balance factor + rotations) |

## Project organization

Each folder follows the same pattern:

- **Header** — public API (`Initialize`, insert/remove/find, traversals, `Destroy`, …)
- **Implementation** — linked-structure logic
- **`main.c`** — small demo that prints steps and results

Payload type is `typedef`'d as `Info` per module (usually `int`; binary tree uses `char`).

## Build and run

### Visual Studio

1. Open [`TADs.sln`](TADs.sln).
2. Set the desired project as the startup project.
3. Build and run (Debug or Release; x86 or x64).

### Command line (gcc / clang)

From the repo root, compile any project the same way — link `main.c` with its implementation file:

```bash
cd "Singly Linked List" && gcc -o sll main.c SLL.c && ./sll
cd "../Doubly Linked List" && gcc -o dll main.c DLL.c && ./dll
cd "../Circular Singly Linked List" && gcc -o csll main.c CSLL.c && ./csll
cd "../Circular Doubly Linked List" && gcc -o cdll main.c CDLL.c && ./cdll
cd "../Stack" && gcc -o stack main.c Stack.c && ./stack
cd "../Queue" && gcc -o queue main.c Queue.c && ./queue
cd "../Binary Tree" && gcc -o btree main.c BinaryTree.c && ./btree
cd "../Binary Search Tree" && gcc -o bst main.c BST.c && ./bst
cd "../AVL Tree" && gcc -o avl main.c AVL.c && ./avl
```

On Windows with MinGW, use the same commands and run the `.exe` files produced.

## Operations summary

### Linked lists (SLL, DLL, CSLL, CDLL)

- Insert first, last, or at a middle position
- Find and remove by value
- List all elements
- DLL and CDLL also support listing backwards
- Destroy the list

### Stack

- `Push` / `Pop` / `Top` / `Empty` / `ListAll` / `Destroy`

### Queue

- `Enqueue` / `Dequeue` / `First` / `Empty` / `Destroy`

### Trees (Binary Tree, BST, AVL)

- Insert (binary tree: root / left / right by parent key; BST and AVL: ordered insert)
- Six traversal orders: pre-/in-/post-order × left- and right-oriented
- Find by value
- Destroy

**BST and AVL** also provide node count, formatted tree print, and remove.

**AVL** additionally maintains a balance factor and supports four rotations: right, left, left-right, and right-left.

## Notes

These are educational demos for course INF01203, not a shared library. Each project is self-contained and meant to be compiled and run on its own.
