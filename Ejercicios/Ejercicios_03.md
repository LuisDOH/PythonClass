# Ejercicios Prácticos de Python condicionales if-elif-else

A continuacion encontrara algunos ejercicios que deben resolverse utilizando condicionales en Python. Recuerde que:
* **`if` simple**: Para evaluar una condición aislada.
* **`if - else`**: Para tomar una ruta cuando una condición se cumple y otra cuando no.
* **`if - elif - else`**: Para evaluar múltiples categorías, rangos o alternativas posibles.

---

## 🎯 Instrucciones
Para cada uno de los ejercicios:
1. Analiza el escenario del mundo real.
2. Identifica los datos que debes solicitar al usuario mediante `input()`.
3. Determina cuál de las estructuras (`if`, `if-else` o `if-elif-else`) es la adecuada.
4. Escribe el programa en Python asegurándote de usar la indentación correcta (4 espacios).

---

## 📝 Lista de Ejercicios

### 1. Descuento por Compra Mínima (`if` simple)
* **Escenario:** Una boutique ofrece un regalo especial en la caja registradora: si el cliente realiza una compra mayor a $1,000, recibe automáticamente un cupón de $100 para su siguiente visita. Si compra menos de $1,000, simplemente paga su cuenta normalmente.
* **Lógica:** Solicita el monto de la compra. Si es mayor a 1000, muestra el mensaje sobre el cupón otorgado. Al final, imprime siempre el total a pagar.
* **Ejemplo de ejecución:**
  ```text
  Ingresa el monto total de tu compra: 1250
  ¡Felicidades! Has ganado un cupón de $100 para tu próxima compra.
  Gracias por comprar en nuestra boutique. Total a pagar: $1250
  ```

---

### 2. Validador de Mayores de Edad (`if - else`)
* **Escenario:** Un sitio web de videojuegos requiere validar si un usuario puede registrarse para comprar juegos con clasificación para adultos (18+).
* **Lógica:** Solicita el año de nacimiento del usuario y calcula su edad restando el año actual (ejemplo: 2026). Si la edad es mayor o igual a 18, otorga acceso; de lo contrario, notifica que se requiere supervisión de un tutor.
* **Ejemplo de ejecución:**
  ```text
  Ingresa tu año de nacimiento: 2010
  Tienes 16 años. Acceso denegado: debes tener al menos 18 años para crear una cuenta.
  ```

---

### 3. Calculadora de Tarifas de Cine por Categoría (`if - elif - else`)
* **Escenario:** Un cine establece el precio de sus entradas según la edad de la persona:
  * Niños (menores de 12 años): **$50**
  * Estudiantes / Adultos (de 12 a 64 años): **$80**
  * Adultos mayores (65 años o más): **$40**
* **Lógica:** Pide la edad del cliente e imprime la categoría correspondiente y el precio final del boleto.
* **Ejemplo de ejecución:**
  ```text
  Ingresa la edad del cliente: 68
  Categoría: Adulto Mayor.
  El precio de tu boleto es de $40.
  ```

---

### 4. Sistema de Semáforo Inteligente (`if - elif - else`)
* **Escenario:** El software de un auto autónomo lee la señal del semáforo e indica la acción a tomar.
* **Lógica:** Solicita el color del semáforo (`verde`, `amarillo`, `rojo`). 
  * Si es `verde`, imprime: *"Avanzar con seguridad."*
  * Si es `amarillo`, imprime: *"Precaución: Reducir la velocidad y prepararse para frenar."*
  * Si es `rojo`, imprime: *"Alto total. Esperar cambio de luz."*
  * Si el usuario escribe cualquier otro texto, imprime: *"Color inválido. Detener el vehículo por seguridad."*
* **Ejemplo de ejecución:**
  ```text
  ¿De qué color está el semáforo?: amarillo
  Precaución: Reducir la velocidad y prepararse para frenar.
  ```

---

### 5. Control de Calificaciones Académicas (`if - elif - else`)
* **Escenario:** Una universidad califica a sus alumnos utilizando letras según la nota numérica alcanzada (del 0 al 100):
  * **90 a 100**: Excelente (A)
  * **80 a 89**: Notable (B)
  * **70 a 79**: Aceptable (C)
  * **60 a 69**: Suficiente (D)
  * **Menor a 60**: Insuficiente / Reprobado (F)
