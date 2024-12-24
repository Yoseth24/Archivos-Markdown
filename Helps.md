# Project Overview

Welcome to Green Wizards Math Reasoning Step-by-Step! This project aims to enhance advanced models by developing and evaluating complex user prompts. For each pair of skills, generate prompts that integrate the skills in a sophisticated way. Prompts should be challenging enough that [latest models] are unlikely to produce accurate responses. Model outputs will be annotated to identify and correct errors.

## Key Terminology:

- **Prompt**: A question or statement designed to elicit a response from the model, incorporating two complex skills.
-   **Model Response**: The model’s step-by-step answer to the prompt, used for evaluation.
-   **Annotation**: The process of reviewing the model’s response for accuracy, relevance to the prompt, and proper skill use, while noting any reasoning errors.
-   **Error Identification**: Detecting reasoning flaws or gaps in the model’s application of skills.
-   **Error Correction**: Fixing identified errors and providing clear explanations for the corrections.
-   **Teaching Material**: If necessary, developing educational resources to explain and address reasoning errors.

# Task Attempt Workflow

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

# Task Specifications

## Step 1: Write a Prompt (math problem)
In this step, you will write a math problem for the model to solve. Problems should adhere to the specifications below.
### Specifications list
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


| Category  | Example | Explanation |
| ------------- | ------------- | -- |
|**Good Example** |Given a circle with a radius of r, a square is inscribed inside the circle. Calculate the area of the region outside the square but inside the circle.|This is a good example because it integrates geometry concepts (circle and square) and requires the model to compute areas of both shapes and then find the difference. It challenges the model to perform multiple steps and apply different geometric formulas, making it complex enough to potentially stump the model.|
|**Bad Example**|What is the area of a rectangle with a length of 5 units and a width of 3 units?|This problem is too simple for the task requirements. It only requires a basic application of the area formula for rectangles ($\text{Area} = \text{length} \times \text{width}$) and does not challenge the model's problem-solving abilities. It lacks complexity and is not suitable for evaluating the model’s capacity to handle more advanced tasks.|
|**Bad Example**| What is the sum of the first 10 positive integers? Also, find the area of a triangle with a base of 5 units and a height of 7 units.|This problem is unsuitable because it includes two separate math problems in one prompt, which goes against the requirement that a math problem should have only one correct solution. Both problems individually are also too simple.|

10. Math problems **should not** contain any **spelling, grammar, or formatting errors**

