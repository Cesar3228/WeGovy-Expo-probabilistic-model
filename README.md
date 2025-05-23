# 🧠 Simulación de Ocupación en Evento Multiespacios

Este proyecto simula el comportamiento de hasta **6000 asistentes** durante un evento presencial con múltiples espacios como ponencias, stands, pantallas, baños, zonas de comida, traslado y áreas lounge. La simulación estima minuto a minuto la distribución de personas según diferentes **escenarios de permanencia**.

## 🎯 Objetivo

Evaluar la dinámica de ocupación de un recinto con alta afluencia para:
- Identificar cuellos de botella
- Determinar subutilización de espacios
- Medir asistentes sin asignación (libres)
- Optimizar capacidades de zonas clave

---

## ⚙️ Lógica del Modelo

- Se simulan **91 minutos** (de 9:00 a 10:30 AM).
- Se contemplan **4 escenarios de permanencia**:
  - Corta Permanencia (70%)
  - Media Permanencia (80%)
  - Larga Permanencia (90%)
  - Total Permanencia (100%)
- Las actividades tienen **rotaciones y límites de capacidad**:
  - Ponencias: en dos bloques de 20 minutos.
  - Stands, pantallas, comida y baños: activados por rotaciones aleatorias.
  - Lounge: capacidad constante.
  - Traslado: simulado con rango aleatorio.
- Se calcula **minuto a minuto**:
  - Asistentes por actividad
  - Asistentes libres
  - Total asistentes presentes

---

## 🧮 Variables Simuladas

| Variable         | Descripción                                      |
|------------------|--------------------------------------------------|
| `Ponencias`      | Asistentes en salas durante bloques definidos    |
| `Stands`         | Interacción con stands cada ciertos minutos      |
| `Pantallas`      | Interacción con pantallas breves                 |
| `Lounge`         | Zona de descanso con capacidad fija              |
| `Baños`          | Uso de sanitarios dividido en hombres/mujeres   |
| `Comida`         | Servicio de alimentos en rotación                |
| `Traslado`       | Personas en movimiento dentro del recinto        |
| `Libres`         | Personas sin actividad asignada en ese minuto    |

---

## 📊 Resultados

- Se genera un DataFrame por escenario, con el estado minuto a minuto.
- Se puede analizar:
  - La evolución de ocupación por zona.
  - Cuántos asistentes permanecen sin actividad.
  - El uso efectivo de los espacios del evento.

---

## 🧠 Ejemplo de uso

```python
# Para visualizar un escenario:
df_ocupacion_por_escenario["Media Permanencia"]
