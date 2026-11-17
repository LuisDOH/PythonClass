# Guía Completa de Diccionarios en Python (`dict`)

## 1. Definición y Conceptos Fundamentales

En Python, un **diccionario** (`dict`) es una estructura de datos nativa que almacena información en pares de **clave-valor** (*key-value*). A diferencia de las listas o tuplas, que se indexan mediante un rango numérico secuencial (`0, 1, 2...`), los diccionarios se indexan mediante **claves únicas**, las cuales actúan como etiquetas identificadoras para acceder rápidamente a su valor asociado.

### Características Principales
* **Mutables:** Se pueden añadir, modificar y eliminar elementos después de su creación.
* **Ordenados (desde Python 3.7+):** Mantienen el orden exacto en el que fueron insertados los elementos.
* **Claves Únicas e Inmutables:** No pueden existir dos claves idénticas dentro del mismo diccionario. Además, las claves deben ser de un tipo de dato inmutable (como `str`, `int`, `float` o `tuple`).
* **Valores Flexibles:** Los valores asociados a las claves pueden ser de cualquier tipo de dato (números, cadenas, listas, booleanos, funciones e incluso otros diccionarios).
* **Alto Rendimiento:** Internamente utilizan **tablas hash**, lo que permite buscar, insertar o eliminar datos en tiempo constante $\mathcal{O}(1)$, independientemente de si el diccionario tiene 10 o 10 millones de registros.

### Sintaxis Básica
Se definen encerrando los pares `clave: valor` entre llaves `{}` y separándolos por comas:

```python
# Diccionario vacío
diccionario_vacio = {}
otro_vacio = dict()

# Diccionario con datos
empleado = {
    "id": 1042,
    "nombre": "Laura Martínez",
    "puesto": "Desarrolladora Backend",
    "activo": True,
}
```

---

## 2. Aplicaciones en el Mundo Real

Los diccionarios son una de las estructuras más utilizadas en el desarrollo de software profesional debido a su similitud con formatos estándar de intercambio de datos (como **JSON**).

1. **Representación de Objetos y Registros:** Modelar entidades como perfiles de usuario, fichas de productos en un e-commerce o datos de un estudiante.
2. **Consumo y Creación de APIs Web:** La gran mayoría de servicios web intercambian información en formato JSON, el cual se traduce directamente a diccionarios en Python.
3. **Contadores y Agrupación de Datos:** Contar la frecuencia de palabras en un texto, agrupar ventas por categoría o tabular resultados de encuestas.
4. **Caché y Tablas de Búsqueda (Lookup Tables):** Almacenar resultados de operaciones costosas o configuraciones del sistema para acceder a ellas de forma instantánea mediante su identificador.
5. **Configuraciones de Aplicaciones:** Guardar parámetros de conexión a bases de datos, credenciales o preferencias de usuario.

---

## 3. Operaciones Básicas: Leer, Modificar y Eliminar

### A. Cómo Leer Información

#### 1. Acceso directo mediante corchetes `[]`
Es la forma más rápida, pero **arroja un error (`KeyError`) si la clave no existe**.
```python
usuario = {"nombre": "Carlos", "edad": 28}
print(usuario["nombre"])  # Salida: Carlos
# print(usuario["correo"]) -> Lanza KeyError
```

#### 2. Acceso seguro mediante el método `.get()`
Es la práctica recomendada cuando no estamos seguros de si la clave existe. Si no la encuentra, devuelve `None` (o un valor por defecto que especifiquemos) en lugar de detener el programa.
```python
print(usuario.get("edad"))                        # Salida: 28
print(usuario.get("correo"))                      # Salida: None
print(usuario.get("correo", "No registrado"))     # Salida: No registrado
```

---

### B. Cómo Añadir y Modificar Información

La sintaxis para agregar un nuevo par clave-valor y para actualizar uno existente es exactamente la misma: **si la clave no existe, Python la crea; si ya existe, sobrescribe su valor**.

