## Ejercicio 2: Cálculo de Pago en Estacionamiento

Este módulo calcula el importe a pagar en un estacionamiento basándose en el tiempo de permanencia (HH:MM), cobrando S/. 2.5 por hora o fracción.

### Análisis del Algoritmo
- Si el vehículo permanece `02:00` horas, se cobran exactamente 2 horas.
- Si permanece `02:05` horas, la fracción de 5 minutos hace que se cobren 3 horas en total.

### Diagrama de Flujo

```mermaid
graph TD
    A([Inicio]) --> B[/Leer tiempo en formato HH:MM/]
    B --> C[Separar Horas y Minutos]
    C --> D{¿Minutos > 0?}
    
    D -- Sí --> E[Horas_a_pagar = Horas + 1]
    D -- No --> F[Horas_a_pagar = Horas]
    
    E --> G[Importe = Horas_a_pagar * 2.5]
    F --> G
    
    G --> H[/Mostrar Importe a pagar/]
    H --> I([Fin])
