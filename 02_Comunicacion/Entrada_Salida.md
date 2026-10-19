# ¿Cómo se comunica la computadora con nosotros?

Hasta ahora hemos visto cómo guardar datos dentro de "cajas" llamadas variables. Pero, ¿cómo interactuamos con el programa?

Para que un programa sea útil, necesita **comunicarse**:
1. **Hablar con nosotros:** Mostrarnos mensajes, resultados o preguntas en la pantalla.
2. **Escucharnos:** Pedirnos datos que nosotros escribimos desde el teclado.

En Python, hacemos esto con dos instrucciones fundamentales: `print()` e `input()`.

---

## 1. Mostrar mensajes en pantalla: La función `print()`

La palabra *print* significa "imprimir" en inglés. En programación, usar `print()` significa **mostrar un mensaje en la pantalla del usuario**.

### Sintaxis básica
Para que Python muestre algo, escribes `print` seguido de paréntesis `()`. Lo que quieras mostrar va **dentro** de los paréntesis:

```python
print("¡Hola, mundo!")
```

Si ejecutas esta línea, verás en pantalla:
> ¡Hola, mundo!

---

### ¿Qué podemos mostrar con `print()`?

#### A. Texto directo (Strings)
Si quieres mostrar un texto tal cual, **debes ponerlo entre comillas** (simples `'...'` o dobles `"..."`).

```python
print("Bienvenido a tu primera clase de programación.")
```

#### B. El contenido de una variable
Si quieres mostrar lo que hay guardado en una variable, **NO usas comillas**. Pon únicamente el nombre de la variable.

```python
nombre = "Lucía"
print(nombre)
```
> **Salida en pantalla:**  
> Lucía

> ⚠️ **Atención:**  
> * `print("nombre")` mostrará la palabra literal **nombre**.  
> * `print(nombre)` mostrará lo que está guardado dentro de la variable (en este caso, **Lucía**).

#### C. Combinar texto y variables
A menudo querrás combinar texto fijo con el contenido de una variable. Hay dos formas muy sencillas de hacerlo:

1. **Usando comas `,` (Método clásico y fácil):**
   La coma une elementos y les añade un espacio automáticamente.

   ```python
   edad = 15
   print("Tienes", edad, "años.")
   ```
   > **Salida:** Tienes 15 años.

2. **Usando f-strings (Formato moderno y recomendado):**
   Colocas una letra `f` antes de las comillas y metes la variable dentro de llaves `{}`.

   ```python
   nombre = "Carlos"
   edad = 16
   print(f"Hola {nombre}, tu edad es {edad} años.")
   ```
   > **Salida:** Hola Carlos, tu edad es 16 años.

---

## 2. Pedir datos al usuario: La función `input()`

Ahora aprenderemos a hacer que la computadora nos escuche. La función `input()` hace una pausa en el programa y **espera a que el usuario escriba algo en el teclado y presione la tecla Enter**.

### Sintaxis básica

```python
input("Escribe tu nombre: ")
```

Cuando Python lee esa línea:
1. Muestra en pantalla el texto `"Escribe tu nombre: "`.
2. Se queda esperando a que el usuario responda.

---

### Guardar lo que el usuario responde
Si usas `input()` solo, lo que el usuario escriba se perderá. Para recordarlo, **debemos guardar la respuesta en una variable**:

```python
# Guardamos la respuesta del usuario en la variable 'nombre_usuario'
nombre_usuario = input("¿Cómo te llamas? ")

# Ahora podemos saludarlo usando 'print'
print(f"¡Mucho gusto, {nombre_usuario}!")
```

---

## 3. El gran detalle de `input()`: ¡Todo lo lee como Texto!

Este es el tro Tropiezo número 1 de todo principiante en programación:

> 🚨 **REGLA DE ORO:**  
> Todo lo que entra por `input()` se guarda siempre como una **cadena de texto (`str`)**, incluso si el usuario digita números.

### El problema:

```python
# Imaginemos este ejemplo:
edad = input("¿Cuántos años tienes? ")
# Si el usuario escribe 15, Python guarda "15" (texto, no número).

# Si intentas sumar números con texto, Python fallará o hará algo extraño:
siguiente_edad = edad + 1  # ❌ ¡DARA ERROR! No se puede sumar texto + número.
```

---

### La solución: Convertir tipos de datos (*Type Casting*)

Si le pides al usuario un número (edad, precio, cantidad) y vas a hacer operaciones matemáticas con él, debes **convertir** el resultado de `input()` usando `int()` (para enteros) o `float()` (para decimales).

#### Ejemplo para Números Enteros (`int`):

```python
# Encapsulamos el input() dentro de int()
edad = int(input("¿Cuántos años tienes? "))

# Ahora 'edad' sí es un número real
edad_futura = edad + 1
print(f"El próximo año tendrás {edad_futura} años.")
```

#### Ejemplo para Números con Decimales (`float`):

```python
precio = float(input("¿Cuánto cuesta el producto? "))
descuento = precio - 5.0
print(f"Con descuento te queda en: ${descuento}")
```

---

## 4. Unir todo: Tu primer programa interactivo

A continuación vemos un ejemplo donde combinamos **variables, input, conversiones y print**:

```python
# 1. Entrada de datos
nombre = input("Escribe tu nombre: ")
horas_estudio = int(input("¿Cuántas horas estudias a la semana? "))

# 2. Procesamiento (cálculo)
horas_al_mes = horas_estudio * 4

# 3. Salida de datos
print("----------------------------------------")
print(f"¡Hola, {nombre}!")
print(f"Estudias aproximadamente {horas_al_mes} horas al mes. ¡Buen trabajo!")
print("----------------------------------------")
```

---

## 5. Ejercicios Prácticos

Escribe un programa en Python para cada uno de los siguientes retos:

1. **El Saludador:** Pide al usuario su nombre y su color favorito. Luego muestra un mensaje que diga: `"Hola [Nombre], tu color favorito es el [Color]!"`.
2. **Calculadora de Edad Doble:** Pide al usuario su edad actual. Calcula el doble de su edad y muéstraselo en un mensaje amigable.
3. **Conversor de Moneda Simplificado:** Pide al usuario una cantidad en dólares (puede llevar decimales). Multiplícala por la tasa de cambio local y muestra cuántos pesos equivale.
