# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller 1 - Modelado de Proceso del Cliente con BPMN_

## 👥 Integrantes del equipo
- Deivid Nicolas Urrea Lara (GitHub: DNico21)
- Samuel Acero García (GitHub: Iron200044)
- Andrés Felipe Azcona (GitHub: andresazcona)

## 🧠 Descripción general del trabajo

El objetivo del taller fue modelar un proceso de negocio real utilizando la notación BPMN 2.0, identificando eventos, actividades, decisiones, actores involucrados y puntos críticos del flujo.

En la primera parte se trabajó el caso base de la Clínica Salud Viva, modelando el proceso de agendamiento de citas médicas con separación por swimlanes y uso correcto de gateways exclusivos y paralelos.

Posteriormente, se aplicó la metodología al cliente real encontrado: **Cemedica IPS y Salud Ocupacional**, modelando el proceso de generación, validación y envío de los archivos RIPS en formato JSON al sistema SISPRO, conforme a lo establecido en las Resoluciones 2275 de 2023 y 558 de 2024.

Este proceso es fundamental para el cumplimiento normativo ante el Ministerio de Salud y la DIAN, ya que los RIPS constituyen el mecanismo oficial de reporte de prestación de servicios de salud.

---

## 🔧 Proceso de desarrollo

El desarrollo del modelo se realizó en las siguientes etapas:

1. Análisis del contexto del cliente, identificando la problemática principal: el sistema legacy (EGMH) no genera automáticamente los RIPS en formato JSON.
2. Definición del alcance del proceso a modelar, enfocándolo exclusivamente en la generación y envío del RIPS a SISPRO.
3. Identificación de actores principales del proceso:
   - Profesional de Salud
   - Sistema EGMH (Legacy)
   - Área Administrativa
   - Plataforma SISPRO
4. Construcción manual del flujo en herramienta digital (draw.io), respetando la estructura trabajada en clase.
5. Incorporación de buenas prácticas BPMN:
   - Flujo de izquierda a derecha.
   - Uso de un único evento de inicio.
   - Uso de gateways exclusivos (XOR) para decisiones.
   - Separación clara de responsabilidades mediante swimlanes.
   - Uso de eventos de mensaje para interacción entre organizaciones.

Se priorizó representar el proceso desde la perspectiva del negocio y no desde un enfoque técnico de implementación.

---

## 🧩 Análisis del modelo propuesto

### Estructura del modelo

El modelo se estructuró en un único proceso con cuatro swimlanes:

- Profesional de Salud  
- Sistema EGMH (Legacy)  
- Área Administrativa  
- Plataforma SISPRO  

El flujo inicia con la atención médica realizada y culmina con la aceptación del RIPS por parte de SISPRO.

El modelo incluye:

- Evento de inicio.
- Evento de fin.
- Dos gateways exclusivos:
  - ¿Información completa?
  - ¿Archivo aceptado?
- Ciclo de retroalimentación en caso de rechazo.
- Comunicación entre la IPS y SISPRO mediante flujo de mensaje.

---

### Representación de las necesidades del cliente

El modelo refleja de manera clara la problemática real de Cemedica IPS:

- Dependencia de un sistema legacy sin mantenimiento.
- Necesidad de validar la integridad de los datos antes de generar el RIPS.
- Envío obligatorio de información a una plataforma gubernamental externa.
- Gestión de errores y reprocesamiento en caso de rechazo del archivo.

El ciclo de retroalimentación modelado permite evidenciar que el proceso no termina ante un rechazo, sino que incorpora análisis y ajuste de datos antes de un nuevo envío, lo cual representa una práctica realista de control y cumplimiento.

---

### Supuestos tomados

Para efectos del modelado se asumió que:

- El sistema EGMH almacena correctamente la información clínica.
- La validación realizada por SISPRO es automática.
- El proceso puede repetirse hasta que el archivo sea aceptado.
- No se modelaron detalles técnicos internos (estructura JSON, validaciones de esquema, APIs), ya que el enfoque es de proceso de negocio.

---

## 📈 Diagrama final entregado

> Archivo: `entrega/modelo-final.drawio`  
> Proceso: **Proceso de Generación y Envío de RIPS JSON – Cemedica IPS**

El diagrama fue desarrollado manualmente respetando la notación BPMN 2.0 y siguiendo el estilo trabajado en clase.

---

## 📋 Tabla de actores, entidades o componentes

| Nombre del elemento | Tipo | Descripción | Responsable |
|---------------------|------|-------------|-------------|
| Profesional de Salud | Actor | Registra la atención médica en el sistema | IPS |
| Sistema EGMH (Legacy) | Sistema | Sistema de historias clínicas donde se almacena la información | IPS |
| Área Administrativa | Actor | Analiza errores y ajusta datos en caso de rechazo | IPS |
| Plataforma SISPRO | Sistema Externo | Valida y recibe archivos RIPS JSON | Ministerio de Salud |

---

## 🔍 Investigación complementaria

### Tema investigado:
Buenas prácticas en modelado BPMN 2.0 aplicadas a procesos regulados.

### Resumen:

BPMN 2.0, definido por la Object Management Group (OMG), es un estándar internacional para la representación gráfica de procesos de negocio. Su objetivo es permitir que tanto perfiles técnicos como no técnicos comprendan el flujo de un proceso de manera clara y estructurada.

Entre las buenas prácticas aplicadas en este modelo se destacan:

- Uso de un único evento de inicio.
- Uso de gateways exclusivos para decisiones binarias.
- Separación de responsabilidades mediante swimlanes.
- Representación explícita de interacción entre organizaciones mediante mensajes.
- Evitar sobrecarga visual innecesaria.

En procesos regulados como el envío de RIPS, es fundamental modelar claramente los puntos de validación y los ciclos de retroalimentación, ya que representan riesgos operativos y dependencias externas.

---

## 📚 Referencias

- Ministerio de Salud y Protección Social. Resolución 2275 de 2023.
- Ministerio de Salud y Protección Social. Resolución 558 de 2024.
- Sistema Integral de Información de la Protección Social (SISPRO). Micrositio FEV-RIPS. https://www.sispro.gov.co/Pages/Home.aspx

---

_Este documento hace parte de la entrega del Taller 1 del curso Arquitectura Empresarial - Universidad de La Sabana._

