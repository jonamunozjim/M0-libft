*This project has been created as part of the 42 curriculum by jmunoz-j.*

<div align="right">
  <strong>Languages:</strong>
  <a href="README.md">English</a> ｜ 
  <a href="README_es.md">Español</a>
</div>

# Libft (Library of Functions)

## Description
This project is the core foundation of the 42 school curriculum. The goal is to recreate from scratch various standard C library (libc) functions, as well as additional utility functions for string manipulation, memory management, and data structures (linked lists).

By rewriting these functions, you gain a deep understanding of their internal mechanics, rigorous dynamic memory management (preventing *leaks* and *segmentation faults*), and the creation of robust and modular code. The result of this project is a static library (`libft.a`) that will be used as a fundamental tool in the vast majority of future 42 projects.

## Instructions

### Prerequisites
To compile this project you will need:
- A C compiler (such as `gcc` or `clang`).
- The `make` utility.

### Compilation and Installation
1. Clone this repository to your local machine.
2. Navigate to the root of the repository.
3. Run the `make` command in your terminal.

This will compile all the source files (`.c`) and generate the static library file named `libft.a`.

**Available Makefile commands:**
- `make`: Compiles the static library `libft.a`.
- `make clean`: Removes the object files (`.o`) generated during compilation.
- `make fclean`: Executes `clean` and also removes the `libft.a` file.
- `make re`: Executes `fclean` followed by `make`, recompiling everything from scratch.

