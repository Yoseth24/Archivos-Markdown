## Project Overview

Welcome to Green Wizards Math Reasoning Step-by-Step! This project aims to enhance advanced models by developing and evaluating complex user prompts. For each pair of skills, generate prompts that integrate the skills in a sophisticated way. Prompts should be challenging enough that [latest models] are unlikely to produce accurate responses. Model outputs will be annotated to identify and correct errors.

### Key Terminology:

- **Prompt**: A question or statement designed to elicit a response from the model, incorporating two complex skills.
-   **Model Response**: The model’s step-by-step answer to the prompt, used for evaluation.
-   **Annotation**: The process of reviewing the model’s response for accuracy, relevance to the prompt, and proper skill use, while noting any reasoning errors.
-   **Error Identification**: Detecting reasoning flaws or gaps in the model’s application of skills.
-   **Error Correction**: Fixing identified errors and providing clear explanations for the corrections.
-   **Teaching Material**: If necessary, developing educational resources to explain and address reasoning errors.

### Task Attempt Workflow

1. **PROMPT** - _Write and Solve an Elegant Math Problem_
    - Select two Skills to incorporate into a prompt (you must use both)
    - Write a prompt that can stump the model (causing it to make a reasoning error)
    - Make sure your problem can be solved
2. **RESPONSE** - _Rate the Correctness of Each Step_
    - Check the model’s response, determining whether each step is correct or incorrect
      - Determine if the step should be solved using LLM (text-based), or python (code-based computations).
      - If the response does not have any reasoning errors, repeat Step 1.
    - Write a brief justification explaining the error
3. **REWRITING** - _Rewrite incorrect steps_
    - Correct the model's reasoning by rewriting any incorrect steps
    - Write a brief justification explaining the changes
4. **REGENERATE** - _Repeat the process until the Final Answer is reached_
    - Regenerate the response after each correction, restarting the model's train of thought
    - Repeat Steps 2-4 until the model arrives at the correct answer
5. **SUMMARIZE** - _Summarize the task using the checkboxes and short responses_
    - Accuracy - Does the original model response (BEFORE REWRITES) make an error?
    - Instruction Following - Does the response AFTER REWRITES follow all prompt instructions?
    - Skills Check - Does the response AFTER REWRITES utilize both of the skills selected in step 1?
    - First Incorrect Step - What was the first incorrect step with a reasoning error made by the model?
    - Skills Gap - What Skill(s) does the model fail at or not include in the response?
### Task Specifications

##### Step 1: Write a Prompt (math problem)
In this step, you will write a math problem for the model to solve. Problems should adhere to the specifications below.
##### Specifications list
1. Math problems **must** lead to an error in reasoning in at least one of the steps in the model’s initial response
2. Math problems **must** use proper LaTeX formatting for all mathematical expressions.
3. Prompts **must** be original.
4. Math problems must be solvable
    a. Avoid problems that don't contain the information necessary to solve them
    b. Avoid problems with impossible scenarios, for example:
        i. Dividing by zero
        ii. Asking for the square root of a negative number if the domain is real numbers
    c. Avoid problems containing terms, concepts, theorems, or lemmas that do not adhere to mathematical rules
5. Math problems **must** have **only one correct solution**
    + Avoid problems that have many potential answers
    - ⭐️Answers must be either a number or a mathematical expression
    - ⭐️Answers should be able to be read by something like Python or Wolphram Alpha
6. ⭐️There must only be one answer to the prompt
    - A question like “find all the roots of this quadratic x^2 + 5x + 6” is not a valid prompt because it would result in two answers, -2 and -3
    - A better question to use is “what is the minimum of the roots of this quadratic x^2 + 5x + 6” because the ground truth final answer is -3 only.
7. ⭐️Prompts must not ask for proofs
    - ⭐️Prompts can only ask questions that result in an answer that can be machine verified
    - ⭐️This is an example of a prompt that would fail:
       - In a regular hexagon, three diagonals are drawn, intersecting at the center of the hexagon. The diagonals divide the hexagon into $6$ congruent triangles, $3$ of which are colored red and the remaining $3$ are colored blue. Prove that there exists a coloring of the triangles such that it is possible to draw a line that passes through the center of the hexagon and divides it into two parts that are each one color.

8. ⭐️Prompts **must** not ask multiple questions in the problem statement
    - ⭐️Prompts must only ask for one question and one answer
    - ⭐️This is an example of a prompt that would fail:
      - Given that $\sin \theta = \frac{1}{3}$, find the value of $\frac{\cos^3 2\theta}{\cos^2 3\theta}$, considering only the principal value of $\theta$. Check if the resulting expression is a perfect cube, and identify any degenerate cases for the values of $\theta$.

9. Math problems must be **sufficiently complex, but not contrived**
    - Problems should be complex enough to stump the model but also not contrived, meaning that the problems should reflect realistic scenarios/ask

---

## Descripción General del Proyecto
¡Bienvenido a Green Wizards Math Reasoning Step-by-Step! Este proyecto busca mejorar modelos avanzados mediante el desarrollo y evaluación de prompts complejos. Para cada par de habilidades, genere prompts que integren las habilidades de manera sofisticada. Los prompts deben ser lo suficientemente desafiantes para que [últimos modelos] tengan pocas probabilidades de producir respuestas precisas. Las salidas del modelo serán anotadas para identificar y corregir errores.

