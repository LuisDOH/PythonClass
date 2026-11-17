# Guía Completa de Python: Listas (`list`)

Hasta ahora, hemos guardado un solo dato por variable (por ejemplo: `edad = 20` o `nombre = "Ana"`). Pero en la vida real necesitamos manejar **colecciones de datos**: una lista de compras, las calificaciones de 30 alumnos o los productos en un carrito en línea.

En Python, la estructura más versátil y utilizada para almacenar colecciones de elementos es la **Lista (`list`)**.

---

## 1. ¿Qué es una Lista y cuál es su Estructura?

Una lista es una estructura de datos que permite almacenar múltiples elementos agrupados bajo un mismo nombre de variable.

### Sintaxis básica
Las listas se definen encerrando sus elementos entre **corchetes `[]`** y separándolos por **comas `,`**.

```python
# Lista de cadenas de texto (strings)
frutas = ["manzana", "plátano", "naranja", "uva"]

# Lista de números enteros
calificaciones = [9, 10, 8, 7, 10]

# Lista vacía (muy útil para ir llenándola después)
carrito_compras = []
```

---

## 2. Características Principales de las Listas

Las listas en Python tienen 4 propiedades fundamentales que todo programador debe conocer:

1. **Son Ordenadas:** Los elementos mantienen el orden exacto en el que fueron agregados. Cada elemento ocupa una posición fija llamada **índice**.
2. **Son Mutables (Modificables):** A diferencia de los textos (`str`), el contenido de una lista **sí puede cambiar** después de haber sido creada (puedes agregar, editar o borrar elementos).
3. **Permiten Duplicados:** Una lista puede contener elementos repetidos sin ningún problema (por ejemplo: `[10, 10, 8, 10]`).
4. **Son Heterogéneas:** Pueden almacenar distintos tipos de datos al mismo tiempo (números, textos, booleanos e incluso otras listas).
   ```python
   perfil_usuario = ["Carlos", 25, 1.78, True]
   ```

---

## 3. Índices y Acceso a los Elementos

Para leer o modificar un dato específico dentro de una lista, usamos su **índice** (posición) entre corchetes.

> ⚠️ **Regla de Oro en Programación:** El conteo de posiciones siempre empieza en **cero (`0`)**, no en `1`.

```text
Lista:      ["manzana", "plátano", "naranja", "uva"]
Índice (+):      0          1          2        3
Índice (-):     -4         -3         -2       -1
```

### Ejemplos de Acceso y Modificación

```python
frutas = ["manzana", "plátano", "naranja", "uva"]

# 1. Leer elementos con índices positivos (de izquierda a derecha)
print(frutas[0])   # Imprime: manzana
print(frutas[2])   # Imprime: naranja

# 2. Leer elementos con índices negativos (de derecha a izquierda)
print(frutas[-1])  # Imprime: uva (el último elemento)
print(frutas[-2])  # Imprime: naranja (el penúltimo)

# 3. Modificar un elemento existente (Mutabilidad)
frutas[1] = "fresa"
print(frutas)      # Imprime: ['manzana', 'fresa', 'naranja', 'uva']
```

### Rebanado de Listas (*Slicing*)
Permite extraer una sublista indicando un rango `[inicio : fin]` (el índice `fin` no se incluye):

```python
numeros = [10, 20, 30, 40, 50, 60]

print(numeros[1:4])   # Imprime: [20, 30, 40] (índices 1, 2 y 3)
print(numeros[:3])    # Imprime: [10, 20, 30] (desde el principio hasta índice 2)
print(numeros[3:])    # Imprime: [40, 50, 60] (desde índice 3 hasta el final)
```

---

## 4. Métodos Más Comunes de las Listas

Los **métodos** son funciones integradas que pertenecen a las listas y se invocan usando un punto después del nombre de la variable (`lista.metodo()`).

### A. Métodos para AGREGAR elementos

| Método | Descripción | Ejemplo |
| :--- | :--- | :--- |
| **`.append(x)`** | Agrega un elemento `x` al **final** de la lista. | `lista.append("pera")` |
| **`.insert(i, x)`** | Inserta el elemento `x` en la posición exacta `i`, recorriendo los demás a la derecha. | `lista.insert(1, "kiwi")` |
| **`.extend(otra_lista)`** | Une todos los elementos de otra lista al final de la lista actual. | `lista.extend(["mango", "piña"])` |

