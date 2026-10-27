# Guía Básica de Python: Operadores Relacionales (Comparación)

En la programación, constantemente necesitamos tomar decisiones basándonos en si una afirmación es verdadera o falsa. Para comparar valores entre sí, utilizamos los **operadores relacionales** (también conocidos como *operadores de comparación*).

---

## 1. ¿Qué es un Operador Relacional?

Un **operador relacional** compara dos valores (llamados operandos) y devuelve siempre un resultado de tipo **booleano**:
* `True` (Verdadero)
* `False` (Falso)

### Ejemplo conceptual:
Si le preguntas a Python: *¿Es 10 mayor que 5?*, Python responderá `True`.

---

## 2. Los 6 Operadores Relacionales en Python

Python cuenta con 6 operadores relacionales principales:

| Operador | Nombre / Significado | Ejemplo | Resultado |
| :---: | :--- | :---: | :---: |
| `==` | **Igual a** | `5 == 5` | `True` |
| `!=` | **Diferente de / Distinto de** | `5 != 3` | `True` |
| `>` | **Mayor que** | `10 > 20` | `False` |
| `<` | **Menor que** | `8 < 15` | `True` |
| `>=` | **Mayor o igual que** | `10 >= 10` | `True` |
| `<=` | **Menor o igual que** | `7 <= 5` | `False` |

---

## 3. Detalle y Ejemplos de Cada Operador

### A. Operador de Igualdad (`==`)
Verifica si dos valores son exactamente iguales.

> ⚠️ **¡Cuidado, error común de principiante!**
> * `=` es el operador de **asignación** (guardar un valor en una variable).
> * `==` es el operador de **comparación** (preguntar si dos cosas son iguales).

```python
edad = 18
print(edad == 18)  # Devuelve: True
print(edad == 20)  # Devuelve: False
```

### B. Operador de Diferencia (`!=`)
Verifica si dos valores son **distintos** o diferentes entre sí. Devuelve `True` si NO son iguales.

```python
codigo_acceso = "1234"
print(codigo_acceso != "0000")  # Devuelve: True
print(codigo_acceso != "1234")  # Devuelve: False
```

### C. Mayor que (`>`) y Menor que (`<`)
Comparan si un número es estrictamente mayor o menor que otro.

```python
precio = 150.0

print(precio > 100.0)  # Devuelve: True (150 es mayor que 100)
print(precio < 50.0)   # Devuelve: False (150 no es menor que 50)
```

### D. Mayor o igual que (`>=`) y Menor o igual que (`<=`)
Permiten incluir el valor límite en la comparación.

```python
calificacion = 70

# El mínimo para aprobar es 70
print(calificacion >= 70)  # Devuelve: True (70 es igual a 70)
print(calificacion > 70)   # Devuelve: False (70 no es estrictamente mayor que 70)
```

---

## 4. Comparación de Cadenas de Texto (`str`)

Los operadores relacionales no solo funcionan con números; también sirven para comparar **texto**.

### A. Igualdad exacta (`==` / `!=`)
Toma en cuenta las mayúsculas y minúsculas (*Case-sensitive*).

```python
print("Python" == "python")  # Devuelve: False (la 'P' mayúscula cambia todo)
print("Hola" != "Adios")    # Devuelve: True
```

### B. Comparación alfabética (`>` / `<`)
Python compara los caracteres según su orden en la tabla Unicode/ASCII (similar al orden alfabético).

```python
print("ana" < "carlos")  # Devuelve: True (la 'a' va antes que la 'c')
```

---

## 5. Comparaciones Encadenadas en Python

Una de las características más elegantes de Python es que permite **encadenar operadores relacionales** para comprobar rangos de forma limpia, tal como se hace en las matemáticas tradicionales.

### Ejemplo: Validar si un número está en un rango (entre 10 y 20)

```python
x = 15

# Forma tradicional de otros lenguajes:
# x >= 10 and x <= 20

# Forma encadenada estilo Python:
print(10 <= x <= 20)  # Devuelve: True
```

---

## 6. Integración con `input()` y Estructuras Condicionales

En la práctica, los operadores relacionales se utilizan junto con `input()` para tomar decisiones mediante `if`/`else`.

### Ejemplo real: Sistema de Control de Acceso

```python
# Pedimos la edad al usuario
edad_usuario = int(input("Ingresa tu edad: "))

# Evaluamos la condición con un operador relacional
es_mayor_de_edad = edad_usuario >= 18

print(f"¿Tienes acceso permitido?: {es_mayor_de_edad}")
```

---

## 7. Tabla de Resumen Rápido

| Expresión | ¿Cómo se lee? | Resultado |
| :--- | :--- | :---: |
| `15 == 15` | "¿Es 15 igual a 15?" | `True` |
| `10 != 10` | "¿Es 10 diferente de 10?" | `False` |
| `25 > 30` | "¿Es 25 mayor que 30?" | `False` |
| `4 <= 4` | "¿Es 4 menor o igual a 4?" | `True` |
| `"A" == "a"` | "¿Es 'A' igual a 'a'?" | `False` |

---

## 8. Ejercicios Prácticos para la Clase

Determina cuál será la salida (`True` o `False`) de las siguientes instrucciones:

1. `print(8 * 2 == 16)`
2. `print(100 / 2 != 50)`
3. `print("gato" > "perro")`
4. `print(15 >= 15)`
5. `print(3 ** 2 < 8)`
