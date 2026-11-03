*Este proyecto ha sido creado como parte del currículo de 42 por jmunoz-j.*

<div align="right">
  <strong>Languages:</strong>
  <a href="README.md">English</a> ｜ 
  <a href="README_es.md">Español</a>
</div>

# Libft (Biblioteca de Funciones)

## Descripción
Este proyecto es la base central del currículo de la escuela 42. El objetivo es recrear desde cero varias funciones de la biblioteca estándar de C (libc), así como funciones de utilidad adicionales para la manipulación de strings, gestión de memoria y estructuras de datos (listas enlazadas).

Al reescribir estas funciones, adquieres un profundo conocimiento de su mecánica interna, de la gestión rigurosa de la memoria dinámica (previniendo fugas/leaks y fallos de segmentación/segmentation faults) y de la creación de código robusto y modular. El resultado de este proyecto es una biblioteca estática (`libft.a`) que se usará como herramienta fundamental en la gran mayoría de los futuros proyectos de 42.

## Instrucciones

### Requisitos previos
Para compilar este proyecto necesitarás:
- Un compilador de C (como `gcc` o `clang`).
- La utilidad `make`.

### Compilación e Instalación
1. Clona este repositorio en tu máquina local.
2. Navega hasta la raíz del repositorio.
3. Ejecuta el comando `make` en tu terminal.

Esto compilará todos los archivos fuente (`.c`) y generará el archivo de la biblioteca estática llamado `libft.a`.

**Comandos de Makefile disponibles:**
- `make`: Compila la biblioteca estática `libft.a`.
- `make clean`: Elimina los archivos objeto (`.o`) generados durante la compilación.
- `make fclean`: Ejecuta `clean` y también elimina el archivo `libft.a`.
- `make re`: Ejecuta `fclean` seguido de `make`, recompilando todo desde cero.

### Ejecución / Uso en otros proyectos
Para usar esta biblioteca en tus propios proyectos:
1. Incluye el archivo de cabecera en tus archivos `.c`: `#include "libft.h"`
2. Compila tus archivos junto con la biblioteca:
   ```bash
   gcc tu_archivo.c -L. -lft -o tu_programa
   ```

## Descripción Detallada de la Biblioteca

### Funciones de Comprobación y Manipulación de Caracteres

| Función | Prototipo | Descripción | Parámetros (Entradas) |
|---|---|---|---|
| `ft_isalpha` | `int ft_isalpha(int c);` | Comprueba si es un carácter alfabético. | `c`: El carácter a comprobar. |
| `ft_isdigit` | `int ft_isdigit(int c);` | Comprueba si es un dígito (del 0 al 9). | `c`: El carácter a comprobar. |
| `ft_isalnum` | `int ft_isalnum(int c);` | Comprueba si es un carácter alfanumérico. | `c`: El carácter a comprobar. |
| `ft_isascii` | `int ft_isascii(int c);` | Comprueba si un carácter pertenece al conjunto de caracteres ASCII. | `c`: El carácter a comprobar. |
| `ft_isprint` | `int ft_isprint(int c);` | Comprueba si es un carácter imprimible. | `c`: El carácter a comprobar. |
| `ft_toupper` | `int ft_toupper(int c);` | Convierte un carácter a mayúscula. | `c`: El carácter a convertir. |
| `ft_tolower` | `int ft_tolower(int c);` | Convierte un carácter a minúscula. | `c`: El carácter a convertir. |

### Funciones de Manipulación de Strings

