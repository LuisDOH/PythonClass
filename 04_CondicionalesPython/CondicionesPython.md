# Guía Básica de Python: Tomando Decisiones con Condicionales

En los programas de computadora, por defecto las instrucciones se ejecutan de arriba hacia abajo, una tras otra. Sin embargo, en la vida real y en los programas útiles, necesitamos **tomar decisiones** según las circunstancias.

En Python, tomamos decisiones utilizando las **estructuras condicionales**: `if`, `elif` y `else`.

---

## 1. El Concepto Fundamental: ¿Qué es una Condición?

Imagina cómo tomas decisiones en tu vida diaria antes de salir de casa:

> 🌧️ **"SI está lloviendo, ENTONCES me llevo un paraguas. DE LO CONTRARIO, me voy con lentes de sol."**

Eso es exactamente una **estructura condicional**. No es más que una pregunta con dos posibles respuestas:
1. **Verdadero (`True`)**: Ocurrió la condición, ejecutamos el Plan A.
2. **Falso (`False`)**: No ocurrió la condición, ejecutamos el Plan B (o no hacemos nada).

En programación, le enseñamos a la computadora a hacerse esas mismas preguntas para que adapte sus acciones según las entradas del usuario o los datos recibidos.

### Diagrama de Flujo de Decisiones

```text
                   ¿Está lloviendo?
                          |
             +------------+------------+
             |                         |
         [ SÍ / True ]             [ NO / False ]
             |                         |
    Llevar paraguas           Llevar lentes de sol
             |                         |
             +------------+------------+
                          |
                   Salir de casa
```

---

## 2. La Estructura Básica: `if` (El "SI..." condicional)

La palabra clave `if` en Python le dice a la computadora: *"Revisa esta condición. Si resulta verdadera, ejecuta este bloque de código."*

### Sintaxis básica

```python
if condicion:
    # Código que se ejecuta SOLO si la condición es True
```

### ⚠️ Regla Crucial en Python: La Indentación (Sangría)

A diferencia de otros lenguajes de programación que usan corchetes `{}` o palabras como `end` para delimitar bloques, Python utiliza la **sangría / indentación** (habitualmente 4 espacios o una tecla `Tab`). 

Todo el código inclinado a la derecha pertenece al bloque que depende del `if`.

```python
edad = 20

# Pregunta que hace Python: ¿La edad es mayor o igual a 18?
if edad >= 18:
    print("Acceso permitido.")
    print("Bienvenido al sistema de votación.")  # Esta línea está DENTRO del if

print("Gracias por visitar nuestro sitio.")      # Esta línea está FUERA del if y se ejecuta siempre
```

---

## 3. La Alternativa: `else` (El "DE LO CONTRARIO...")

El bloque `else` es la respuesta por defecto de tu programa. Se ejecuta **únicamente cuando la condición del `if` fue Falsa (`False`)**. No requiere evaluar una condición propia porque captura cualquier caso no cubierto.

### Piénsalo así:
- **`if`**: Si la clave es correcta ➡️ Abre la puerta.
- **`else`**: De lo contrario ➡️ Muestra un mensaje de "Clave incorrecta".

### Ejemplo paso a paso:

```python
edad = int(input("¿Cuántos años tienes?: "))

if edad >= 18:
    # Se ejecuta si el usuario ingresa 18 o un número mayor
    print("Eres mayor de edad. Puedes entrar.")
else:
    # Se ejecuta si el usuario ingresa un número menor a 18
    print("Eres menor de edad. Necesitas la compañía de un tutor.")
```

---

## 4. Múltiples Opciones en Cadena: `elif` (El "SI NO SE CUMPLIÓ LO ANTERIOR, PERO SI...")

¿Qué pasa cuando no tenemos solo dos alternativas (Sí/No), sino muchas posibilidades? Para eso existe `elif` (una abreviación de *else if*).

Permite evaluar opciones **en orden estricto de arriba hacia abajo**. Tan pronto como Python encuentra la primera opción verdadera, ejecuta su código y **omite todas las demás**.

### Ejemplo de la Vida Real: El Semáforo

