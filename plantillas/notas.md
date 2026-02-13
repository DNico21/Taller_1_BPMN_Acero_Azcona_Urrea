# 🗒️ Registro de Trabajo en Clase - Taller 1

## 📆 Fecha de la sesión
7 de febrero de 2026

## 👥 Integrantes presentes
- Deivid Nicolas Urrea Lara (GitHub: DNico21)
- Samuel Acero García (GitHub: Iron200044)
- Andrés Felipe Azcona (GitHub: andresazcona)

## 🧠 Actividades realizadas en clase

Durante la sesión se trabajó el modelado del caso base propuesto: **Clínica Salud Viva – Proceso de Agendamiento de Citas Médicas**.

Se desarrollaron las siguientes actividades:

- Análisis del contexto del caso y comprensión del flujo completo del proceso de agendamiento.
- Identificación de los actores principales: Paciente, Sistema de Citas y Base de Datos.
- Definición del evento de inicio ("Necesita agendar cita") y del evento de fin ("Cita confirmada").
- Modelado de las actividades principales del paciente: ingresar al sistema, seleccionar especialidad, médico, fecha y confirmar cita.
- Modelado de las actividades del sistema: consulta de especialidades, médicos y disponibilidad.
- Inclusión de un gateway exclusivo (X) para representar la decisión "¿Horario disponible?".
- Modelado del registro de la cita en el sistema.
- Inclusión de un gateway paralelo (+) para representar el envío simultáneo de notificaciones (correo y SMS).
- Uso de un data store para representar la base de datos de citas/agendas.
- Aplicación de buenas prácticas BPMN vistas en clase:
  - Flujo de izquierda a derecha.
  - Separación clara en swimlanes.
  - Uso correcto de eventos, actividades y gateways.
  - Nombres claros y orientados al negocio.

Herramientas utilizadas:
- Modelado digital directamente en Lucidchart.

Parte desarrollada en clase:
- Construcción completa del modelo BPMN del caso base.
- Identificación y validación de eventos, decisiones y paralelismo.
- Estructuración del flujo general respetando el estándar BPMN 2.0.

## 🧩 Boceto inicial del modelo

> El modelo fue desarrollado directamente en herramienta digital durante la sesión, construyendo una versión estructurada del diagrama BPMN del proceso de agendamiento de citas de la Clínica Salud Viva.

## 🔁 Tareas definidas para complementar el taller

| Tarea asignada | Responsable | Fecha estimada |
|----------------|-------------|----------------|
| Ajustes finales del modelo BPMN del caso base | Deivid Nicolas Urrea Lara | 15/02 |
| Modelado del proceso del cliente real (Cemedica IPS) | Samuel Acero García | 16/02 |
| Redacción del informe técnico | Andrés Felipe Azcona | 17/02 |
| Investigación normativa (RIPS JSON y buenas prácticas BPMN) | Deivid Nicolas Urrea Lara | 17/02 |

---

_Este documento resume el trabajo colaborativo realizado durante la sesión del Taller 1 en el curso AREM - Arquitectura Empresarial - Universidad de La Sabana._
