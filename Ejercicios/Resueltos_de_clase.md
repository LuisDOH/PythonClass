## Ejercicio 24 de Octubre 2024
Una empresa de paquetería cobra por kg enviado. Su costo por kg es de $20 pesos. Si la carga total del envió es mayor a 100 kg se realiza un descuento del 25%.
Desarrolle un programa que permita calcular el costo de un envió con esta empresa y en caso de aplicar, indique al usuario que tiene un descuento del 25%.

```python
peso_paquete = float(input("Cuanto pesa el paquete? "))
costo_kg = 20
descuento = 0.25

if peso_paquete >= 100:
    print("Aplica descuento")
    total = peso_paquete*costo_kg
    monto_descuento = total*descuento
    total_final = total - monto_descuento
    print(f"El costo del envio es: ${total}")
    print(f"El descuento aplicado es: ${monto_descuento}")
    print(f"El costo final con descuento es ${total_final}")

else:
    print("No aplica descuento")
    total = peso_paquete*costo_kg
    print(f"El costo de envio es de ${total}")

```
