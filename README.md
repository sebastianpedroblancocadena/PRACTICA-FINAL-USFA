# Documentación del Proyecto: Práctica Final - Lógica de Programación II

## 1. Descripción General de la Web
Esta aplicación web es un simulador interactivo de un entorno de desarrollo (IDE). Está diseñada para presentar y ejecutar visualmente una práctica de la materia **Lógica de Programación II** de la **USFA**, desarrollada por **Sebastian Blanco**.
- **Frontend**: HTML5, Tailwind CSS y la librería de iconos Lucide.
- **Funcionalidad interactiva**: Utiliza JavaScript para aplicar resaltado de sintaxis (*syntax highlighting*) al código C++ y simular una terminal asíncrona que emula el comportamiento de compilación y ejecución de consola, replicando la lógica exacta del script en C++.

---

## 2. Documentación del Código C++ (Backend Lógico)

El núcleo algorítmico del proyecto es un script en C++ que contiene 11 ejercicios sobre diversas estructuras de datos y algoritmos (arreglos, matrices, pilas, colas y ordenamiento).

### 2.1. Estructura y Librerías Utilizadas
El programa está estructurado en módulos y hace uso de las siguientes librerías estándar (STL):
- `<iostream>`: Entrada/salida estándar a consola.
- `<string>`: Manipulación de cadenas de texto.
- `<vector>`: Uso de arreglos dinámicos para gestión de memoria eficiente.
- `<stack>`: Implementación de Pilas (arquitectura LIFO).
- `<queue>`: Implementación de Colas (arquitectura FIFO).
- `<algorithm>`: Utilidades algorítmicas estándar.
- `<cctype>`: Funciones para manipulación y evaluación de caracteres (ej. `tolower`).

### 2.2. Funciones Utilitarias (Validación y UI de Consola)
- **Constantes de Color (ANSI)**: Se definen secuencias de escape ANSI (`C_TITULO`, `C_ERROR`, `C_EXITO`, etc.) para dar un formato visual y jerarquía en la consola.
- `leerEntero(string mensaje)` y `leerDouble(string mensaje)`: Funciones robustas que solicitan datos al usuario y previenen bucles infinitos en la consola si el usuario ingresa un tipo de dato incorrecto (letras en lugar de números). Hacen uso de `cin.clear()` y `cin.ignore()`.
- `pausar()`: Detiene la ejecución esperando un *Enter*, simulando el `system("pause")` pero de manera multiplataforma.
- `aMinusculas(string texto)`: Convierte cadenas completas a letras minúsculas para realizar búsquedas insensibles a mayúsculas (*case-insensitive*).

### 2.3. Estructuras de Datos (Clases)
- **`Estudiante`**: Almacena `codigo`, `nombre`, `carrera` y `promedio`.
- **`EstudianteTramite`**: Almacena `codigo`, `nombre` y `tramite` orientado al ejercicio de sistema de atención.
- **`Producto`**: Clase sencilla para almacenar el `nombre` dentro del inventario.

---

### 2.4. Detalle de Ejercicios

#### Ejercicio 1: Estadísticas de un arreglo
- **Descripción**: Lee un arreglo de *N* números enteros ingresados por el usuario.
- **Procesamiento**: Itera sobre el vector para calcular e imprimir la suma total, el promedio y encontrar secuencialmente los valores máximo y mínimo.

#### Ejercicio 2: Buscar y contar
- **Descripción**: Realiza búsquedas específicas dentro de un arreglo de *N* enteros.
- **Procesamiento**: Identifica la primera posición de aparición de un número dado, cuenta el total de incidencias y guarda todas las posiciones exactas donde aparece en un `vector<int>` auxiliar.

#### Ejercicio 3: Ordenamiento
- **Descripción**: Ordena un vector numérico de manera ascendente.
- **Procesamiento**: Implementa el clásico **Algoritmo de Burbuja (Bubble Sort)** con complejidad `O(n^2)`. Recorre el arreglo intercambiando elementos adyacentes si el elemento actual es mayor al siguiente.

