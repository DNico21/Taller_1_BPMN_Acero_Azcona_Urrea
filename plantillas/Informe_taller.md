# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 1 - Modelado de Proceso del Cliente con BPMN_

## 👥 Integrantes del equipo
- Deivid Nicolas Urrea Lara (GitHub: DNico21)
- Samuel Acero García (GitHub: Iron200044)
- Andrés Felipe Azcona (GitHub: andresazcona)

## 🧠 Descripción general del trabajo
El objetivo del taller fue modelar un proceso de negocio real utilizando la notación BPMN 2.0, identificando eventos, actividades, decisiones, actores involucrados y puntos críticos del flujo. 

En la primera parte se trabajó el caso base de la Clínica Salud Viva, modelando el proceso de agendamiento de citas médicas. Posteriormente, se aplicó la metodología al cliente real asignado: Cemedica IPS y Salud Ocupacional.

El proceso seleccionado fue la generación, validación y envío de los archivos RIPS en formato JSON al sistema SISPRO, de acuerdo con las Resoluciones 2275 de 2023 y 558 de 2024. Este proceso es crítico para el cumplimiento normativo ante el Ministerio de Salud y la DIAN.

## 🔧 Proceso de desarrollo
Para el desarrollo del taller se siguieron los siguientes pasos:

1. Análisis del problema real del cliente, identificando la necesidad de generar archivos RIPS en formato JSON desde un sistema legacy (EGMH) sin mantenimiento.
2. Definición del alcance del proceso a modelar, enfocándolo específicamente en la generación y envío de RIPS a SISPRO.
3. Identificación de actores clave:
   - Profesional de Salud
   - Sistema Legacy EGMH
   - Módulo Generador RIPS
   - Área Administrativa
   - Plataforma SISPRO
4. Diseño preliminar del flujo en borrador.
5. Modelado digital utilizando herramienta BPMN (Lucidchart / draw.io).
6. Ajuste del diagrama aplicando buenas prácticas BPMN 2.0 (uso correcto de gateways exclusivos, separación en pools y lanes, eventos de mensaje y eventos de error).

Se priorizó modelar primero los eventos de inicio y fin, luego las actividades principales, y finalmente las decisiones y validaciones externas.

## 🧩 Análisis del modelo propuesto

### Estructura del modelo
El modelo se estructuró en dos pools principales:
- Pool 1: Cemedica IPS
- Pool 2: Plataforma SISPRO

Dentro del pool de Cemedica se definieron lanes para separar responsabilidades entre el profesional de salud, el sistema legacy y el módulo generador de RIPS.

El flujo inicia con la prestación del servicio médico y finaliza cuando el archivo RIPS JSON es aceptado por SISPRO.

Se incluyen:
- Eventos de inicio y fin
- Gateways exclusivos (XOR) para validación de datos y respuesta de SISPRO
- Eventos intermedios de mensaje para la comunicación entre sistemas
- Evento de error en caso de rechazo del archivo

### Representación de las necesidades del cliente
El modelo refleja la problemática real de Cemedica:
- Sistema legacy sin soporte
- Necesidad de extracción y transformación de datos
- Validación normativa obligatoria
- Interacción con plataforma gubernamental externa

Se evidencia la necesidad de un módulo intermedio que transforme la información clínica en formato JSON conforme a la normativa vigente.

### Supuestos tomados
- Se asume que el sistema legacy almacena correctamente la información clínica.
- Se asume que la validación en SISPRO es automática.
- Se modela un flujo ideal sin interrupciones manuales adicionales.
- No se modelan aspectos técnicos internos de programación, solo el proceso de negocio.

## 📈 Diagrama final entregado
> Ver archivo: entrega/modelo-final.drawio  
> Proceso: "Generación y Envío de RIPS JSON a SISPRO – Cemedica IPS"

## 📋 Tabla de actores, entidades o componentes

| Nombre del elemento | Tipo | Descripción | Responsable |
|---------------------|------|-------------|-------------|
| Profesional de Salud | Actor | Registra la atención médica en el sistema | IPS |
| Sistema Legacy EGMH | Sistema | Sistema de historias clínicas desarrollado en 2008 | IPS |
| Módulo Generador RIPS | Componente | Extrae, valida y transforma datos a JSON | IPS |
| Área Administrativa | Actor | Supervisa cumplimiento normativo | IPS |
| Plataforma SISPRO | Sistema Externo | Valida y recibe archivos RIPS JSON | Ministerio de Salud |

## 🔍 Investigación complementaria

### Tema investigado:
Buenas prácticas en modelado BPMN 2.0 y modelado de procesos regulados.

### Resumen:
BPMN 2.0 es un estándar definido por la Object Management Group (OMG) para modelar procesos de negocio de manera formal y comprensible tanto para perfiles técnicos como de negocio. Entre sus buenas prácticas se encuentran: utilizar un solo evento de inicio, mantener claridad visual, evitar cruces innecesarios de flujo, utilizar gateways exclusivos para decisiones binarias y separar claramente organizaciones externas mediante pools.

En procesos regulados como el envío de información a plataformas gubernamentales, es recomendable modelar explícitamente los eventos de mensaje y los eventos de error, ya que representan puntos críticos del proceso. Esto permite identificar riesgos, dependencias externas y posibles cuellos de botella.

La aplicación de estas buenas prácticas permitió construir un modelo claro, estructurado y alineado con estándares internacionales.

## 📚 Referencias
- [1] Ministerio de Salud y Protección Social. Resolución 2275 de 2023.
- [2] Ministerio de Salud y Protección Social. Resolución 558 de 2024.
- [3] SISPRO. Micrositio FEV-RIPS. https://www.sispro.gov.co/Pages/Home.aspx
- [4] Object Management Group (OMG). BPMN 2.0 Specification. https://www.omg.org/spec/BPMN/

---

_Este documento hace parte de la entrega del Taller 1 del curso Arquitectura Empresarial - Universidad de La Sabana._