| Función | Prototipo | Descripción | Parámetros (Entradas) |
|---|---|---|---|
| `ft_strlen` | `size_t ft_strlen(const char *s);` | Calcula la longitud de una string. | `s`: La string a medir. |
| `ft_strlcpy` | `size_t ft_strlcpy(char *dst, const char *src, size_t size);` | Copia de strings con límite de tamaño. | `dst`: Búfer de destino<br>`src`: String de origen<br>`size`: Tamaño total del búfer. |
| `ft_strlcat` | `size_t ft_strlcat(char *dst, const char *src, size_t size);` | Concatenación de strings con límite de tamaño. | `dst`: Búfer de destino<br>`src`: String de origen<br>`size`: Tamaño total del búfer. |
| `ft_strchr` | `char *ft_strchr(const char *s, int c);` | Localiza la primera aparición de un carácter. | `s`: String donde buscar<br>`c`: Carácter a encontrar. |
| `ft_strrchr` | `char *ft_strrchr(const char *s, int c);` | Localiza la última aparición de un carácter. | `s`: String donde buscar<br>`c`: Carácter a encontrar. |
| `ft_strncmp` | `int ft_strncmp(const char *s1, const char *s2, size_t n);` | Compara dos strings hasta `n` caracteres. | `s1`, `s2`: Strings a comparar<br>`n`: Máximo de caracteres a comparar. |
| `ft_strnstr` | `char *ft_strnstr(const char *big, const char *little, size_t len);` | Localiza una substring dentro de una string, buscando un máximo de `len` caracteres. | `big`: String donde buscar<br>`little`: Substring a encontrar<br>`len`: Máximo de caracteres a buscar. |
| `ft_strdup` | `char *ft_strdup(const char *s);` | Duplica una string, asignando memoria con `malloc`. | `s`: String a duplicar. |
| `ft_substr` | `char *ft_substr(char const *s, unsigned int start, size_t len);` | Extrae una substring de una string original. | `s`: String original<br>`start`: Índice de inicio<br>`len`: Longitud máxima de la substring. |
| `ft_strjoin` | `char *ft_strjoin(char const *s1, char const *s2);` | Concatena dos strings en una nueva string. | `s1`: String prefijo<br>`s2`: String sufijo. |
| `ft_strtrim` | `char *ft_strtrim(char const *s1, char const *set);` | Elimina los caracteres especificados del principio y del final de una string. | `s1`: String a recortar<br>`set`: Caracteres a eliminar. |
| `ft_split` | `char **ft_split(char const *s, char c);` | Divide una string en un array de substrings usando un carácter delimitador. | `s`: String a dividir<br>`c`: Carácter delimitador. |
| `ft_strmapi` | `char *ft_strmapi(char const *s, char (*f)(unsigned int, char));` | Aplica una función a cada carácter de una string para crear una nueva string. | `s`: String a iterar<br>`f`: Función a aplicar. |
| `ft_striteri` | `void ft_striteri(char *s, void (*f)(unsigned int, char*));` | Aplica una función a cada carácter de una string, modificando la original. | `s`: String a iterar<br>`f`: Función a aplicar. |

### Funciones de Manipulación de Memoria

| Función | Prototipo | Descripción | Parámetros (Entradas) |
|---|---|---|---|
| `ft_memset` | `void *ft_memset(void *s, int c, size_t n);` | Llena un bloque de memoria con un byte específico. | `s`: Bloque de memoria<br>`c`: Valor del byte<br>`n`: Número de bytes. |
| `ft_bzero` | `void ft_bzero(void *s, size_t n);` | Pone a cero los primeros `n` bytes de un bloque de memoria. | `s`: Bloque de memoria<br>`n`: Número de bytes. |
| `ft_memcpy` | `void *ft_memcpy(void *dest, const void *src, size_t n);` | Copia un área de memoria a otra (sin superposición). | `dest`: Destino<br>`src`: Origen<br>`n`: Número de bytes. |
| `ft_memmove` | `void *ft_memmove(void *dest, const void *src, size_t n);` | Copia un área de memoria a otra (gestionando correctamente la superposición). | `dest`: Destino<br>`src`: Origen<br>`n`: Número de bytes. |
| `ft_memchr` | `void *ft_memchr(const void *s, int c, size_t n);` | Escanea un bloque de memoria en busca de la primera aparición de un byte. | `s`: Bloque de memoria<br>`c`: Byte a encontrar<br>`n`: Número de bytes. |
| `ft_memcmp` | `int ft_memcmp(const void *s1, const void *s2, size_t n);` | Compara dos bloques de memoria. | `s1`, `s2`: Bloques de memoria<br>`n`: Número de bytes. |
| `ft_calloc` | `void *ft_calloc(size_t nmemb, size_t size);` | Asigna memoria para un array y la inicializa a cero. | `nmemb`: Número de elementos<br>`size`: Tamaño de cada elemento. |

### Funciones de Conversión y E/S (Salida a Descriptor de Archivo)

