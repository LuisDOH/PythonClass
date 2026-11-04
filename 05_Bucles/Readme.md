# Guía Básica de Python: Estructuras de Repetición (Bucles / Loops)

Hasta este momento, nuestros programas han ejecutado el código de arriba a abajo una sola vez. Sin embargo, en la vida real y en la programación, con frecuencia necesitamos **repetir una tarea muchas veces** sin tener que escribir las mismas líneas de código una y otra vez.

Para esto utilizamos las **estructuras de repetición** (también llamadas *bucles*, *ciclos* o *loops*).

---

## 1. El Concepto Fundamental: ¿Por qué necesitamos repetir acciones?

Imagina las siguientes situaciones de la vida real:

* 🏃‍♂️ **Dar 10 vueltas a una pista de carreras:** Repites la acción "dar una vuelta" contando cada una hasta llegar a 10.
* 🔒 **Pedir el PIN de un cajero automático:** El cajero te pide el PIN una y otra vez **MIENTRAS** la clave ingresada sea incorrecta.
* 📱 **Revisar una lista de contactos:** Revisas cada nombre de la lista, uno por uno, de principio a fin.

En Python existen dos tipos de bucles principales para resolver estos problemas:

1. **`while` (Mientras)**: Repite código mientras una condición sea verdadera (útil cuando **NO sabemos** exactamente cuántas veces se repetirá).
2. **`for` (Para)**: Repite código un número determinado de veces o recorre una colección de elementos (útil cuando **SÍ sabemos** cuántas veces queremos repetir algo).

---

## 2. El Bucle `while` (Repetir MIENTRAS se cumpla algo)

La estructura `while` evalúa una condición antes de cada repetición. Si la condición resulta verdadera (`True`), ejecuta las instrucciones del bloque. Cuando la condición se vuelve falsa (`False`), el bucle se detiene.

### Sintaxis Básica

```python
while condicion:
    # Código que se repite mientras la condición sea True
```

### Ejemplo 1: Contador simple del 1 al 5

```python
contador = 1

while contador <= 5:
    print(f"Número de vuelta: {contador}")
    contador = contador + 1  # Incrementamos el contador para no crear un bucle infinito

print("¡Fin del ciclo!")
```

### ⚠️ El Gran Peligro: El Bucle Infinito

Si la condición del `while` **nunca se vuelve falsa**, el programa se quedará ejecutándose para siempre hasta que falle o lo fuerces a cerrarse.

```python
# ❌ ERROR COMÚN: Olvidar cambiar la variable de control
x = 1
while x <= 5:
    print("¡Ayuda, no me detengo!")
    # Olvidamos poner: x = x + 1
```

### Ejemplo 2: Validar un dato ingresado por el usuario

Un uso muy común del `while` es obligar al usuario a ingresar un dato válido antes de continuar:

```python
contrasena_correcta = "python123"
intento = input("Ingresa la contraseña: ")

# MIENTRAS la contraseña ingresada sea distinta a la correcta, volvemos a pedirla
while intento != contrasena_correcta:
    print("❌ Contraseña incorrecta. Inténtalo de nuevo.\n")
    intento = input("Ingresa la contraseña: ")

print(" Accesso concedido al sistema.")
```

---

## 3. El Bucle `for` y la Función `range()`

El bucle `for` en Python se utiliza principalmente para iterar (recorrer) sobre una secuencia fija de elementos o números.

### A. La función `range()`

Para repetir algo un número exacto de veces, combinamos `for` con la función `range()`.

| Formato de `range()` | ¿Qué valores genera? | Ejemplo |
| :--- | :--- | :--- |
| `range(limite)` | Desde `0` hasta `limite - 1` | `range(5)` $\rightarrow$ `0, 1, 2, 3, 4` |
| `range(inicio, fin)` | Desde `inicio` hasta `fin - 1` | `range(1, 6)` $\rightarrow$ `1, 2, 3, 4, 5` |
| `range(inicio, fin, paso)` | Salta de `paso` en `paso` | `range(2, 11, 2)` $\rightarrow$ `2, 4, 6, 8, 10` |

### Ejemplo 1: Repetir una tarea 5 veces

```python
for i in range(5):
    print(f"Ejecutando iteración número {i}")
```

> **Nota:** La variable `i` (abreviación de *índice* o *iterador*) toma un valor nuevo en cada vuelta automáticamente. No necesitas incrementarla manualmente como en el `while`.

### Ejemplo 2: Tabla de multiplicar de un número

```python
numero = int(input("¿De qué número quieres la tabla de multiplicar?: "))

print(f"\n--- Tabla del {numero} ---")
for i in range(1, 11):
    resultado = numero * i
    print(f"{numero} x {i} = {resultado}")
```

### Ejemplo 3: Contar en reversa (Despegue de un cohete)

```python
print("Iniciando cuenta regresiva:")

for conteo in range(10, 0, -1):
    print(conteo)

print("🚀 ¡Despegue!")
```

---

## 4. Control de Bucles: `break` y `continue`

Existen dos instrucciones especiales que nos permiten alterar el flujo normal de cualquier bucle:

### A. `break` (Interrumpir / Salir del ciclo)
Detiene inmediatamente el bucle por completo, sin importar si la condición sigue siendo verdadera.

```python
print("Buscando el número 7...")

for numero in range(1, 10):
    if numero == 7:
        print("¡Encontrado! Deteniendo la búsqueda.")
        break  # Rompe el ciclo for
    print(f"Revisando el número {numero}...")
```

### B. `continue` (Saltar a la siguiente vuelta)
Omite el resto del código de la vuelta actual y salta de inmediato a la siguiente iteración.

```python
# Imprimir solo números impares omitiendo los pares
for i in range(1, 6):
    if i % 2 == 0:
        continue  # Si es par, se salta el print y pasa al siguiente número
    print(f"Número impar: {i}")
```

---

## 5. Comparativa Rápida: ¿Cuál bucle debo utilizar?

| Criterio | Usar Bucle `while` | Usar Bucle `for` |
| :--- | :--- | :--- |
| **Número de repeticiones** | Desconocido de antemano | Conocido previamente |
| **Condición de paro** | Depende de un evento (ej. lo que escriba el usuario) | Depende de un límite numérico o una lista |
| **Control de variable** | Requiere actualizar manualmente la variable | Se actualiza automáticamente |
| **Ejemplo típico** | "Pedir la clave hasta que sea correcta" | "Imprimir la lista de los primeros 100 números" |

---

## 6. Ejercicios Prácticos para la Clase

Intenta escribir el código en Python para resolver estos problemas:

1. **El Acumulador de Ahorros (`while`):**  
   Pide al usuario una meta de ahorro (por ejemplo, \$1,000). Luego, utiliza un `while` para pedir continuamente montos ahorrados y sumarlos hasta que el acumulado sea mayor o igual a la meta establecida. Muestra un aviso de felicitación al terminar.

2. **La Suma de los Primeros N Números (`for`):**  
   Pide al usuario un número entero `N` positivo. Utiliza un bucle `for` con `range()` para calcular e imprimir la suma de todos los números enteros desde el 1 hasta `N` (ejemplo: si el usuario ingresa `5`, debe calcular `1 + 2 + 3 + 4 + 5 = 15`).