### Terminología Clave:
- **Prompt**: Una pregunta o declaración diseñada para obtener una respuesta del modelo, incorporando dos habilidades complejas.
- **Respuesta del Modelo**: La respuesta paso a paso del modelo al prompt, utilizada para evaluación.
- **Anotación**: El proceso de revisar la respuesta del modelo por precisión, relevancia al prompt y uso adecuado de habilidades, mientras se señalan errores de razonamiento.
- **Identificación de Errores**: Detectar fallas o vacíos de razonamiento en la aplicación de habilidades del modelo.
- **Corrección de Errores**: Corregir errores identificados y proporcionar explicaciones claras para las correcciones.
- **Material Didáctico**: Si es necesario, desarrollar recursos educativos para explicar y abordar errores de razonamiento.

### Flujo de Trabajo del Intento de Tarea
1. **PROMPT** - *Escribir y Resolver un Problema Matemático Elegante*
    - Seleccionar dos Habilidades para incorporar en un prompt (debe usar ambas)
    - Escribir un prompt que pueda confundir al modelo (causando un error de razonamiento)
    - Asegurarse de que su problema pueda resolverse
2. **RESPUESTA** - *Calificar la Corrección de Cada Paso*
    - Revisar la respuesta del modelo, determinando si cada paso es correcto o incorrecto
      - Determinar si el paso debe resolverse usando LLM (basado en texto) o python (cálculos basados en código).
      - Si la respuesta no tiene errores de razonamiento, repetir Paso 1.
    - Escribir una breve justificación explicando el error
3. **REESCRITURA** - *Reescribir pasos incorrectos*
    - Corregir el razonamiento del modelo reescribiendo cualquier paso incorrecto
    - Escribir una breve justificación explicando los cambios
4. **REGENERAR** - *Repetir el proceso hasta alcanzar la Respuesta Final*
    - Regenerar la respuesta después de cada corrección, reiniciando la línea de pensamiento del modelo
    - Repetir Pasos 2-4 hasta que el modelo llegue a la respuesta correcta
5. **RESUMIR** - *Resumir la tarea usando las casillas de verificación y respuestas cortas*
    - Precisión - ¿La respuesta original del modelo (ANTES DE REESCRITURAS) tiene un error?
    - Seguimiento de Instrucciones - ¿La respuesta DESPUÉS DE REESCRITURAS sigue todas las instrucciones del prompt?
    - Verificación de Habilidades - ¿La respuesta DESPUÉS DE REESCRITURAS utiliza ambas habilidades seleccionadas en el paso 1?
    - Primer Paso Incorrecto - ¿Cuál fue el primer paso incorrecto con error de razonamiento hecho por el modelo?
    - Brecha de Habilidades - ¿Qué Habilidad(es) falla el modelo o no incluye en la respuesta?

### Especificaciones de la Tarea
##### Paso 1: Escribir un Prompt (problema matemático)
En este paso, escribirá un problema matemático para que el modelo resuelva. Los problemas deben cumplir con las especificaciones siguientes.
##### Lista de especificaciones
1. Los problemas matemáticos **deben** conducir a un error de razonamiento en al menos uno de los pasos de la respuesta inicial del modelo
2. Los problemas matemáticos **deben** usar formato LaTeX apropiado para todas las expresiones matemáticas.
3. Los prompts **deben** ser originales.
4. Los problemas matemáticos deben ser resolubles
    a. Evitar problemas que no contengan la información necesaria para resolverlos
    b. Evitar problemas con escenarios imposibles, por ejemplo:
        i. División por cero
        ii. Pedir la raíz cuadrada de un número negativo si el dominio son números reales
    c. Evitar problemas que contengan términos, conceptos, teoremas o lemas que no se adhieran a reglas matemáticas
5. Los problemas matemáticos **deben** tener **solo una solución correcta**
    + Evitar problemas que tengan múltiples respuestas posibles
    - ⭐️Las respuestas deben ser un número o una expresión matemática
    - ⭐️Las respuestas deben poder ser leídas por algo como Python o Wolphram Alpha
6. ⭐️Debe haber solo una respuesta al prompt
    - Una pregunta como "encuentra todas las raíces de esta cuadrática x^2 + 5x + 6" no es un prompt válido porque resultaría en dos respuestas, -2 y -3
    - Una mejor pregunta sería "cuál es el mínimo de las raíces de esta cuadrática x^2 + 5x + 6" porque la respuesta final verdadera es solo -3.
7. ⭐️Los prompts no deben pedir demostraciones
    - ⭐️Los prompts solo pueden hacer preguntas que resulten en una respuesta que pueda ser verificada por máquina
    - ⭐️Este es un ejemplo de un prompt que fallaría:
       - En un hexágono regular, se dibujan tres diagonales que se intersectan en el centro del hexágono. Las diagonales dividen el hexágono en $6$ triángulos congruentes, $3$ de los cuales están coloreados de rojo y los $3$ restantes de azul. Demuestra que existe una coloración de los triángulos tal que es posible dibujar una línea que pase por el centro del hexágono y lo divida en dos partes que sean cada una de un solo color.
8. ⭐️Los prompts **no** deben hacer múltiples preguntas en el enunciado del problema
    - ⭐️Los prompts deben hacer solo una pregunta y pedir una respuesta
    - ⭐️Este es un ejemplo de un prompt que fallaría:
      - Dado que $\sin \theta = \frac{1}{3}$, encuentra el valor de $\frac{\cos^3 2\theta}{\cos^2 3\theta}$, considerando solo el valor principal de $\theta$. Verifica si la expresión resultante es un cubo perfecto e identifica cualquier caso degenerado para los valores de $\theta$.
9. Los problemas matemáticos deben ser **suficientemente complejos, pero no artificiales**
    - Los problemas deben ser lo suficientemente complejos para confundir al modelo pero no artificiales, es decir, los problemas deben reflejar escenarios realistas/preguntas

