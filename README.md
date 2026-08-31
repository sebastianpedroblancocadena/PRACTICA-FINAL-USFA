# Práctica Final - Lógica de Programación II

## Información General
* **Institución:** Universidad Privada San Francisco de Asís (USFA)[cite: 6].
* **Carrera:** Ingeniería de Sistemas[cite: 6].
* **Materia:** Lógica de Programación II[cite: 6].
* **Estudiante:** Sebastian Blanco[cite: 6].

---

## Descripción del Proyecto
Este repositorio contiene la solución completa a la **Práctica Final** de la asignatura Lógica de Programación II[cite: 6]. El proyecto abarca un conjunto de **11 módulos en C++** que evalúan el dominio de estructuras de datos dinámicas, operaciones matriciales, algoritmos de ordenamiento, búsqueda y gestión de colecciones avanzadas mediante la Biblioteca Estándar de Plantillas (STL)[cite: 6].

---

## Arquitectura y Lógica del Código (C++)
El código fuente principal (`main.cpp`) implementa buenas prácticas de programación estructurada y modularización:

* **Librerías Estándar Utilizadas:**
  * `<iostream>` y `<string>`: Manejo seguro de flujos de entrada/salida y cadenas de texto[cite: 6].
  * `<vector>`: Creación de arreglos dinámicos unidimensionales y bidimensionales (matrices) con asignación de memoria eficiente en tiempo de ejecución[cite: 6].
  * `<stack>`: Implementación de la estructura LIFO (Last In, First Out) para la simulación de historiales[cite: 6].
  * `<queue>`: Implementación de la estructura FIFO (First In, First Out) para la gestión de colas de atención[cite: 6].
  * `<algorithm>` y `<cctype>`: Manipulación avanzada de caracteres y cadenas (*case-insensitive*)[cite: 6].

* **Robustez y Manejo de Errores:**
  * Se implementaron funciones de validación de entrada (`leerEntero` y `leerDouble`) que interceptan errores de tipo de datos mediante el control de estados del flujo (`cin.clear()` y `cin.ignore()`), evitando caídas de ejecución[cite: 6].
  * Interfaz de consola estilizada mediante secuencias de escape ANSI para diferenciar visualmente títulos, secciones, errores y mensajes de éxito[cite: 6].

---

## Desglose Lógico por Módulos (Ejercicios)

| # | Tema / Módulo | Descripción de la Lógica e Implementación en C++ |
| :--- | :--- | :--- |
| **1** | Estadísticas de un arreglo | Utiliza `std::vector<int>` de tamaño dinámico $N$, iterando linealmente para calcular la sumatoria total, el promedio aritmético y los valores extremos (`mayor` y `menor`)[cite: 6]. |
| **2** | Buscar y contar | Implementa una búsqueda secuencial para ubicar la primera coincidencia de un valor, computar su frecuencia total y almacenar las posiciones de índice en un vector auxiliar[cite: 6]. |
| **3** | Ordenamiento (Bubble Sort) | Aplica el algoritmo de ordenamiento de burbuja mediante bucles anidados para comparar elementos adyacentes y realizar intercambios condicionales temporales (`temp`)[cite: 6]. |
| **4** | Búsqueda de palabras | Realiza búsquedas de texto ignorando mayúsculas y minúsculas (*case-insensitive*) transformando dinámicamente cada carácter por referencia (`char &c`) mediante `tolower`[cite: 6]. |
| **5** | Registro de estudiantes | Modela objetos mediante la clase `Estudiante` para encapsular atributos heterogéneos (código, nombre, carrera, promedio), permitiendo búsquedas por claves específicas y cálculo de máximos[cite: 6]. |
| **6** | Estadísticas de una matriz | Gestiona una estructura anidada `vector<vector<int>>` de dimensiones $F \times C$, procesando la matriz en doble bucle para hallar sumas acumuladas, promedios y límites[cite: 6]. |
| **7** | Operaciones con matriz | Procesa matrices cuadradas $N \times N$ realizando suma/resta algebraica matricial, extracción de la diagonal principal (`i == j`), diagonal secundaria (`[i][n - 1 - i]`) y sumatorias por filas o columnas[cite: 6]. |
| **8** | Buscar en una matriz | Recorre una matriz bidimensional mapeando y devolviendo las coordenadas exactas de fila y columna de todas las coincidencias encontradas[cite: 6]. |
| **9** | Historial de páginas (Pilas) | Simula el comportamiento de un navegador web aplicando `std::stack<string>`, manipulando punteros lógicos con `push()` (visitar), `pop()` (regresar) y `top()` (ver actual)[cite: 6]. |
| **10** | Sistema de atención (Colas) | Modela una cola de atención estudiantil usando `std::queue<EstudianteTramite>`, utilizando `push()` para encolar y la combinación de `front()` con `pop()` para despachar[cite: 6]. |
| **11** | Inventario + matriz | Sincroniza un vector unidimensional de objetos `Producto` con una matriz de ventas configurada con 5 columnas fijas (días hábiles), cruzando índices para hallar productos más rentables y picos diarios[cite: 6]. |

---

## Compilación y Ejecución
Para compilar y ejecutar el código fuente en un entorno local con `g++`:

```bash
g++ -O2 main.cpp -o practica_final
./practica_final