```python
tareas = ["Estudiar", "Comer"]
tareas.append("Dormir")        # ['Estudiar', 'Comer', 'Dormir']
tareas.insert(1, "Hacer tarea") # ['Estudiar', 'Hacer tarea', 'Comer', 'Dormir']
```

### B. Métodos para ELIMINAR elementos

| Método | Descripción | Ejemplo |
| :--- | :--- | :--- |
| **`.remove(x)`** | Busca y elimina la **primera aparición** del valor `x`. (Da error si no existe). | `lista.remove("Comer")` |
| **`.pop(i)`** | Elimina y **devuelve** el elemento en la posición `i`. Si no se indica índice, elimina el último. | `ultimo = lista.pop()` |
| **`.clear()`** | Vacía completamente la lista, dejándola con 0 elementos `[]`. | `lista.clear()` |

```python
colores = ["rojo", "azul", "verde", "azul"]
colores.remove("azul")         # Elimina solo el primer 'azul' -> ['rojo', 'verde', 'azul']
eliminado = colores.pop(0)     # Elimina 'rojo' y lo guarda en la variable -> ['verde', 'azul']
```

### C. Métodos para BUSCAR y CONTAR

| Método | Descripción | Ejemplo |
| :--- | :--- | :--- |
| **`.index(x)`** | Devuelve el **índice** de la primera aparición del elemento `x`. | `pos = lista.index("verde")` |
| **`.count(x)`** | Cuenta cuántas veces aparece el elemento `x` dentro de la lista. | `veces = lista.count(10)` |

```python
notas = [8, 10, 9, 10, 7, 10]
print(notas.count(10))  # Imprime: 3
print(notas.index(9))   # Imprime: 2
```

### D. Métodos para ORDENAR e INVERTIR

| Método | Descripción | Ejemplo |
| :--- | :--- | :--- |
| **`.sort()`** | Ordena la lista original de menor a mayor (o alfabéticamente). | `numeros.sort()` |
| **`.sort(reverse=True)`** | Ordena la lista original de mayor a menor. | `numeros.sort(reverse=True)` |
| **`.reverse()`** | Invierte el orden actual de los elementos (sin ordenarlos). | `lista.reverse()` |

```python
precios = [350, 120, 890, 45]
precios.sort()
print(precios)  # Imprime: [45, 120, 350, 890]
```

---

## 5. Funciones Útiles y Recorrido con Bucles

Además de sus métodos propios, las listas trabajan muy bien con funciones nativas de Python y ciclos `for`:

### Funciones integradas clave
* **`len(lista)`**: Devuelve la cantidad total de elementos (longitud) de la lista.
* **`sum(lista)`**: Suma todos los elementos (solo si son números).
* **`max(lista)` / `min(lista)`**: Devuelven el valor máximo y mínimo respectivamente.
* **`in`**: Operador para verificar si un elemento existe dentro de la lista (`True` o `False`).

```python
edades = [18, 22, 19, 25, 20]

print("Total de alumnos:", len(edades))      # 5
print("Edad mayor:", max(edades))            # 25
print("Promedio:", sum(edades) / len(edades)) # 20.8
print("¿Hay alguien de 22?:", 22 in edades)  # True
```

### Recorriendo una lista con el bucle `for`
La forma más limpia y habitual de procesar todos los datos de una lista es iterando directamente sobre ella:

```python
productos = ["Leche", "Pan", "Huevos", "Café"]

print("--- Lista del Supermercado ---")
for item in productos:
    print(f"- Comprar: {item}")
```

---

## 6. Errores Comunes de Principiantes

1. **`IndexError: list index out of range` (Índice fuera de rango):**
   Ocurre cuando intentas acceder a una posición que no existe. Si una lista tiene 4 elementos, sus índices van del `0` al `3`; pedir `lista[4]` provocará este error.
2. **Asignar el resultado de `.append()` o `.sort()` a una variable:**
   Estos métodos modifican la lista directamente y devuelven `None`.
   * ❌ **Incorrecto:** `lista = lista.append("nuevo")` (Esto borra tu lista y la convierte en `None`).
   * ✅ **Correcto:** `lista.append("nuevo")`
