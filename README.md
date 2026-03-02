# 🕵️ Editor Vigilante: Entorno de Evaluación Controlado

Este proyecto consiste en una herramienta web ligera diseñada para docentes técnicos (Programación, Robótica, Electrónica) que necesiten aplicar evaluaciones escritas en entornos de laboratorio, asegurando la integridad del contenido mediante la restricción de funciones de copiado y el monitoreo de la actividad del estudiante.

---

## 📋 Descripción General
El **Editor Vigilante** es un archivo HTML auto-contenido que transforma el navegador en un procesador de texto restringido. Su objetivo principal es fomentar la producción propia del estudiante, evitando el "copiar y pegar" de fuentes externas durante exámenes teóricos o técnicos.

### Funcionalidades Principales:
* **Anti-Copy/Paste:** Bloqueo de atajos de teclado (`Ctrl+C`, `Ctrl+V`, `Ctrl+X`) y menú contextual.
* **Modo Pantalla Completa:** Obliga al estudiante a mantener el foco visual en la evaluación.
* **Sistema de Infracciones:** Detecta y contabiliza cada vez que el alumno cambia de pestaña, minimiza el navegador o sale de pantalla completa.
* **Exportación Directa:** Genera un archivo compatible con Microsoft Word (`.doc`) para la entrega final.

---

## ⚙️ Configuración para el Docente
Para adaptar la plantilla a su curso, siga estos pasos numerados:

1.  **Abrir el archivo:** Localice el archivo `.html` y ábralo con un editor de texto (Bloc de notas, VS Code, etc.).
2.  **Localizar constantes:** Busque el bloque de código identificado como `// SECCIÓN PARA EL DOCENTE`.
3.  **Personalizar parámetros:** Modifique los valores de la estructura `CONFIG` según su planificación:

| Parámetro | Descripción | Ejemplo |
| :--- | :--- | :--- |
| `asignatura` | Nombre del curso o módulo. | `"Programación Java - 2do BD"` |
| `docente` | Nombre del profesor a cargo. | `"Prof. Juan Pérez"` |
| `limiteInfracciones` | Cantidad de avisos antes del bloqueo. | `3` |
| `nombreArchivo` | Nombre del archivo de descarga. | `"entrega_robotica.doc"` |

---

## 🚀 Guía de Aplicación en el Aula

Para implementar esta herramienta en un grupo de **UTU**, se recomienda el siguiente flujo de trabajo:

### 1. Preparación del Entorno
Distribuya el archivo configurado en las estaciones de trabajo del laboratorio. Puede utilizar una carpeta compartida en red o la plataforma educativa institucional.

### 2. Ejecución de la Evaluación
Solicite a los estudiantes que:
* Abran el archivo con un navegador moderno (Chrome, Edge o Firefox).
* Presionen el botón **"Iniciar Evaluación"** y acepten la solicitud de pantalla completa.
* Redacten su respuesta utilizando las herramientas de formato básico proporcionadas.

### 3. Cierre y Recolección
Una vez finalizado el tiempo, el estudiante debe:
* Presionar **"Descargar Entrega"**.
* Subir el archivo `.doc` generado a la plataforma de entrega definida por el docente.

---

## ⚠️ Consideraciones Técnicas y Pedagógicas
* **Nivel de Seguridad:** Esta es una herramienta de monitoreo preventivo basada en el lado del cliente. Es ideal para exámenes presenciales donde existe supervisión docente adicional.
* **Uso en Robótica/Programación:** Es especialmente útil para evaluar la capacidad de explicar lógica de algoritmos o sintaxis de lenguajes (como Java) sin asistencia de IDEs o motores de búsqueda.
* **Compatibilidad:** Funciona de manera óptima en sistemas operativos de escritorio.

---
## ⚖️ Privacidad y Ética Educativa

Este proyecto ha sido desarrollado bajo principios de **transparencia y minimización de datos**, cumpliendo con los siguientes criterios:

1.  **Privacidad de Aplicaciones:** Debido a las restricciones de seguridad (*sandboxing*) de los navegadores modernos, esta herramienta **no puede ni intenta** acceder al historial de navegación, archivos personales, cámara, micrófono o aplicaciones externas (como WhatsApp, Discord o Gemini) del estudiante.
2.  **Monitoreo del Foco:** El sistema únicamente detecta eventos de pérdida de foco en su propia pestaña (eventos `blur` y `visibilitychange`). Registra **cuándo** el estudiante abandona la evaluación, pero **nunca hacia dónde** se dirige.
3.  **Ejecución en el Cliente:** Todo el procesamiento ocurre de forma local en el navegador del estudiante. No se envían datos a servidores externos; la información de auditoría se destruye al cerrar la pestaña, a menos que se descargue el archivo final.
4.  **Uso Pedagógico:** El reporte de integridad tiene como fin exclusivo servir de insumo para que el docente pueda validar la autoría del texto en el marco de una evaluación presencial controlada.
   
*Desarrollado como apoyo a la labor docente en el ámbito técnico.*