* **Lógica:** Solicita la calificación numérica e imprime la letra asignada y su descripción.
* **Ejemplo de ejecución:**
  ```text
  Ingresa la calificación obtenida (0 - 100): 85
  Resultado: Notable (Letra B).
  ```

---

### 6. Sistema de Cobro de Envío Paquetería (`if - elif - else`)
* **Escenario:** Una empresa de mensajería cobra según el peso del paquete enviado en kilogramos:
  * Hasta 1 kg: **$50**
  * Más de 1 kg y hasta 5 kg: **$100**
  * Más de 5 kg y hasta 10 kg: **$180**
  * Más de 10 kg: **$300**
* **Lógica:** Solicita el peso del paquete en kg (`float`) e informa la tarifa del envío.
* **Ejemplo de ejecución:**
  ```text
  Ingresa el peso del paquete en kilogramos: 3.5
  El costo de envío para un paquete de 3.5 kg es de $100.
  ```

---

### 7. Alerta de Nivel de Batería de Celular (`if - elif - else`)
* **Escenario:** El sistema operativo de un teléfono móvil muestra un aviso en pantalla según el porcentaje de carga restante:
  * **20% o menos**: *"Batería baja: activa el modo de ahorro de energía."*
  * **Entre 21% y 80%**: *"Batería en nivel normal."*
  * **Más de 80% y menos de 100%**: *"Carga óptima."*
  * **100%**: *"Carga completa: desconecta el cargador."*
* **Lógica:** Pide el porcentaje de batería actual (número entero) y muestra la notificación adecuada.
* **Ejemplo de ejecución:**
  ```text
  Ingresa el porcentaje de batería actual: 15
  Batería baja: activa el modo de ahorro de energía.
  ```

---

### 8. Calculadora de Índice de Masa Corporal (IMC) (`if - elif - else`)
* **Escenario:** Una clínica médica utiliza una app para clasificar el Índice de Masa Corporal de un paciente tras calcular la fórmula:  
  $$\text{IMC} = \frac{\text{peso}}{\text{estatura}^2}$$
  
  Rangos de diagnóstico:
  * IMC menor a 18.5: **Bajo peso**
  * IMC entre 18.5 y 24.9: **Peso normal**
  * IMC entre 25.0 y 29.9: **Sobrepeso**
  * IMC de 30.0 o más: **Obesidad**
* **Lógica:** Pide el peso en kg y la estatura en metros. Calcula el IMC y muestra tanto el valor numérico como el diagnóstico.
* **Ejemplo de ejecución:**
  ```text
  Ingresa tu peso en kg: 70
  Ingresa tu estatura en metros: 1.75
  Tu IMC es 22.86. Diagnóstico: Peso normal.
  ```

---

### 9. Calculadora de Impuestos por Rango de Ingresos (`if - elif - else`)
* **Escenario:** La Secretaría de Hacienda aplica una tasa de impuesto mensual sobre los ingresos brutos de los trabajadores:
  * Hasta $10,000 al mes: **Exento (0% de impuesto)**
  * De $10,000.01 a $25,000: **10% de impuesto**
  * De $25,000.01 a $50,000: **15% de impuesto**
  * Más de $50,000: **20% de impuesto**
* **Lógica:** Pide el sueldo mensual bruto, calcula el monto a retener de impuestos e imprime el sueldo neto que recibirá el trabajador.
* **Ejemplo de ejecución:**
  ```text
  Ingresa tu sueldo mensual bruto: 20000
  Monto de impuesto retenido (10%): $2000.0
  Sueldo neto a recibir: $18000.0
  ```

---

### 10. Sistema de Descuentos en Restaurante por Día (`if - elif - else`)
* **Escenario:** Un restaurante de mariscos ofrece promociones especiales según el día de la semana que el cliente ingrese:
  * `lunes`: **2x1 en bebidas.**
  * `miércoles`: **15% de descuento en platillos fuertes.**
  * `viernes`: **Postre gratis en consumos mayores a $300.**
  * Cualquier otro día (`martes`, `jueves`, `sábado`, `domingo`): **Sin promociones vigentes.**
* **Lógica:** Solicita el día de la semana (en texto en minúsculas) e indica la promoción aplicable.
* **Ejemplo de ejecución:**
  ```text
  ¿Qué día de la semana es hoy?: miércoles
  Promoción del día: ¡Hoy tienes 15% de descuento en platillos fuertes!
  ```
