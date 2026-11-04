# Guía Completa de Python: Operadores Lógicos (`and`, `or`, `not`)

Los **operadores lógicos** (también conocidos como operadores booleanos) permiten combinar múltiples condiciones en una sola expresión. Son la herramienta fundamental para construir razonamientos complejos y tomar decisiones sofisticadas en programación.

---

## 1. Conceptos Fundamentales

Los operadores lógicos trabajan con valores booleanos (`True` o `False`). Reciben una o varias condiciones evaluadas como verdaderas o falsas y devuelven un único resultado booleano.

En Python, disponemos de tres operadores lógicos escritos en inglés simple:

1. **`and`** (Y lógico / Conjunción)
2. **`or`** (O lógico / Disyunción)
3. **`not`** (NO lógico / Negación)

---

## 2. Detalle de los Operadores Lógicos

### A. Operador `and` (Y Lógico)

El operador `and` evalúa dos expresiones y devuelve **`True` únicamente cuando AMBAS condiciones son verdaderas**. Si al menos una de las condiciones es `False`, el resultado final será `False`.

#### Tabla de Verdad del `and`:

| Condición A | Condición B | `A and B` | Explicación |
| :---: | :---: | :---: | :--- |
| `True` | `True` | **`True`** | Ambas se cumplen. |
| `True` | `False` | **`False`** | Una de las dos no se cumple. |
| `False` | `True` | **`False`** | Una de las dos no se cumple. |
| `False` | `False` | **`False`** | Ninguna se cumple. |

#### Ejemplo del Mundo Real:
> *"Para abordar un avión necesitas presentar tu pase de abordar **Y** tu identificación oficial."*

```python
tiene_pase = True
tiene_identificacion = True

# Ambas deben ser True
puede_abordar = tiene_pase and tiene_identificacion
print("¿Puede abordar?:", puede_abordar)  # Devuelve: True
```

---

### B. Operador `or` (O Lógico)

El operador `or` evalúa dos expresiones y devuelve **`True` si AL MENOS UNA de las condiciones es verdadera**. Solo devolverá `False` cuando **todas** las condiciones evaluadas sean falsas.

#### Tabla de Verdad del `or`:

| Condición A | Condición B | `A or B` | Explicación |
| :---: | :---: | :---: | :--- |
| `True` | `True` | **`True`** | Ambas se cumplen. |
| `True` | `False` | **`True`** | Al menos una se cumple. |
| `False` | `True` | **`True`** | Al menos una se cumple. |
| `False` | `False` | **`False`** | Ninguna se cumple. |

#### Ejemplo del Mundo Real:
> *"Tienes descuento en la tienda si pagas con tarjeta de crédito de la tienda **O** si cuentas con un cupón promocional."*

```python
es_tarjeta_tienda = False
tiene_cupon = True

# Basta con que una sea True
aplica_descuento = es_tarjeta_tienda or tiene_cupon
print("¿Aplica descuento?:", aplica_descuento)  # Devuelve: True
```

---

### C. Operador `not` (NO Lógico / Negación)

El operador `not` es un operador **unario** (funciona con un solo operando). Su función es **invertir el valor booleano** del resultado: convierte `True` en `False` y `False` en `True`.

#### Tabla de Verdad del `not`:

| Condición A | `not A` | Explicación |
| :---: | :---: | :--- |
| `True` | **`False`** | Invierte el valor verdadero a falso. |
| `False` | **`True`** | Invierte el valor falso a verdadero. |

#### Ejemplo del Mundo Real:
> *"El sistema de alarma suena si la puerta **NO** está cerrada."*

```python
puerta_cerrada = False

# Invierte el estado de la variable
sonar_alarma = not puerta_cerrada
print("¿Sonar alarma?:", sonar_alarma)  # Devuelve: True
```

---

## 3. Evaluación en Cortocircuito (*Short-Circuit Evaluation*)

Python utiliza un mecanismo de optimización llamado **evaluación en cortocircuito**:

1. **En expresiones con `and`:** Si la primera condición evalúa a `False`, Python **detiene la evaluación de inmediato** y devuelve `False`, sin importar el resultado de la segunda condición (ya que es imposible que el resultado sea `True`).
2. **En expresiones con `or`:** Si la primera condición evalúa a `True`, Python **detiene la evaluación de inmediato** y devuelve `True`, sin revisar la segunda condición.