```python
color_semaforo = input("¿De qué color está el semáforo? (verde/amarillo/rojo): ")

if color_semaforo == "verde":
    print("Avanza con seguridad.")
elif color_semaforo == "amarillo":
    print("Prepara tu alto, reduce la velocidad.")
elif color_semaforo == "rojo":
    print("Detente inmediatamente.")
else:
    print("Color no reconocido. Conduce con precaución.")
```

### Ejemplo Práctico: Clasificación por Edades

```python
edad = int(input("Ingresa tu edad: "))

if edad < 3:
    print("Categoría: Bebé (Entrada Gratis)")
elif edad < 12:
    print("Categoría: Niño (Boleto Infantil)")
elif edad < 18:
    print("Categoría: Adolescente (Boleto Joven)")
elif edad < 65:
    print("Categoría: Adulto (Boleto General)")
else:
    print("Categoría: Adulto Mayor (Descuento Especial)")
```

---

## 5. Decisiones Complejas: Operadores Lógicos (`and`, `or`, `not`)

A veces una decisión requiere verificar dos o más condiciones al mismo tiempo. Para esto combinamos las condiciones con operadores lógicos.

### A. El operador `and` (Requiere que TODAS las condiciones sean Verdaderas)
> *"Para subir a la atracción necesitas medir más de 1.40 m **Y** ser mayor de 10 años."*

```python
estatura = 1.50
edad = 12

if estatura >= 1.40 and edad >= 10:
    print("¡Puedes subir a la atracción! 🎢")
else:
    print("No cumples con los requisitos de seguridad.")
```

### B. El operador `or` (Requiere que AL MENOS UNA condición sea Verdadera)
> *"Tienes descuento si eres estudiante **O** si posees membresía VIP."*

```python
es_estudiante = False
tiene_membresia = True

if es_estudiante or tiene_membresia:
    print("¡Felicidades! Se aplicó un 20% de descuento.")
else:
    print("Precio regular sin descuento.")
```

---

## 6. Decisiones dentro de Decisiones: Condicionales Anidados

Puedes colocar una estructura `if` dentro de otra. Es útil para realizar comprobaciones por niveles o etapas.

```python
tiene_cuenta = True
contrasena_correcta = False

if tiene_cuenta:
    print("Usuario localizado.")
    # Segunda comprobación (solo se evalúa si la primera fue exitosa)
    if contrasena_correcta:
        print("Acceso concedido al sistema.")
    else:
        print("Contraseña errónea. Inténtalo de nuevo.")
else:
    print("El usuario no existe en la base de datos.")
```

---

## 7. Guía de Referencia Rápida

| Palabra Clave | Significado en Lenguaje Común | ¿Cuándo la uso? |
| :--- | :--- | :--- |
| **`if`** | **"Si se cumple esta condición..."** | Obligatorio. Es la primera comprobación en cualquier decisión. |
| **`elif`** | **"Si no se cumplió la anterior, pero sí esta..."** | Opcional. Úsalo cuando tengas 3 o más alternativas posibles. |
| **`else`** | **"Si no se cumplió ninguna de las anteriores..."** | Opcional. Acción por defecto cuando ninguna otra condición dio `True`. |

---

## 8. Ejercicios Prácticos para Principiantes

Intenta escribir el código en Python para resolver estas situaciones cotidianas:

1. **El Termostato del Clima:**
   Pide al usuario la temperatura actual en grados Celsius:
   - Si es menor a 15°, muestra: *"Hace frío, ponte una chamarra 🧥"*.
   - Si está entre 15° y 28°, muestra: *"El clima está agradable 🌤️"*.
   - Si es mayor a 28°, muestra: *"Hace mucho calor, enciende el aire acondicionado 🥵"*.

2. **Evaluación de Aprobación:**
   Crea un programa que pida la calificación de un examen (del 0 al 10):
   - Si la nota es 6 o más, muestra: *"¡Felicidades, has aprobado!"*.
   - De lo contrario, muestra: *"Lo sentimos, no alcanzaste la nota mínima"*.
