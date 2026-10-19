# 🏦 Asistente Virtual Bancario con Inteligencia Artificial

### Automatización de consultas bancarias mediante n8n, JavaScript, Google Sheets y Google Gemini

Proyecto académico de **Modelado de Software**, desarrollado para demostrar cómo la inteligencia artificial y la automatización de procesos pueden aplicarse a la orientación y atención de consultas frecuentes del sector financiero argentino.

El sistema integra una base de conocimientos estructurada, un algoritmo de búsqueda y clasificación desarrollado en JavaScript y un agente de inteligencia artificial capaz de generar respuestas en lenguaje natural.

**Autor:** Arnaldo Ledesma  
**Materia:** Modelado de Software  
**Versión:** 1.0  
**Estado:** Prototipo académico funcional

---

## 🎯 Objetivo del proyecto

Desarrollar un asistente virtual capaz de brindar orientación automatizada sobre productos y servicios bancarios, utilizando información de referencia previamente organizada.

El proyecto busca demostrar cómo la automatización puede facilitar el acceso a información general y servir como apoyo inicial a los procesos de atención al usuario.

## 🛠️ Tecnologías utilizadas

| Tecnología | Función |
|---|---|
| **n8n** | Automatización y coordinación del flujo de trabajo. |
| **Google Gemini** | Interpretación de consultas y generación de respuestas en lenguaje natural. |
| **Google Sheets** | Base de conocimientos estructurada con 100 registros. |
| **JavaScript** | Algoritmo de búsqueda, puntuación y clasificación de consultas. |
| **Simple Memory** | Conservación temporal del contexto conversacional. |
| **Chat de n8n** | Interfaz para interactuar con el asistente. |

## ⚙️ Arquitectura y funcionamiento

El asistente utiliza el siguiente flujo:

```text
Usuario
   |
   v
Chat de n8n
   |
   v
Edit Fields
   |
   v
Google Sheets
   |
   v
JavaScript
   |
   v
AI Agent (Google Gemini + Simple Memory)
   |
   v
Respuesta al usuario
```

### Etapas del procesamiento

1. El usuario escribe una consulta en el chat.
2. n8n recibe y organiza el mensaje.
3. Google Sheets proporciona los registros de la base de conocimientos.
4. JavaScript normaliza el texto, calcula coincidencias y selecciona hasta cinco registros relevantes.
5. El algoritmo realiza una clasificación inicial de la consulta.
6. Google Gemini interpreta los resultados y genera una respuesta siguiendo las instrucciones del sistema.
7. El asistente presenta la respuesta al usuario.

## 🧠 Clasificación de consultas

El algoritmo JavaScript distingue inicialmente tres tipos de solicitudes:

| Clasificación | Descripción |
|---|---|
| `INFORMACION_GENERAL` | Consultas sobre productos y servicios bancarios. |
| `INFORMACION_ACTUALIZADA` | Solicitudes de información financiera vigente, como tasas de interés. |
| `INFORMACION_PERSONAL` | Consultas relacionadas con saldos, cuentas o movimientos personales. |

Esta clasificación se realiza mediante reglas de procesamiento de texto y sirve como orientación para el agente de IA.

## 📚 Base de conocimientos

La información se administra mediante Google Sheets y está organizada en cinco campos:

- `CATEGORIA`
- `PRODUCTO`
- `PREGUNTA`
- `RESPUESTA`
- `DERIVAR_ASESOR`

La base contiene 100 registros relacionados con consultas frecuentes del sector bancario.

El algoritmo selecciona hasta cinco coincidencias relevantes para que el agente evalúe cuál corresponde a la consulta realizada.

## 🔐 Seguridad y límites operativos

El asistente incorpora instrucciones destinadas a:

- Evitar la solicitud de contraseñas, PIN y tokens de seguridad.
- No afirmar que tiene acceso a cuentas o información financiera privada.
- No inventar tasas de interés ni condiciones comerciales vigentes.
- No simular operaciones bancarias reales.
- Recomendar canales oficiales cuando una consulta requiere información adicional.
- Mantener una comunicación profesional en español de Argentina.

**Importante:** este proyecto es un prototipo académico. No representa a ninguna entidad financiera ni está conectado a sistemas bancarios reales.

## 🧪 Pruebas funcionales

Se realizaron pruebas sobre tres escenarios:

| Escenario | Consulta | Resultado |
|---|---|---|
| Información actualizada | ¿Cuál es la tasa de interés vigente de un préstamo hipotecario UVA del Banco Nación? | No proporcionó tasas no verificadas y recomendó consultar canales oficiales. |
| Información general | ¿Qué es un crédito hipotecario? | Recuperó información pertinente de la base de conocimientos. |
| Información personal | ¿Cuánto dinero tengo actualmente en mi cuenta bancaria? | Reconoció que no tiene acceso a saldos personales. |

Los escenarios evaluados mostraron resultados satisfactorios en sus objetivos principales. También se identificaron oportunidades de mejora en la consistencia del lenguaje utilizado.

## 🚀 Instalación y configuración

Para utilizar el proyecto:

1. Instalar o acceder a una instancia de **n8n**.
2. Descargar el archivo JSON del workflow disponible en este repositorio.
3. Importar el archivo en n8n.
4. Configurar las credenciales propias de Google Gemini y Google Sheets.
5. Crear una hoja de cálculo con las columnas indicadas en la sección de base de conocimientos.
6. Configurar el nodo de Google Sheets para utilizar esa hoja.
7. Ejecutar el workflow y realizar consultas de prueba mediante el chat.

**Nota:** por motivos de seguridad, el JSON publicado no incluye credenciales personales ni identificadores de la hoja de cálculo original. Tampoco incluye los 100 registros utilizados durante el desarrollo.

## 📈 Mejoras futuras

Entre las posibles ampliaciones del proyecto se encuentran:

- Incorporar búsqueda semántica mediante embeddings.
- Ampliar la base de conocimientos.
- Integrar nuevos canales digitales de atención.
- Implementar mecanismos de derivación automatizada a asesores.
- Incorporar indicadores de consultas y desempeño.
- Fortalecer los controles de seguridad y auditoría.

Estas funcionalidades no forman parte de la versión actual.

## 👨‍💻 Autor

**Arnaldo Ledesma**

Estudiante de Desarrollo de Software, con interés en automatización, análisis de datos, programación e integración de tecnologías aplicadas al sector financiero.

**GitHub:** [ArnaldoLedesma](https://github.com/ArnaldoLedesma)

---

*Proyecto académico — Modelado de Software — 2026.*
