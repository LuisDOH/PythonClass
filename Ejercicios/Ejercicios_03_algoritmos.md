# Ejercicios de Razonamiento Algorítmico: Diseñando Soluciones Paso a Paso

> 📌 **Objetivo:** Resolver problemas reales únicamente diseñando la secuencia de pasos lógicos (algoritmo), identificando las entradas, las decisiones y las salidas necesarias, **sin utilizar ningún lenguaje de programación**.

---

## 🛠️ Estructura que debe entregar el alumno por cada ejercicio

Para cada problema, el alumno debe completar las siguientes 4 secciones en su libreta:

1. **Entradas:** ¿Qué información necesitas pedirle al usuario o al sistema?
2. **Operaciones / Procesamiento:** ¿Qué cálculos o transformaciones debes hacer con los datos?
3. **Decisiones (`SI` / `SI NO`):** ¿Qué preguntas debes hacerte según los resultados o condiciones?
4. **Salidas:** ¿Qué mensaje o resultado final debes comunicarle al usuario?

---

## 📝 Lista de Ejercicios

### Ejercicio 1: El Control de Acceso a un Estacionamiento

* **Escenario:** Un estacionamiento automatizado cobra \$20 por hora. Si el cliente permanece más de 5 horas, la tarifa cambia a un pago fijo promocional de \$120 por todo el día. Además, si el cliente pertenece al convenio de la plaza comercial, recibe un descuento adicional de \$20 sobre su total final.
* **Tu objetivo:** Escribe la secuencia de pasos detallada que debe realizar la computadora del cajero automático para calcular el cobro final.
* **Puntos clave a resolver:**
  - ¿Cómo saber si se aplica la tarifa por hora o la tarifa fija por día?
  - ¿En qué momento se evalúa si tiene convenio o no?

---

### Ejercicio 2: Sistema de Selección para Beca Escolar

* **Escenario:** Una universidad otorga una beca estudiantil bajo las siguientes reglas de selección:
  - El estudiante debe tener un promedio general de **9.0 o más**.
  - Además, el ingreso familiar mensual debe ser **menor o igual a \$15,000**.
  - Si cumple ambos requisitos, la beca se aprueba. Si falla en cualquiera de los dos, la solicitud es rechazada.
* **Tu objetivo:** Diseña el algoritmo paso a paso que realiza el comité de becas para evaluar la solicitud de un aspirante.
* **Puntos clave a resolver:**
  - ¿Qué datos debes solicitar al estudiante al inicio?
  - ¿Cómo verificar las dos condiciones antes de tomar la decisión final?

---

### Ejercicio 3: Cálculo de Nómina Semanal con Horas Extra

* **Escenario:** Una empresa paga a sus empleados un sueldo base de **\$100 por hora** trabajada durante las primeras 40 horas de la semana. Si el empleado trabaja más de 40 horas, las horas sobrantes (horas extra) se pagan al **doble** (\$200 por hora extra).
* **Tu objetivo:** Escribe el procedimiento exacto paso a paso para calcular el salario semanal total de un trabajador.
* **Puntos clave a resolver:**
  - ¿Cómo separar las 40 horas normales de las horas extra sobrantes?
  - ¿Cómo calcular el sueldo base y el pago extra por separado antes de sumarlos?

---

### Ejercicio 4: Clasificación y Cobro de Equipaje en Aerolínea

* **Escenario:** En el mostrador de un aeropuerto, se pesa la maleta de un pasajero en kilogramos:
  - Si pesa **hasta 23 kg**, la maleta pasa sin costo adicional (Documentada normal).
  - Si pesa **más de 23 kg y hasta 30 kg**, se cobra una penalización por sobrepeso de **\$500**.
  - Si pesa **más de 30 kg**, la maleta no se permite en el avión y debe enviarse por carga especial.
* **Tu objetivo:** Redacta los pasos del procedimiento que debe seguir el personal en el sistema al registrar la maleta de un pasajero.
* **Puntos clave a resolver:**
  - Identificar los tres caminos o resultados posibles según el peso.
  - Especificar la indicación o cobro que recibe el pasajero en cada caso.

---

### Ejercicio 5: Asignación de Turnos Médicos de Urgencia (Triage)

* **Escenario:** En la sala de urgencias de un hospital, una enfermera clasifica a los pacientes según la gravedad de sus síntomas para asignar prioridad de atención:
  - Si el paciente presenta **dificultad para respirar o pérdida de conciencia**, se le asigna **Prioridad 1 (Atención Inmediata)**.
  - Si presenta **fiebre alta (mayor a 39 °C) o dolor intenso**, se le asigna **Prioridad 2 (Atención Preferente en menos de 15 min)**.
  - En cualquier otro caso, se le asigna **Prioridad 3 (Atención Regular por turno de llegada)**.
* **Tu objetivo:** Escribe el algoritmo en lenguaje natural para la recepción médica de urgencias.
* **Puntos clave a resolver:**
  - ¿Qué preguntas clínicas debe ingresar la enfermera?
  - ¿Cómo determinar en cuál de los 3 niveles de prioridad encaja el paciente?