#### Ejercicio 4: Búsqueda de palabras
- **Descripción**: Busca una cadena de texto (*string*) dentro de un arreglo de palabras.
- **Procesamiento**: Convierte de forma dinámica tanto las palabras del vector como el término de búsqueda a minúsculas usando la función `aMinusculas()` para garantizar coincidencias independientemente de cómo se escribió el texto.

#### Ejercicio 5: Registro de estudiantes
- **Descripción**: Sistema básico de gestión sobre un arreglo de objetos `vector<Estudiante>`.
- **Procesamiento**: Registra estudiantes, imprime el catálogo completo, busca perfiles por código (búsqueda exacta) o por nombre (búsqueda insensible), e identifica al alumno que posee el mayor promedio aritmético.

#### Ejercicio 6: Estadísticas de una matriz
- **Descripción**: Crea y evalúa una matriz bidimensional dinámica de tamaño *N x M* (filas x columnas).
- **Procesamiento**: Recorre la matriz utilizando dos bucles `for` anidados para sumar todos los elementos, obtener el promedio general y encontrar los valores absolutos máximo y mínimo.

#### Ejercicio 7: Operaciones con matrices cuadradas
- **Descripción**: Ejecuta álgebra de matrices sobre dos matrices cuadradas de tamaño *N x N* (Matriz A y Matriz B).
- **Procesamiento**:
  - **Suma y resta**: Iteración simultánea de matrices (`A[i][j] ± B[i][j]`).
  - **Diagonales**: Extracción lineal de la diagonal principal (`A[i][i]`) y secundaria (`A[i][n-1-i]`).
  - **Sumatoria cruzada**: Suma individual del contenido de cada fila y de cada columna de la Matriz A.

#### Ejercicio 8: Buscar en una matriz
- **Descripción**: Ubica un valor dentro de una tabla bidimensional (Matriz *N x M*).
- **Procesamiento**: Retorna y muestra todas las coordenadas exactas `[Fila, Columna]` donde se produce una coincidencia, así como el conteo total de veces que se repite el número en la tabla.

#### Ejercicio 9: Historial de páginas (Estructura de Pila)
- **Descripción**: Simula de forma lógica el historial de navegación de un navegador web.
- **Procesamiento**: Emplea la estructura `std::stack<string>` (arquitectura LIFO: *Last In, First Out*). Las opciones del menú permiten hacer `push` de nuevas URLs, regresar (`pop`) a la página anterior y visualizar la página que está en el tope (`top`).

#### Ejercicio 10: Sistema de atención (Estructura de Cola)
- **Descripción**: Emula un sistema para filas de atención para estudiantes.
- **Procesamiento**: Utiliza la estructura `std::queue<EstudianteTramite>` (arquitectura FIFO: *First In, First Out*). Permite registrar (encolar) estudiantes al final de la fila, atender y retirar (`pop`) al que está al frente (`front()`) e imprimir en pantalla el estado actual de los que restan en la cola.

#### Ejercicio 11: Inventario y matriz de ventas multidimensional
- **Descripción**: Integra vectores de objetos unidimensionales y matrices numéricas bidimensionales para estadísticas de ventas semanales.
- **Procesamiento**:
  - Almacena un catálogo en `vector<Producto>`.
  - Mantiene una matriz `vector<vector<int>> ventas` asociando las filas a los productos y 5 columnas a los días laborables (Lunes a Viernes).
  - Efectúa agregaciones para calcular y mostrar ventas totales por producto (suma de la fila) y totales por día (suma de la columna), dictaminando cuál es el producto estrella y el día de mayor comercio.

### 2.5. Ciclo Principal (`main()`)
Actúa como la interfaz de usuario, proveyendo un "Menú de Práctica Final". 
- Se apoya en una estructura iterativa `do-while` para mantener el programa vivo hasta recibir una instrucción de salida (0).
- Usa un bloque condicional `switch-case` para direccionar la ejecución hacia cada una de las 11 funciones modulares correspondientes.