#### 1. Asignación directa con `[]`
```python
producto = {"nombre": "Teclado", "precio": 500}

# Añadir una nueva clave
producto["stock"] = 15

# Modificar una clave existente
producto["precio"] = 450

print(producto)
# Salida: {'nombre': 'Teclado', 'precio': 450, 'stock': 15}
```

#### 2. Actualización masiva con `.update()`
Permite fusionar otro diccionario o actualizar múltiples claves en una sola instrucción.
```python
producto.update({"precio": 420, "marca": "Logitech"})
print(producto)
# Salida: {'nombre': 'Teclado', 'precio': 420, 'stock': 15, 'marca': 'Logitech'}
```

---

### C. Cómo Eliminar Información

#### 1. Palabra reservada `del`
Elimina un par clave-valor específico. Lanza `KeyError` si la clave no existe.
```python
datos = {"a": 1, "b": 2, "c": 3}
del datos["b"]
print(datos)  # Salida: {'a': 1, 'c': 3}
```

#### 2. Método `.pop(clave, valor_por_defecto)`
Elimina la clave indicada **y devuelve su valor** para que puedas guardarlo o procesarlo. Si se pasa un segundo argumento, evita el error en caso de que la clave no exista.
```python
valor_eliminado = datos.pop("c")
print(valor_eliminado)  # Salida: 3
print(datos)            # Salida: {'a': 1}
```

#### 3. Método `.popitem()`
Elimina y devuelve en forma de tupla `(clave, valor)` el **último elemento insertado** en el diccionario.
```python
registro = {"x": 10, "y": 20}
ultimo = registro.popitem()
print(ultimo)    # Salida: ('y', 20)
print(registro)  # Salida: {'x': 10}
```

#### 4. Método `.clear()`
Vacía por completo el diccionario, dejándolo en `{}`.
```python
registro.clear()
print(registro)  # Salida: {}
```

---

## 4. Métodos Más Utilizados

| Método | Descripción | Ejemplo de Uso |
| :--- | :--- | :--- |
| **`.keys()`** | Devuelve una vista iterable con todas las **claves** del diccionario. | `for k in d.keys():` |
| **`.values()`** | Devuelve una vista iterable con todos los **valores** del diccionario. | `for v in d.values():` |
| **`.items()`** | Devuelve una vista iterable de tuplas `(clave, valor)`. Es el método estándar para iterar ambos datos a la vez. | `for k, v in d.items():` |
| **`.get(clave, default)`** | Obtiene el valor de una clave de forma segura sin lanzar excepciones si no existe. | `d.get("rol", "Invitado")` |
| **`.update(otro_dict)`** | Actualiza el diccionario con los pares clave-valor de otro diccionario u objeto iterable. | `d.update({"activo": False})` |
| **`.setdefault(clave, default)`** | Si la clave existe, devuelve su valor. Si **no** existe, la inserta con el valor por defecto indicado y lo devuelve. | `d.setdefault("puntos", 0)` |
| **`.copy()`** | Crea una copia superficial (*shallow copy*) independiente del diccionario original. | `copia = d.copy()` |
| **`dict.fromkeys(seq, val)`** | Método de clase que crea un nuevo diccionario usando una secuencia como claves y asignando a todas el mismo valor inicial. | `dict.fromkeys(["a", "b"], 0)` |

---

## 5. Iteración y Patrones Comunes

### Iterar sobre claves, valores o ambos
```python
calificaciones = {"Matemáticas": 9.5, "Historia": 8.0, "Física": 9.0}

# 1. Iterar solo claves (comportamiento por defecto)
for materia in calificaciones:
    print(materia)

# 2. Iterar solo valores
for nota in calificaciones.values():
    print(nota)

# 3. Iterar clave y valor simultáneamente (Más común)
for materia, nota in calificaciones.items():
    print(f"En {materia} obtuviste {nota}")
```

### Verificar existencia de una clave (`in`)
```python
if "Física" in calificaciones:
    print("La materia está registrada.")
```
```