### Execution / Usage in other projects
To use this library in your own projects:
1. Include the header file in your `.c` files: `#include "libft.h"`
2. Compile your files along with the library:
   ```bash
   gcc your_file.c -L. -lft -o your_program


## Detailed Library Description

### Character Check and Manipulation Functions

| Function | Prototype | Description | Parameters (Inputs) |
|---|---|---|---|
| `ft_isalpha` | `int ft_isalpha(int c);` | Checks for an alphabetic character. | `c`: The character to check. |
| `ft_isdigit` | `int ft_isdigit(int c);` | Checks for a digit (0 through 9). | `c`: The character to check. |
| `ft_isalnum` | `int ft_isalnum(int c);` | Checks for an alphanumeric character. | `c`: The character to check. |
| `ft_isascii` | `int ft_isascii(int c);` | Checks whether a character fits into the ASCII character set. | `c`: The character to check. |
| `ft_isprint` | `int ft_isprint(int c);` | Checks for any printable character. | `c`: The character to check. |
| `ft_toupper` | `int ft_toupper(int c);` | Converts a character to uppercase. | `c`: The character to convert. |
| `ft_tolower` | `int ft_tolower(int c);` | Converts a character to lowercase. | `c`: The character to convert. |

### String Manipulation Functions

| Function | Prototype | Description | Parameters (Inputs) |
|---|---|---|---|
| `ft_strlen` | `size_t ft_strlen(const char *s);` | Calculates the length of a string. | `s`: The string to measure. |
| `ft_strlcpy` | `size_t ft_strlcpy(char *dst, const char *src, size_t size);` | Size-bounded string copying. | `dst`: Destination buffer<br>`src`: Source string<br>`size`: Total buffer size. |
| `ft_strlcat` | `size_t ft_strlcat(char *dst, const char *src, size_t size);` | Size-bounded string concatenation. | `dst`: Destination buffer<br>`src`: Source string<br>`size`: Total buffer size. |
| `ft_strchr` | `char *ft_strchr(const char *s, int c);` | Locates the first occurrence of a character. | `s`: String to search<br>`c`: Character to find. |
| `ft_strrchr` | `char *ft_strrchr(const char *s, int c);` | Locates the last occurrence of a character. | `s`: String to search<br>`c`: Character to find. |
| `ft_strncmp` | `int ft_strncmp(const char *s1, const char *s2, size_t n);` | Compares two strings up to `n` characters. | `s1`, `s2`: Strings to compare<br>`n`: Max characters to compare. |
| `ft_strnstr` | `char *ft_strnstr(const char *big, const char *little, size_t len);` | Locates a substring in a string, searching up to `n` characters. | `big`: String to search in<br>`little`: Substring to find<br>`len`: Max characters to search. |
| `ft_strdup` | `char *ft_strdup(const char *s);` | Duplicates a string, allocating memory with `malloc`. | `s`: String to duplicate. |
| `ft_substr` | `char *ft_substr(char const *s, unsigned int start, size_t len);` | Extracts a substring from an original string. | `s`: Original string<br>`start`: Starting index<br>`len`: Max substring length. |
| `ft_strjoin` | `char *ft_strjoin(char const *s1, char const *s2);` | Concatenates two strings into a new string. | `s1`: Prefix string<br>`s2`: Suffix string. |
| `ft_strtrim` | `char *ft_strtrim(char const *s1, char const *set);` | Trims specified characters from the beginning and end of a string. | `s1`: String to trim<br>`set`: Characters to remove. |
| `ft_split` | `char **ft_split(char const *s, char c);` | Splits a string into an array of substrings using a delimiter character. | `s`: String to split<br>`c`: Delimiter character. |
| `ft_strmapi` | `char *ft_strmapi(char const *s, char (*f)(unsigned int, char));` | Applies a function to each character of a string to create a new string. | `s`: String to iterate<br>`f`: Function to apply. |
| `ft_striteri` | `void ft_striteri(char *s, void (*f)(unsigned int, char*));` | Applies a function to each character of a string, modifying the original. | `s`: String to iterate<br>`f`: Function to apply. |

### Memory Manipulation Functions

| Function | Prototype | Description | Parameters (Inputs) |
|---|---|---|---|
| `ft_memset` | `void *ft_memset(void *s, int c, size_t n);` | Fills a memory block with a specific byte. | `s`: Memory block<br>`c`: Byte value<br>`n`: Number of bytes. |
| `ft_bzero` | `void ft_bzero(void *s, size_t n);` | Zeroes out the first `n` bytes of a memory block. | `s`: Memory block<br>`n`: Number of bytes. |
| `ft_memcpy` | `void *ft_memcpy(void *dest, const void *src, size_t n);` | Copies a memory area to another (non-overlapping). | `dest`: Destination<br>`src`: Source<br>`n`: Number of bytes. |
| `ft_memmove` | `void *ft_memmove(void *dest, const void *src, size_t n);` | Copies a memory area to another (handling overlapping correctly). | `dest`: Destination<br>`src`: Source<br>`n`: Number of bytes. |
| `ft_memchr` | `void *ft_memchr(const void *s, int c, size_t n);` | Scans a memory block for the first occurrence of a byte. | `s`: Memory block<br>`c`: Byte to find<br>`n`: Number of bytes. |
| `ft_memcmp` | `int ft_memcmp(const void *s1, const void *s2, size_t n);` | Compares two memory blocks. | `s1`, `s2`: Memory blocks<br>`n`: Number of bytes. |
| `ft_calloc` | `void *ft_calloc(size_t nmemb, size_t size);` | Allocates memory for an array and initializes it to zero. | `nmemb`: Number of elements<br>`size`: Size of each element. |

### Conversion and I/O Functions (File Descriptor Output)

| Function | Prototype | Description | Parameters (Inputs) |
|---|---|---|---|
| `ft_atoi` | `int ft_atoi(const char *nptr);` | Converts a string to an integer (`int`). | `nptr`: String representing a number. |
| `ft_itoa` | `char *ft_itoa(int n);` | Converts an integer to a newly allocated string. | `n`: Integer to convert. |
| `ft_putchar_fd` | `void ft_putchar_fd(char c, int fd);` | Outputs a character to the given file descriptor. | `c`: Character to write<br>`fd`: File descriptor. |
| `ft_putstr_fd` | `void ft_putstr_fd(char *s, int fd);` | Outputs a string to the given file descriptor. | `s`: String to write<br>`fd`: File descriptor. |
| `ft_putendl_fd` | `void ft_putendl_fd(char *s, int fd);` | Outputs a string followed by a newline to the file descriptor. | `s`: String to write<br>`fd`: File descriptor. |
| `ft_putnbr_fd` | `void ft_putnbr_fd(int n, int fd);` | Outputs an integer to the given file descriptor. | `n`: Integer to write<br>`fd`: File descriptor. |

### Linked List Functions (t_list)

| Function | Prototype | Description | Parameters (Inputs) |
|---|---|---|---|
| `ft_lstnew` | `t_list *ft_lstnew(void *content);` | Creates a new node. | `content`: Data for the new node. |
| `ft_lstadd_front` | `void ft_lstadd_front(t_list **lst, t_list *new);` | Adds a node to the beginning of the list. | `lst`: Pointer to the first node<br>`new`: Node to add. |
| `ft_lstsize` | `int ft_lstsize(t_list *lst);` | Counts the number of nodes in a list. | `lst`: The beginning of the list. |
| `ft_lstlast` | `t_list *ft_lstlast(t_list *lst);` | Returns the last node of the list. | `lst`: The beginning of the list. |
| `ft_lstadd_back` | `void ft_lstadd_back(t_list **lst, t_list *new);` | Adds a node to the end of the list. | `lst`: Pointer to the first node<br>`new`: Node to add. |
| `ft_lstdelone` | `void ft_lstdelone(t_list *lst, void (*del)(void *));` | Frees the memory of a single node in the list. | `lst`: Node to free<br>`del`: Function to delete content. |
| `ft_lstclear` | `void ft_lstclear(t_list **lst, void (*del)(void *));` | Deletes and frees all nodes in the list safely. | `lst`: Pointer to a node<br>`del`: Function to delete content. |
| `ft_lstiter` | `void ft_lstiter(t_list *lst, void (*f)(void *));` | Iterates through the list and applies a function to each node. | `lst`: A node in the list<br>`f`: Function to apply. |
| `ft_lstmap` | `t_list *ft_lstmap(t_list *lst, void *(*f)(void *), void (*del)(void *));` | Creates a new list by iterating another and applying a function, managing memory errors. | `lst`: A node<br>`f`: Function to apply<br>`del`: Deletion function. |


# Resources
## Documentation and References

- Operating system manual pages: man 3 [function] (e.g., man 3 strlen).
 
- Valgrind Documentation (for memory leak analysis).

- Official GCC compiler rules and 42 Norm specifications (Norminette).

# Artificial Intelligence Usage

During the development of this project, AI was used as an educational support tool, to translate and interpret error logs from tools like Valgrind (e.g., Invalid read of size 1 or Address is not stack'd), to understand the mechanics of logical short-circuiting in conditionals, and to analyze potential integer overflow/underflow scenarios and Memory Leaks.

The AI was explicitly instructed not to provide solved code, but to limit itself to explaining the underlying logic and pointing out algorithmic flaws, ensuring that all project code was written and iterated autonomously.