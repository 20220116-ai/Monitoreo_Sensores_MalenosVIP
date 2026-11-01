# Monitoreo de neumáticos – Maleños VIP

Plataforma web del Mantenimiento Predictivo Basado en Condición (PdM/CBM) para la ruta Lima – Mala (R-01). Muestra el estado de las llantas de los 55 buses a partir de los sensores de presión y temperatura.

## Qué incluye

- **Flota:** una tarjeta por bus con sus cuatro neumáticos y el color del semáforo.
- **Alertas:** responsable y acción según el momento de la operación; registro de atención y cierre con su causa.
- **Mapa de ruta:** posición de cada bus en la ruta y estado de sus llantas.
- **Indicadores:** disponibilidad de datos, tiempo de aviso, amarillos atendidos a tiempo y falsas alarmas.
- **Configuración:** presión recomendada por eje, límites del semáforo y fuente de datos.

## Reglas del semáforo

Sobre la presión corregida a frío, como porcentaje de la presión recomendada del eje:

| Estado | Condición |
|---|---|
| Verde | 90 % o más, sin caída anormal |
| Amarillo | 80 – 90 %, o caída de más de 5 % frente al arranque en frío de ayer (fuga lenta) |
| Rojo | Menos de 80 %, o pérdida rápida de presión |
| Sin datos | El sensor no transmite durante más de 5 min con el motor encendido |

Corrección a frío: `P_frío = (P_medida + 1,013) × (T_ref + 273,15) ÷ (T_medida + 273,15) − 1,013` [bar; °C].

## Cómo usarlo

Abra `index.html` en cualquier navegador. Por defecto funciona en modo demostración, con lecturas simuladas; en **Configuración → Fuente de datos → Datos reales** se conecta a un servicio web o se carga un archivo JSON de lecturas.