**Feel free to find inspiration in this** [Math Problems Bank](https://docs.google.com/spreadsheets/d/1dMXhZEsHycYRSz_7vxgjYGbTWPMSJwtZ6r6IoSE5eXI/edit?gid=0#gid=0)

### Step 1a: Solve the Math Problem
Next, you will solve the math problem and verify the problem satisfies all the constraints above.

### Step 1b: Keep Prompting the Model until it Produces an Incorrect Response

Next, you will submit the math problem for the model to solve. If the model answers <ins>correctly</ins>, or only makes calculation errors, submit a different problem. Keep submitting problems **until the model produces an incorrect response**.

<img src="/Imagenes/img1.png" alt="drawing" width="700"/>

IMPORTANT NOTE:
    - Your task is to create a prompt that results in at least one reasoning error.
        - If your prompt only produces a calculation error, revise it to introduce a reasoning error before completing the task.
## Step 2: Rate the Correctness of Each Step

### When you identify a mistake in the model's response, follow these steps:
1. Mark the step as "Incorrect."
2. Explain the mistake and why it is wrong.
3. Rewrite the model’s reasoning with a corrected solution.
4. Select either **Reasoning Error** or **Calculation Error**.
   
### Criteria for Incorrect Labeling:
- **Incorrect**: A clear mathematical error is present.
- **Not Incorrect**: Issues like poor LaTeX formatting, valid but inefficient solutions, or suboptimal expressions that are still mathematically correct should not be labeled as incorrect.

When asked to rate if each step is done correctly or incorrectly, you will see 4 possible step labels: Incorrect - LLM is appropriate, Correct - LLM is appropriate, Incorrect - Python is appropriate, Correct - Python is appropriate. We will review more in detail below the two images!

<img src="/Imagenes/img2.png" alt="drawing" width="700"/>

The below flow charts show how to think through which of the 4 step labels to choose:

<img src="/Imagenes/img3.png" alt="drawing" width="700"/>

### Each step label is designed to address two questions:
1. **Is the math in the step correct?**
   - This is straightforward: verify if the mathematical operations performed are correct and the model’s output is accurate.
2. **Should this step ideally be solved using the model’s LLM or Python capabilities?**
    - This question relates to determining whether a step should be solved using the model's large language model (LLM) or its Python capabilities (implicit code execution, or ICE).
    - LLMs are better suited for tasks involving reasoning, logic, or proofs. Python is ideal for more complex calculations or numerical tasks where precision is crucial.
  

### When to Use LLM or Python
- Select LLM is ideal to solve the problem when the step is similar to:
    - <ins>_Essentially when the math problem requires abstract concept, word, or pattern recognition_</ins>
        - **Word problems** that require an understanding of natural language
        - **Pattern recognition**, like simple sequences
        - Deducing or applying **proofs, theorems, propositions, and corollaries** where the model relies on step-by-step reasoning, intuition, and context
        - **Abstract math**, such as measure theory (e.g. prove a certain Lebesgue set is measurable) or number theory (e.g., determining if an extension of a field has finitely many intermediate fields)
        - Theoretical probability, (e.g. What is P(A)P(B) for independent A and B)
- Select Python is ideal to solve the problem when the step is similar to:
    - <ins>_Essentially when the math problem involves a very precise input\/output_</ins>
        - **Simple variable-based calculus** (e.g. derive x^2 + 2x + 7)
        - Applying number tests that don’t rely on large computation, e.g. calculating a limit or applying a ratio test or root test
        - **Manipulating or isolating quantifiers or variables**, where a solution can be calculated (e.g. isolate y in 2x + 3 = 7y; or substitute y = 3z+3 when x = 10+7y)
        - **Basic arithmetic** with small numbers (under 100, e.g. 25 + 37)
        - **Algebra or solving for variables** (e.g. solve for x in 3x+7=3) 
        - **Precise numerical computation or complex arithmetic**, where there are large numbers or multi-step calculations that might introduce errors when using an LLM (e.g., what is 938193 x 93189318)
        - **Trigonometry and evaluation of calculus concepts** (e.g. find the quadratic roots of x^2 - 7x + 4; or solve cos(x)^2 + sin(x^2) = 0 at x = 0)
        - **Matrix operations** or calculations involving vectors (e.g. find a vector orthogonal to v1 = [3,0,2]; or multiply M_1 and M_2 where each is a matrix; or find the determinant of M_3)
        - **Applied probability and statistics**, such as calculating standard deviations or regressions, (e.g. what is the standard deviation of this dataset; or binomial distribution, such as what is the probability of getting exactly 8 heads in 15 coin flips, assuming the coin is fair?)
        - **Distributions or calculations that require calculating areas under a curve, evaluating an integral, or volume** (e.g. what is the probability that a normally distributed variable with mean 100 and standard deviation 15 falls between 90 and 120?; or, “what is the volume of this solid evolution (3x+1)^0.5 at these boundaries …”)
        - **Numerical approximations or evaluating series** (e.g. a Monte Carlo approximation, a binomial distribution, applying Simpson’s rule or a Striling approximation)

### Step 2a: Write a rationale for incorrect steps

In this part of the task, you will provide a rationale for any steps that were rated as Incorrect

#### Specifications List

1. Rationales should clearly explain **why the step is incorrect**
2. Rationales should use **proper spelling and grammar**
3. Rationales do not require LaTeX. If you do use LaTeX, the LaTeX should follow the [style guide](https://docs.google.com/document/d/12wirrYekv_ReVy9FcjvUZWBfCSkRcFAhZ_gbM5k3p_A/pub).
4. Rationales should not contain “model”, “AI”, “LLM”, etc

## Step 3: Rewrite Incorrect Steps

### Rewriting Guidelines
- Maintain Sequential Integrity: Ensure that your rewrite preserves the logical order of the original reasoning and includes the same level of detail.
- Clarity in Rewriting: Rewrite the step clearly and concisely, using simple language that avoids jargon. The rewrite should be self-contained and understandable, following a logical sequence of reasoning.
- Focus on Problem-Solving: Only include information necessary to solve the problem. Do not add extraneous details like definitions of basic concepts.
  
### Types of Errors
1. Calculation Errors: Simple arithmetic or operational mistakes (e.g., incorrect multiplication).
2. Reasoning Errors: Mistakes in understanding the process or logic behind a solution.

For this project, each response must include at least one reasoning error. If the only error is a calculation mistake, modify the prompt to create a reasoning error.

### <ins>**Examples of Errors**</ins>

**Example 1: Rectangle Area (Reasoning Error)**
- **Problem**: A rectangle’s length is doubled, and its width is increased by 3 meters. What is the new area?
-**Incorrect Answer**: Adds the dimensions instead of multiplying.
    - **Error**: Misunderstanding the formula for area.

**Example 2: Car Rental (Calculation Error)**

- **Problem**: How much will it cost to rent a car for 3 days and drive 150 miles?
- **Incorrect Answer**: Correct understanding, but miscalculates the total cost.
    - **Error**: Simple arithmetic mistake.
  
## Step 4: Regenerate

<ins>Repeat the process until Final Answer is reached</ins>
- Regenerate the response after each correction, restarting the model's train of thought
- Repeat Steps 2-4 until the model arrives at the correct answer

## Step 5: Summarize
In this final step, you should summarize the task using the checkboxes and short responses, according to the following dimensions:

- **Accuracy**
    - Does the original model response (BEFORE REWRITES) make an error?
- **Instruction Following**
    - Does the response AFTER REWRITES follow all prompt instructions?
- **Skills Check**
    - Does the response AFTER REWRITES utilize both of the skills selected in step 1?
- **First Incorrect Step**
    - What was the first incorrect step with a reasoning error made by the model?
- **Skills Gap**
    - What Skill(s) does the model fail at or not include in the response?
      
# Apendix
## Python vs. LLM Guidance (labeling calculation and reasoning errors)
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

| Categoría  | Ejemplo | Explicación |
| ------------- | ------------- | -- |
|**Buen Ejemplo** |Dado un círculo con radio r, un cuadrado está inscrito dentro del círculo. Calcular el área de la región fuera del cuadrado pero dentro del círculo.|Este es un buen ejemplo porque integra conceptos de geometría (círculo y cuadrado) y requiere que el modelo calcule áreas de ambas formas y luego encuentre la diferencia. Desafía al modelo a realizar múltiples pasos y aplicar diferentes fórmulas geométricas, haciéndolo lo suficientemente complejo para potencialmente confundir al modelo.|
|**Mal Ejemplo**|¿Cuál es el área de un rectángulo con longitud de 5 unidades y ancho de 3 unidades?|Este problema es demasiado simple para los requisitos de la tarea. Solo requiere una aplicación básica de la fórmula del área para rectángulos ($\text{Área} = \text{longitud} \times \text{ancho}$) y no desafía las habilidades de resolución de problemas del modelo. Carece de complejidad y no es adecuado para evaluar la capacidad del modelo para manejar tareas más avanzadas.|
|**Mal Ejemplo**| ¿Cuál es la suma de los primeros 10 números positivos? Además, encuentra el área de un triángulo con base de 5 unidades y altura de 7 unidades.|Este problema no es adecuado porque incluye dos problemas matemáticos separados en un prompt, lo que va en contra del requisito de que un problema matemático debe tener solo una solución correcta. Ambos problemas individualmente también son demasiado simples.|

10. Los problemas matemáticos **no deben** contener **errores de ortografía, gramática o formato**

**Siéntase libre de encontrar inspiración en este** [Banco de Problemas Matemáticos](https://docs.google.com/spreadsheets/d/1dMXhZEsHycYRSz_7vxgjYGbTWPMSJwtZ6r6IoSE5eXI/edit?gid=0#gid=0)

#### Paso 1a: Resolver el Problema Matemático
A continuación, resolverá el problema matemático y verificará que el problema satisfaga todas las restricciones anteriores.

#### Paso 1b: Seguir Presentando el Problema al Modelo hasta que Produzca una Respuesta Incorrecta

A continuación, presentará el problema matemático para que el modelo lo resuelva. Si el modelo responde <ins>correctamente</ins>, o solo comete errores de cálculo, presente un problema diferente. Siga presentando problemas **hasta que el modelo produzca una respuesta incorrecta**.

<img src="/Imagenes/img1.png" alt="drawing" width="700"/>

NOTA IMPORTANTE
    - Su tarea es crear un prompt que resulte en al menos un error de razonamiento.
    - Si su prompt solo produce un error de cálculo, revíselo para introducir un error de razonamiento antes de completar la tarea.

### Paso 2: Calificar la Corrección de Cada Paso

#### Cuando identifique un error en la respuesta del modelo, siga estos pasos:
1. Marque el paso como "Incorrecto."
2. Explique el error y por qué está mal.
3. Reescriba el razonamiento del modelo con una solución corregida.
4. Seleccione **Error de Razonamiento** o **Error de Cálculo**.
   
#### Criterios para Etiquetado Incorrecto:
- **Incorrecto**: Hay un error matemático claro presente.
- **No Incorrecto**: Problemas como formato LaTeX deficiente, soluciones válidas pero ineficientes, o expresiones subóptimas que son matemáticamente correctas no deben etiquetarse como incorrectas.

Cuando se le pida calificar si cada paso está hecho correcta o incorrectamente, verá 4 posibles etiquetas de paso: Incorrecto - LLM es apropiado, Correcto - LLM es apropiado, Incorrecto - Python es apropiado, Correcto - Python es apropiado. ¡Revisaremos más en detalle a continuación las dos imágenes!

<img src="/Imagenes/img2.png" alt="drawing" width="700"/>

Los diagramas de flujo a continuación muestran cómo pensar qué etiqueta de las 4 elegir:

<img src="/Imagenes/img3.png" alt="drawing" width="700"/>

#### Cada etiqueta de paso está diseñada para abordar dos preguntas:
1. **¿Las matemáticas en el paso son correctas?**
   - Esto es sencillo: verificar si las operaciones matemáticas realizadas son correctas y la salida del modelo es precisa.
2. **¿Este paso debería resolverse idealmente usando las capacidades LLM o Python del modelo?**
    - Esta pregunta se relaciona con determinar si un paso debe resolverse usando el modelo de lenguaje grande (LLM) del modelo o sus capacidades Python (ejecución implícita de código, o ICE).
    - Los LLM son más adecuados para tareas que involucran razonamiento, lógica o demostraciones. Python es ideal para cálculos más complejos o tareas numéricas donde la precisión es crucial.

#### Cuándo Usar LLM o Python
- Seleccione LLM es ideal para resolver el problema cuando el paso es similar a:
    - <ins>_Esencialmente cuando el problema matemático requiere concepto abstracto, palabra o reconocimiento de patrones_</ins>
        - **Problemas verbales** que requieren comprensión del lenguaje natural
        - **Reconocimiento de patrones**, como secuencias simples
        - Deducir o aplicar **pruebas, teoremas, proposiciones y corolarios** donde el modelo se basa en razonamiento paso a paso, intuición y contexto
        - **Matemáticas abstractas**, como teoría de la medida (ej. probar que cierto conjunto de Lebesgue es medible) o teoría de números (ej., determinar si una extensión de un campo tiene finitos campos intermedios)
        - Probabilidad teórica, (ej. Cuál es P(A)P(B) para A y B independientes)
- Seleccione Python es ideal para resolver el problema cuando el paso es similar a:
    - <ins>_Esencialmente cuando el problema matemático involucra una entrada/salida muy precisa_</ins>
        - **Cálculo simple basado en variables** (ej. derivar x^2 + 2x + 7)
        - Aplicar pruebas numéricas que no dependen de gran computación, ej. calcular un límite o aplicar una prueba de razón o prueba de raíz
        - **Manipular o aislar cuantificadores o variables**, donde se puede calcular una solución (ej. aislar y en 2x + 3 = 7y; o sustituir y = 3z+3 cuando x = 10+7y)
        - **Aritmética básica** con números pequeños (menores a 100, ej. 25 + 37)
        - **Álgebra o resolución de variables** (ej. resolver x en 3x+7=3) 
        - **Computación numérica precisa o aritmética compleja**, donde hay números grandes o cálculos de múltiples pasos que podrían introducir errores al usar un LLM (ej., cuál es 938193 x 93189318)
        - **Trigonometría y evaluación de conceptos de cálculo** (ej. encontrar las raíces cuadráticas de x^2 - 7x + 4; o resolver cos(x)^2 + sin(x^2) = 0 en x = 0)
        - **Operaciones matriciales** o cálculos involucrando vectores (ej. encontrar un vector ortogonal a v1 = [3,0,2]; o multiplicar M_1 y M_2 donde cada uno es una matriz; o encontrar el determinante de M_3)
        - **Probabilidad y estadística aplicada**, como calcular desviaciones estándar o regresiones, (ej. cuál es la desviación estándar de este conjunto de datos; o distribución binomial, como cuál es la probabilidad de obtener exactamente 8 caras en 15 lanzamientos de moneda, asumiendo que la moneda es justa?)
        - **Distribuciones o cálculos que requieren calcular áreas bajo una curva, evaluar una integral o volumen** (ej. cuál es la probabilidad de que una variable normalmente distribuida con media 100 y desviación estándar 15 caiga entre 90 y 120?; o, "cuál es el volumen de esta evolución sólida (3x+1)^0.5 en estos límites …")
        - **Aproximaciones numéricas o evaluación de series** (ej. una aproximación de Monte Carlo, una distribución binomial, aplicando la regla de Simpson o una aproximación de Striling)

