## 🧩 1. Introducción

DINO es un agente inteligente local diseñado para trabajar junto al modelo BAM (Behavior Annotation Model), ampliando sus capacidades mediante IA sin comprometer la privacidad del proyecto.

No es un sustituto del QA, ni un generador automático de suites completas.

Es un orquestador inteligente, que acelera tareas repetitivas y mejora la coherencia y calidad del diseño de pruebas.

<p align="center">
  <img src="./dino.png" alt="DINO Logo" width="240">
</p>

![DINO](https://img.shields.io/badge/DINO-Local_AI_Assistant-blueviolet?logo=testcafe&logoColor=white&style=flat-square)![Local Only](https://img.shields.io/badge/Privacy-100%25_Local-orange?style=flat-square)![BAM Compatible](https://img.shields.io/badge/Works_with-BAM_Framework-blue?style=flat-square)


```
Cucumber (qué validar)
→ BAM (cómo declararlo)
→ DINO (cómo orquestarlo con inteligencia)
```
La relación entre BAM y DINO es simbiótica:

## La fuerza de BAM!, la inteligencia de DINO 
Por si te lo preguntas, y sino lo voy a poner igual 😄 Los nombres **DINO** y **BAM** (de Bam-Bam)  se inspiran en el universo de Los Picapiedra.

    BAM = Ejecución simple, robusta y predecible (sólo da porrazos!)
    DINO = Orquestación ágil e inteligente (siempre ayudando!)


## 🧪 2. Preámbulo del proyecto

DINO nace como una iniciativa experimental para explorar el potencial de IA on-premise aplicada a automatización QA moderna:

- Sin enviar datos a la nube
- Sin depender de APIs externas
- Manteniendo control total del proyecto
- Funciona como un sidecar inteligente capaz de:
- Analizar features, steps, requisitos y resultados
- Detectar inconsistencias y huecos de cobertura
- Proponer steps BAM declarativos
- Generar documentación viva
- Validar el cumplimiento de normas BAM internas
- Ayudar a construir mejor trazabilidad real (BMS)

Se trata de un Proof of Concept, orientado a mostrar visión arquitectónica, capacidad técnica y uso responsable de IA en QA.

## 🧠 3. Estado actual del proyecto

🚧 Proyecto en fase inicial (PoC)

🧠 Diseñado para trabajar con modelos IA locales (Ollama, LM Studio, Llama.cpp…)

🔒 Privacidad total (sin cloud)

💬 Asistencia, no sustitución

🧩 Enfocado en integrarse con proyectos BAM/Playwright

## 🎯 4. Objetivos funcionales 

Estos son los objetivos funcionales reales del proyecto, alineados con el roadmap:

### ✔ 4.1. Generar automáticamente steps/tests BAM desde features Gherkin

Esta es la función clave de DINO.

DINO analiza el texto Gherkin y sugiere:
- El método de Page que debe usarse
- El componente adecuado (Button, Modal, Wait, Navigation…)
- El nombre declarativo del step
- La estructura BAM correcta (sin await, usando this.getPage())
- El patrón recomendado según el plugin ESLint BAM-UX

Ejemplo realista:

Entrada:
``` gherkin
Scenario: User searches for a product
  When the user searches for "Laptop"
```
Salida sugerida:
``` ts
When('the user searches for {string}', function (query: string) {
  const user = this.getPage(HomePage);
  user.searchesFor(query);
});
```

### ✔ 4.2. Decorar automáticamente features Gherkin con metadata BMS

Transforma un escenario simple en uno trazable:

Entrada:
``` gherkin
Scenario: User logs in successfully`
```
Salida sugerida:

``` gherkin
@ID=TC-002
@Title=Valid_login_shows_username
@Description=Valid_user_logs_in_and_sees_his_name_in_the_navbar
@Module=Authentication
@Component=Login
@Pre=User_not_authenticated
@AC1=Welcome_message_includes_username
@AC2=Login_modal_should_disappear_after_success
@Data=credentials.valid
@Priority=HIGH
@Risk=LOW
Scenario: User logs in successfully
```


### ✔ 4.3. Validar que las pruebas cumplen las normas BAM

Incluye:
- No usar await en tests
- Estructura declarativa estricta
- Uso correcto de this.getPage()
- Naming DSL BAM
- Validación BMS
- Consistencia entre módulos/componentes

### ✔ 4.4. Detectar gaps entre requisitos, features y pasos

DINO señala huecos como:
- Requisitos sin test
- Features sin AC
- AC no cubiertos
- Steps no utilizados
- Components orphan
- Tests sin prioridad o sin riesgo

### ✔ 4.5. Construir documentación viva
A partir de:
- Features con metadata
- JSON de ejecución
- Relación módulo/componente
- Riesgos, prioridades

DINO genera:

- Matrices de cobertura
- Test Plans
- Resúmenes ejecutivos para PO
- Mapas de calidad por componente


### ✔ 4.6. Análisis de trazas de ejecución BAM

Entrada: execution.json de BAM.

DINO puede:
- Identificar el componente que falló
- Sugerir la causa probable
- Detectar patrones de flakiness
- Proponer mejoras en el componente afectado
- Revisar tiempos, selectores, acciones y transiciones



## ⚙️5. Requisitos no funcionales

Tecnología: TypeScript + Node.js
Compatibilidad: Windows / Linux
Privacidad: 100% local, sin Internet
Extensibilidad: modular y configurado por comandos
Seguridad: nunca sobrescribir archivos sin confirmación

## 🧩 6. Roadmap del proyecto
Fase 0 – Base técnica (actual)
- CLI funcional
- Comando validate-project
- Reglas BAM básicas sin IA

Fase 1 – Generación de steps desde Gherkin
- Integración con modelos IA locales
- Prompts BAM específicos
- Generación de métodos, steps y naming DSL

Fase 2 – RAG ligero
- Indexación de código y metadata
- Análisis contextual del proyecto
- Detección de patrones y duplicados

Fase 3 – QA del QA
- Validación avanzada
- Comparación REQ ↔ Gherkin ↔ steps ↔ ejecución

Fase 4 – Documentación Viva
- Test Plan
- Cobertura
- Resumen de calidad

Fase 5 – Distribución
- Empaquetado como .exe
- Banner CLI
- Mejoras UX
