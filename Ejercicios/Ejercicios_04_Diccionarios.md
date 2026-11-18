# 10 Ejercicios Prácticos de Diccionarios en Python (`dict`)

Ejercicios están diseñados para practicar la creación, lectura, actualización, eliminación y recorrido de diccionarios en escenarios cotidianos.

---

### **1. Agenda de Contactos Telefónicos**
Crea un diccionario llamado `agenda` con tres contactos iniciales donde la clave sea el nombre de la persona y el valor sea su número telefónico (por ejemplo: `{"Ana": "555-1234", "Luis": "555-5678", "Marta": "555-9012"}`). Escribe un programa que pida al usuario un nombre por teclado, busque el teléfono usando el método `.get()` e imprima el número correspondiente o el mensaje `"Contacto no encontrado"` si no existe.

---

### **2. Control de Inventario de Tienda**
Una tienda tiene el siguiente inventario: `inventario = {"manzanas": 50, "platanos": 30, "naranjas": 20}`. Un cliente compra 12 manzanas y llegan 15 naranjas nuevas del proveedor. Actualiza las cantidades en el diccionario e imprime el inventario actualizado producto por producto mediante un ciclo `for` usando `.items()`.

---

### **3. Calculador de Ticket de Supermercado**
Dado un diccionario con los precios por kilo de varios productos `precios = {"arroz": 25.0, "frijol": 38.5, "azucar": 22.0, "aceite": 45.0}` y una lista con la compra de un cliente `carrito = ["arroz", "aceite", "arroz", "frijol"]`, recorre el carrito, consulta el precio de cada artículo en el diccionario y calcula el monto total a pagar.

---

### **4. Traductor Básico de Idiomas**
Diseña un diccionario Español-Inglés con al menos 6 palabras cotidianas (ej. `{"gato": "cat", "perro": "dog", "casa": "house", ...}`). Solicita al usuario una frase corta en español, sepárala por palabras usando `.split()` y construye una nueva frase traducida palabra por palabra; si una palabra no existe en tu diccionario, consérvala en español.

---

### **5. Contador de Frecuencia de Votos (Urna Electoral)**
En una elección escolar se registraron los siguientes votos en una lista: `votos = ["Ana", "Carlos", "Ana", "Elena", "Carlos", "Ana", "Elena", "Carlos", "Carlos"]`. Crea un diccionario vacío `resultados = {}` y utiliza un ciclo `for` para contar cuántos votos obtuvo cada candidato, almacenando el nombre como clave y el total de votos como valor.

---

### **6. Gestor de Calificaciones de Estudiantes**
Un profesor guarda las notas finales de su grupo en el diccionario `notas = {"Sofía": 9.5, "Diego": 5.8, "Valeria": 8.0, "Mateo": 6.2, "Camila": 10.0}`. Recorre el diccionario para calcular el promedio general del grupo e imprime una lista únicamente con los nombres de los alumnos aprobados (calificación mayor o igual a 7.0).

---

### **7. Actualizador de Perfil de Usuario (Red Social)**
Un usuario tiene el siguiente perfil: `perfil = {"usuario": "dev_alex", "correo": "alex@mail.com", "ciudad": "Madrid", "activo": True}`. El usuario decide cambiar su ciudad a `"Barcelona"`, agregar la clave `"edad"` con el valor `24` y eliminar la clave `"activo"` utilizando `.pop()`. Muestra el diccionario resultante antes y después de los cambios.

---

### **8. Conversor de Divisas en Tiempo Real**
Dada la tabla de tasas de cambio respecto al dólar `tasas = {"MXN": 18.50, "EUR": 0.92, "COP": 4100.0, "ARS": 980.0}`, escribe un programa que solicite al usuario una cantidad en dólares (`USD`) y el código de la moneda destino (`MXN`, `EUR`, etc.). Valida si la moneda existe en el diccionario y muestra el monto convertido.

---

### **9. Catálogo de Productos con Diccionarios Anidados**
Una tienda de electrónica organiza su catálogo usando códigos de producto como claves y diccionarios internos con sus datos:

```python
catalogo = {
    "P01": {"nombre": "Teclado Mecánico", "precio": 1200, "stock": 5},
    "P02": {"nombre": "Mouse Inalámbrico", "precio": 450, "stock": 0},
    "P03": {"nombre": "Monitor 24 pulgadas", "precio": 3500, "stock": 3}
}
```

Recorre el catálogo e imprime únicamente los nombres y precios de los productos que **sí tienen existencia disponible** (`stock > 0`).

---

### **10. Sistema de Inicio de Sesión (Login)**
Crea un diccionario con usuarios registrados y sus contraseñas: `usuarios = {"admin": "1234", "maria_g": "claveSegura", "juan99": "python2026"}`. Solicita al usuario su nombre de usuario y contraseña; verifica mediante el diccionario si el usuario existe y si la contraseña coincide exactamente, mostrando `"Acceso concedido"`, `"Contraseña incorrecta"` o `"Usuario no registrado"` según corresponda.