| Función | Prototipo | Descripción | Parámetros (Entradas) |
|---|---|---|---|
| `ft_atoi` | `int ft_atoi(const char *nptr);` | Convierte una string en un entero (`int`). | `nptr`: String que representa un número. |
| `ft_itoa` | `char *ft_itoa(int n);` | Convierte un entero en una string recién asignada en memoria. | `n`: Entero a convertir. |
| `ft_putchar_fd` | `void ft_putchar_fd(char c, int fd);` | Imprime un carácter en el descriptor de archivo proporcionado. | `c`: Carácter a escribir<br>`fd`: Descriptor de archivo. |
| `ft_putstr_fd` | `void ft_putstr_fd(char *s, int fd);` | Imprime una string en el descriptor de archivo proporcionado. | `s`: String a escribir<br>`fd`: Descriptor de archivo. |
| `ft_putendl_fd` | `void ft_putendl_fd(char *s, int fd);` | Imprime una string seguida de un salto de línea en el descriptor de archivo. | `s`: String a escribir<br>`fd`: Descriptor de archivo. |
| `ft_putnbr_fd` | `void ft_putnbr_fd(int n, int fd);` | Imprime un entero en el descriptor de archivo proporcionado. | `n`: Entero a escribir<br>`fd`: Descriptor de archivo. |

### Funciones de Listas Enlazadas (t_list)

| Función | Prototipo | Descripción | Parámetros (Entradas) |
|---|---|---|---|
| `ft_lstnew` | `t_list *ft_lstnew(void *content);` | Crea un nuevo nodo. | `content`: Datos para el nuevo nodo. |
| `ft_lstadd_front` | `void ft_lstadd_front(t_list **lst, t_list *new);` | Añade un nodo al principio de la lista. | `lst`: Puntero al primer nodo<br>`new`: Nodo a añadir. |
| `ft_lstsize` | `int ft_lstsize(t_list *lst);` | Cuenta el número de nodos de una lista. | `lst`: El principio de la lista. |
| `ft_lstlast` | `t_list *ft_lstlast(t_list *lst);` | Devuelve el último nodo de la lista. | `lst`: El principio de la lista. |
| `ft_lstadd_back` | `void ft_lstadd_back(t_list **lst, t_list *new);` | Añade un nodo al final de la lista. | `lst`: Puntero al primer nodo<br>`new`: Nodo a añadir. |
| `ft_lstdelone` | `void ft_lstdelone(t_list *lst, void (*del)(void *));` | Libera la memoria de un solo nodo de la lista. | `lst`: Nodo a liberar<br>`del`: Función para eliminar el contenido. |
| `ft_lstclear` | `void ft_lstclear(t_list **lst, void (*del)(void *));` | Elimina y libera todos los nodos de la lista de forma segura. | `lst`: Puntero a un nodo<br>`del`: Función para eliminar el contenido. |
| `ft_lstiter` | `void ft_lstiter(t_list *lst, void (*f)(void *));` | Itera a través de la lista y aplica una función a cada nodo. | `lst`: Un nodo de la lista<br>`f`: Función a aplicar. |
| `ft_lstmap` | `t_list *ft_lstmap(t_list *lst, void *(*f)(void *), void (*del)(void *));` | Crea una nueva lista iterando otra y aplicando una función, gestionando errores de memoria. | `lst`: Un nodo<br>`f`: Función a aplicar<br>`del`: Función de eliminación. |


# Recursos
## Documentación y Referencias

- Páginas del manual del sistema operativo: man 3 [función] (ej. man 3 strlen).
 
- Documentación de Valgrind (para el análisis de fugas de memoria).

- Reglas oficiales del compilador GCC y especificaciones de la Norma de 42 (Norminette).

# Uso de Inteligencia Artificial

Durante el desarrollo de este proyecto, la IA se utilizó como una herramienta de apoyo educativo, para traducir e interpretar registros de errores de herramientas como Valgrind (ej. *Invalid read of size 1* o *Address is not stack'd*), para comprender la mecánica del cortocircuito lógico en los condicionales, y para analizar posibles escenarios de desbordamiento de enteros (overflow/underflow) y fugas de memoria (Memory Leaks).

Se instruyó explícitamente a la IA para que no proporcionara código resuelto, sino que se limitara a explicar la lógica subyacente y señalar fallos algorítmicos, asegurando que todo el código del proyecto fuera escrito e iterado de forma autónoma.