### Ejemplo práctico del cortocircuito:

```python
divisor = 0
numero = 10

# Gracias al cortocircuito, Python no evalúa (numero / divisor) si divisor == 0,
# evitando un error fatal de división por cero (ZeroDivisionError).
if divisor != 0 and (numero / divisor > 2):
    print("Resultado válido")
else:
    print("Operación no permitida o divisor es cero.")
```

---

## 4. Combinación y Precedencia de Operadores Lógicos

Cuando se combinan múltiples operadores lógicos en una sola línea, Python los evalúa siguiendo un orden jerárquico estricto:

### Orden de Prioridad (Precedencia):
1. **`()`** Paréntesis (alteran el orden predeterminado)
2. Operadores relacionales (`==`, `!=`, `>`, `<`, `>=`, `<=`)
3. **`not`**
4. **`and`**
5. **`or`**

### Ejemplo de Evaluación Paso a Paso:

Dada la siguiente expresión:
```python
resultado = True or False and not True
```

1. Evalúa **`not`**: `not True` $\rightarrow$ `False`
   - Expresión actual: `True or False and False`
2. Evalúa **`and`**: `False and False` $\rightarrow$ `False`
   - Expresión actual: `True or False`
3. Evalúa **`or`**: `True or False` $\rightarrow$ **`True`**

> 💡 **Buena Práctica:** Aunque la precedencia está definida, se recomienda **usar siempre paréntesis** para hacer el código más legible y evitar errores de interpretación.

```python
# Mismo resultado, pero mucho más claro para cualquier desarrollador:
resultado = True or (False and (not True))
```

---

## 5. Aplicaciones Prácticas en Sistemas Reales

### A. Validación de Rango de Valores
Comprobar si un número ingresado se encuentra dentro de un rango determinado (por ejemplo, validar un mes entre 1 y 12):

```python
mes = int(input("Ingresa el número de mes: "))

if mes >= 1 and mes <= 12:
    print("Mes válido.")
else:
    print("Mes inválido. Debe estar entre 1 y 12.")
```

### B. Sistema de Autenticación de Usuarios
Comprobar credenciales de inicio de sesión y el estado de la cuenta:

```python
usuario_correcto = "admin"
clave_correcta = "12345"

input_usuario = input("Usuario: ")
input_clave = input("Contraseña: ")
cuenta_activa = True

if (input_usuario == usuario_correcto and input_clave == clave_correcta) and cuenta_activa:
    print("¡Acceso concedido!")
else:
    print("Credenciales incorrectas o cuenta suspendida.")
```

### C. Filtro de Requisitos Múltiples (Becas Universitarias)
Otorgar una beca si el estudiante tiene promedio sobresaliente **O** ingresos bajos, siempre y cuando **NO** tenga materias reprobadas:

```python
promedio = 9.5
ingresos_bajos = False
materias_reprobadas = False

# Cumple condición académica/económica Y no tiene reprobadas
elegible = (promedio >= 9.0 or ingresos_bajos) and not materias_reprobadas

if elegible:
    print("Beca aprobada.")
else:
    print("No cumple con los requisitos de la beca.")
```

---

## 6. Errores Comunes de Principiantes

### Error 1: Confundir lenguaje natural con sintaxis de Python

* ❌ **Incorrecto:** `if opcion == "a" or "b":`  
  *(En Python, `"b"` no vacía se evalúa siempre como `True`, haciendo que el `if` siempre se cumpla).*
* ✅ **Correcto:** `if opcion == "a" or opcion == "b":`

### Error 2: Negar condiciones complejas sin usar paréntesis

* ❌ **Incorrecto:** `if not edad >= 18 and tiene_permiso:`  
  *(Solo niega `edad >= 18`, no toda la expresión).*
* ✅ **Correcto:** `if not (edad >= 18 and tiene_permiso):`

---

## 7. Ejercicios de Repaso (Evaluación de Expresiones)

Determina el valor resultante (`True` o `False`) de las siguientes expresiones sin ejecutarlas en Python:

1. `expresion1 = (5 > 3) and (8 < 12)`
2. `expresion2 = not (10 == 10 or 5 > 20)`
3. `expresion3 = (True and False) or (not False)`
4. `expresion4 = (15 != 15) or (3 * 2 == 6 and not False)`
