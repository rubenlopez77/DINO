# 🦕 DINO: Diseño Funcional & Roadmap

Declarative Intelligence Orchestration for QAs

DINO es un agente inteligente impulsado por IA diseñado para generar, validar y orquestar artefactos de prueba declarativos dentro del ecosistema BAM (Behavior Annotation Model).

Analiza features Gherkin, pasos existentes, requisitos y resultados de ejecución para ofrecer tests inteligentes, trazabilidad mejorada y procesos QA más coherentes y automatizados.

```Cucumber (Qué) → BAM (Cómo declarativo) → DINO (Orquestación inteligente)```

DINO es la capa IA que se apoya en el modelo BAM y los artefactos Gherkin para orquestar calidad a lo largo del ciclo de automatización.


<p align="center">
  <img src="./dino.png" alt="DINO Logo" width="240">
</p>



## La fuerza de BAM!, la inteligencia de DINO 
Por si te lo preguntas, y sino lo voy a poner igual 😄 Los nombres **DINO** y **BAM** (de Bam-Bam)  se inspiran en el universo de Los Picapiedra.

    BAM = Ejecución simple, robusta y predecible (sólo da porrazos!)
    DINO = Orquestación ágil e inteligente (siempre ayudando!)

## **📌 Preámbulo**

Este proyecto nace como una** iniciativa experimental **para explorar cómo la Inteligencia Artificial puede potenciar la automatización de pruebas bajo el modelo **BAM** (Behavior Annotation Model), un enfoque creado para maximizar:

- **Trazabilidad** real entre requisitos, features y ejecución.
- **Mantenibilidad** de suites automatizadas.
- **Robustez** y reproducibilidad, eliminando await en tests y delegando la asincronía en el Runner.
- **Calidad** estructural, mediante reglas claras validadas por una librería de normas.

El objetivo de este CLI es convertirse en un agente inteligente local, capaz de:

- Analizar proyectos BAM/Playwright.
- Generar steps declarativos BAM desde features Gherkin.
- Detectar huecos de cobertura (“gaps”).
- Validar coherencia entre requisitos y ejecución (“QA del QA”).
- Generar documentación viva.

Este repositorio es una prueba de concepto pública, diseñada para demostrar capacidad técnica, visión QA y uso responsable de IA aplicada a automatización.

---

# **1. Visión del Proyecto**

**DINO** es una herramienta de consola desarrollada en **TypeScript**, diseñada para operar como un sidecar inteligente sobre proyectos BAM/Playwright.

El CLI:

- Se integra con modelos LLM **on-prem** (Gemma, Llama, etc.).  
- Ofrece reglas deterministas BAM que garantizan calidad estructural.  
- Usa análisis contextual (RAG ligero) para comprender el proyecto. 
- Genera código TypeScript listo para ser consumido por la suite de pruebas.  


---

# **2. Objetivos Funcionales**

✔ Generar automáticamente steps/tests BAM desde features Gherkin.

✔ Validar que las pruebas cumplen las normas BAM (sin await, runner correcto, etc.).

✔ Detectar huecos entre requisitos, features y pasos implementados.

✔ Crear documentación viva (Test Plan, trazabilidad, matrices de cobertura).

✔ Reducir el tiempo de creación de tests y aumentar la calidad del diseño.

✔ Mantener la privacidad usando únicamente modelos IA locales (sin cloud).

---

## 3. Requisitos No Funcionales

- Tecnología: TypeScript + Node.js
- Compatibilidad: Windows / Linux
- Privacidad: Sin dependencias cloud — todo local / on-prem
- Extensibilidad: Configurable, modular y desacoplado del core BAM
- Seguridad: Nunca sobrescribir archivos del usuario sin confirmación

## 4. Roadmap del Proyecto
- **Fase 0 **– Base técnica (v0.0.x)
Setup inicial del CLI
Comando init
Reglas BAM básicas (sin IA)
Comando validate-project

- **Fase 1** – Generación de Steps desde Gherkin (v0.1.x)
	Integración con LLM local
	Prompts BAM
	Comando generate-from-features
	Validación automática de steps generados


- **Fase 2** – Contexto y RAG ligero (v0.2.x)
		Indexación de features, steps y requisitos
		Detectar patrones existentes
		Detección básica de gaps
		
- **Fase 3** – QA del QA (v0.3.x)
	Validación cruzada: requisitos ↔ Gherkin ↔ steps ↔ ejecución
	Reportes de coherencia y calidad
- **Fase 4** – Documentación Viva (v1.0)
Generación automática de Test Plans
Matrices de cobertura
Resumen funcional y técnico
- **Fase 5** – Empaquetado y UX
Versionado
Empaquetado como .exe
Banner CLI
Mejoras de experiencia de usuario

Licencia
Este proyecto se distribuye bajo la licencia Apache 2.0, que permite
-Uso personal y comercial
-Modificación
-Distribución
-Sub-licenciamiento

Siempre que se mantenga la atribución al autor y las cláusulas legales incluidas
