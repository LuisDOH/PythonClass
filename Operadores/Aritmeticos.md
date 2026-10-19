# Operadores Aritméticos y Jerarquía de Operaciones

En lecciones anteriores aprendiste a declarar variables, pedir datos al usuario con `input()` y mostrarlos con `print()`. Ahora aprenderemos cómo **procesar datos numéricos** realizando operaciones matemáticas dentro de Python.

---

## 1. ¿Qué son los Operadores Aritméticos?

Los operadores aritméticos son símbolos especiales que le indican a Python que ejecute un cálculo matemático entre dos o más valores (llamados *operandos*).

Python cuenta con **7 operadores aritméticos fundamentales**:

| Operador | Nombre de la Operación | Ejemplo | Resultado |
| :---: | :--- | :--- | :--- |
| `+` | **Suma** | `10 + 5` | `15` |
| `-` | **Resta** | `10 - 5` | `5` |
| `*` | **Multiplicación** | `10 * 5` | `50` |
| `/` | **División (Flotante)** | `10 / 4` | `2.5` |
| `//` | **División Entera** | `10 // 4` | `2` |
| `%` | **Módulo (Residuo/Resto)** | `10 % 4` | `2` |
| `**` | **Potencia (Exponente)** | `2 ** 3` | `8` |

---

## 2. Detalle y Diferencias Clave entre Operadores

### A. Las Operaciones Básicas (`+`, `-`, `*`)
Funcionan exactamente igual que en las matemáticas tradicionales.
```python
a = 15
b = 4

print("Suma:", a + b)           # Imprime: 19
print("Resta:", a - b)          # Imprime: 11
print("Multiplicación:", a * b) # Imprime: 60
```

### B. Los Tres Tipos de División (`/`, `//`, `%`)
Es muy importante entender la diferencia entre estas tres operaciones:

1. **División Tradicional (`/`):**
   Siempre devuelve un número decimal (`float`), incluso si el resultado es exacto.
   ```python
   print(10 / 2)  # Resultado: 5.0 (de tipo float)
   print(10 / 3)  # Resultado: 3.3333333333333335
   ```

2. **División Entera (`//`):**
   Divide los números y **descarta la parte decimal**, redondeando siempre hacia abajo al entero más cercano.
   ```python
   print(10 // 3) # Resultado: 3 (descarta el .333...)
   print(10 // 4) # Resultado: 2 (descarta el .5)
   ```

3. **Módulo o Residuo (`%`):**
   Devuelve el **residuo o sobrante** que queda después de realizar una división entera.
   * *Uso muy común:* Saber si un número es par o impar (un número es par si `numero % 2 == 0`).
   ```python
   # Si dividimos 10 entre 3:
   # 10 / 3 = 3 y sobra 1.
   print(10 % 3)  # Resultado: 1
   ```

### C. Potenciación / Exponente (`**`)
Eleva un número a la potencia de otro.
```python
# 2 elevado al cubo (2 * 2 * 2)
print(2 ** 3)  # Resultado: 8

# 5 al cuadrado (5 * 5)
print(5 ** 2)  # Resultado: 25
```

---

## 3. Jerarquía de Operaciones (Orden de Precedencia)

Cuando escribes una expresión matemática con múltiples operadores (por ejemplo: `3 + 5 * 2`), Python no evalúa las operaciones de izquierda a derecha de forma simple. En su lugar, sigue las reglas matemáticas estándar conocidas como la **jerarquía de operaciones** (similar a la regla PEMDAS).

### Tabla de Prioridad (De mayor a menor importancia)

1. **`()` Parentesis:** Todo lo que esté dentro de un paréntesis se resuelve primero.
2. **`**` Exponentes:** Se evalúan en segundo lugar.
3. **`*`, `/`, `//`, `%` Multiplicación, Divisiones y Módulo:** Tienen el mismo nivel de prioridad y se evalúan antes que las sumas y restas.
4. **`+`, `-` Suma y Resta:** Son las operaciones con menor prioridad.

> 💡 **Regla de Desempate (De izquierda a derecha):**
> Si en una misma expresión hay dos operadores con el **mismo nivel de prioridad** (por ejemplo, una multiplicación y una división), Python los evalúa **de izquierda a derecha**.
>
> *(Excepción: La potenciación `**` se evalúa de derecha a izquierda).*

---

## 4. Ejemplos Pasó a Paso

### Ejemplo 1: Sin paréntesis
```python
resultado = 5 + 3 * 2
```
* **Paso 1:** Identificar prioridades. La multiplicación (`*`) tiene mayor prioridad que la suma (`+`).
* **Paso 2:** Resolver la multiplicación: `3 * 2 = 6`.
* **Paso 3:** Resolver la suma: `5 + 6 = 11`.
* **Resultado final:** `11`.

### Ejemplo 2: Alterando el orden con paréntesis
```python
resultado = (5 + 3) * 2
```
* **Paso 1:** Los paréntesis `()` tienen la máxima prioridad.
* **Paso 2:** Resolver lo que está dentro del paréntesis: `5 + 3 = 8`.
* **Paso 3:** Resolver la multiplicación: `8 * 2 = 16`.
* **Resultado final:** `16`.

### Ejemplo 3: Expresión combinada
```python
resultado = 10 + 2 ** 3 / 4 - 1
```
* **Paso 1 (Potencia):** `2 ** 3 = 8`. La expresión queda: `10 + 8 / 4 - 1`.
* **Paso 2 (División):** `8 / 4 = 2.0`. La expresión queda: `10 + 2.0 - 1`.
* **Paso 3 (Suma/Resta de izq. a der.):** `10 + 2.0 = 12.0`, luego `12.0 - 1 = 11.0`.
* **Resultado final:** `11.0`.

---

## 5. Ejercicios Prácticos de Jerarquía

Intenta calcular mentalmente o en papel el resultado de las siguientes expresiones antes de ejecutarlas en Python:

1. `resultado1 = 12 - 4 + 2`
2. `resultado2 = 10 + 5 * 2 ** 2`
3. `resultado3 = (10 + 5) * (8 // 3)`
4. `resultado4 = 17 % 5 + 3 * 2`
