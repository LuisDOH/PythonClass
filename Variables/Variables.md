# Variables y Tipos de Datos Primitivos

## 1. ¿Qué es una Variable?

Piensa en una **variable** como una caja etiquetada donde puedes guardar un valor o un dato para usarlo o modificarlo más adelante en tu programa. 

En Python, crear una variable es muy sencillo: solo necesitas elegir un nombre para la caja, usar el operador de asignación (`=`) y escribir el valor que quieres guardar dentro.

```python
# Creación de variables
edad = 20
nombre = "Sofia"
```


### Reglas obligatorias para nombrar variables en Python

Para que Python entienda tu código sin lanzar errores, debes seguir las siguientes **reglas estrictas**:

1. **Letras, números y guiones bajos:** El nombre solo puede contener letras (`a-z`, `A-Z`), números (`0-9`) y el guión bajo (`_`).
2. **No puede comenzar con un número:** Un nombre de variable válido puede empezar con una letra o un guión bajo, pero **nunca** con un dígito.
   * `1nombre` (Entrará en error)
   * `nombre1` (Correcto)
3. **Sensible a mayúsculas y minúsculas (*Case-sensitive*):** Las variables `edad`, `Edad` y `EDAD` son tres variables completamente diferentes para Python, tan solo por el hecho de no tener las misma mayúsculas y minúsculas.

4. **Sin palabras reservadas:** No puedes usar palabras que Python ya utiliza para sus propias instrucciones (como `if`, `else`, `for`, `while`, `import`, `class`, `def`, `print`, `input`  etc.).

---

### Buenas prácticas y convenciones del mercado (*Snake Case*)

Además de las reglas obligatorias, la comunidad de Python sigue una convención llamada **PEP 8** para escribir código limpio y legible:

* **Usar `snake_case`:** Cuando el nombre de una variable tenga dos o más palabras, júntalas usando guiones bajos y solo letras minúsculas.
  * `primer_nombre` (Recomendado)
  * `primerNombre` (Funciona, pero no es el estándar en Python)
* **Nombres descriptivos:** El nombre de la variable debe indicar claramente qué dato contiene. Evita usar nombres de una sola letra salvo para ciclos cortos.
  * `precio_total = 150.50` (Excelente)
  * `x = 150.50` (Poco claro)

---

## 2. Tipos de Datos Primitivos en Python

Python asigna automáticamente un **tipo de dato** a cada variable según el valor que le guardes. Los cuatro tipos de datos numéricos y de texto básicos son:

### A. Enteros (`int`)
Representan números enteros, positivos o negativos, sin parte decimal.

* **Uso típico:** Conteo de objetos, edades, años, cantidad de elementos.
```python
cantidad_alumnos = 25
temperatura_grados = -5
anio_actual = 2026
```

---

### B. Flotantes / Decimales (`float`)
Representan números reales que contienen un punto decimal.

* **Uso típico:** Precios, estaturas, promedios, porcentajes.
* **Nota importante:** En Python se utiliza el **punto (`.`)** como separador decimal, no la coma.
```python
precio_producto = 49.99
estatura_metros = 1.75
promedio_calificaciones = 9.4
```

---

### C. Cadenas de Texto (`str` - *Strings*)
Representan secuencias de texto. Se definen envolviendo el texto entre comillas simples (`'...'`) o comillas dobles (`"..."`).

* **Uso típico:** Nombres, correos electrónicos, mensajes, direcciones.
```python
nombre_usuario = "Carlos Alberto"
mensaje_bienvenida = '¡Hola a todos!'
correo_contacto = "estudiante@ejemplo.com"
```

---

### D. Booleanos (`bool`)
Representan valores de verdad o lógica. Solo pueden tener dos valores posibles: `True` (Verdadero) o `False` (Falso).

* **Uso típico:** Banderas de estado, validación de condiciones, interruptores.
* **Nota importante:** Deben escribirse obligatoriamente con la primera letra en mayúscula (`True` / `False`).
```python
es_mayor_de_edad = True
curso_completado = False
usuario_activo = True
```

---

## 3. Descubriendo el Tipo de Dato: La función `type()`

Si quieres saber qué tipo de dato tiene guardado una variable, puedes usar la función integrada `type()` combinada con `print()`:

```python
# Ejemplos de verificación de tipo
edad = 22
precio = 19.50
saludo = "Hola"
es_estudiante = True

print(type(edad))          # Salida: <class 'int'>
print(type(precio))        # Salida: <class 'float'>
print(type(saludo))        # Salida: <class 'str'>
print(type(es_estudiante))  # Salida: <class 'bool'>
```

Note que estamos usando el comando `print` que nos permite mostrar cosas en la consola, pero dentro de el estamos usando el otro comando `type`.
Es como si le pidieramos a `type` que investigue el tipo de dato y luego el resultado nos lo muestre usando el comando `print`. 

---

## 4. Resumen Visual para Recordar

| Tipo de Dato | Tipo en Python | Ejemplo de Valor | Descripción Breve |
| :--- | :--- | :--- | :--- |
| **Entero** | `int` | `10`, `-30` | Números sin punto decimal |
| **Flotante** | `float` | `3.1416`, `-0.5` | Números con punto decimal |
| **Cadena (String)** | `str` | `"Hola"`, `'Python'` | Texto entre comillas |
| **Booleano** | `bool` | `True`, `False` | Valores lógicos |

---

## 5. Ejercicio Práctico para la Clase

Instrucciones: Analiza las siguientes variables e identifica cuáles cumplen las reglas de Python y cuáles generan un error. Si generan error, explica por qué.

1. `1er_lugar = "Oro"`
2. `nombre_estudiante = "Ana"`
3. `promedio-final = 8.5`
4. `class = "Matemáticas"`
5. `EsEstudiante = True`

