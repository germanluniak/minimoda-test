# Práctica clase 01: casos del registro de MiniModa con IA

**Sitio:** https://minimoda-navy.vercel.app/registro

> Así tiene que quedar tu entrega. Reemplazá cada `___tu respuesta aquí___` con lo tuyo.

## 1. Preparación
- Navegador y fecha: Google Chrome Version 156.0.8078.74 - 30/10/2026

## 2. Superficie elegida
- Elegí (chat o cowork): Chat Gemini en el navegador
- Por qué: Por que al estar integrado en el mismo navegador es más comodo, rápido y sencillo de utilizar. 

## 3. Preguntas a Gemini
| # | Pregunta | Respuesta (resumen) | ¿Acierto o error/invento? |
|---|----------|---------------------|---------------------------|
| 1 | ¿Qué campos pide el formulario de registro de https://minimoda-navy.vercel.app/registro? |La respuesta obtenida fue: El formulario de registro pide: Nombre, Email, Contraseña, Confirmar contraseña, Edad, País y Términos y condiciones | Acierto |
| 2 | ¿Cuál es el largo mínimo de la contraseña y qué edad se permite? | La respuesta obtenida fue: Según el formulario el largo mínimo de la contraseña es de 8 caracteres y la edad permitida es Un número entero entre 13 y 120 | Acierto |
| 3 | ¿Qué pasa si no acepto los términos? | La respuesta obtenida fue: Al intentar enviar el formulario, el sistema detectará que falta este requisito y te mostrará un mensaje de error o validación impidiéndote completar el registro | Acierto parcial |

- Un acierto: En el primero de los casos su respuesta fue correcta y completa, indicando todos los campos requeridos en el formulario de registro.
- Un error o invento: No ha cometido errores ni realizado inventos en las respuestas, aunque en la tercera pregunta no especificó el mensaje exacto que se muestra al no aceptar los términos.

## 4. Primer modo
- Superficie y modo: Gemini en el navegador, modo chat
- Prompt de ejemplo:
  ```
  Sos QA. Vamos a probar el registro de https://minimoda-navy.vercel.app/registro
  Campos: nombre, email, contraseña, confirmar contraseña, edad, país y aceptar términos.
  1. Listá las reglas que se ven, los datos válidos e inválidos y los valores límite.
  2. Escribí 6 casos de prueba con: título, precondiciones, pasos con datos concretos,
     resultado esperado, prioridad (high/medium/low) y tipo (functional/negative/boundary).
  No inventes mensajes: si no sabés el texto exacto, marcalo "A VERIFICAR".
  ```
- Qué devolvió: Identificó los 7 campos del registro y describió sus reglas, ejemplos de datos válidos e inválidos y valores límite.
- Diseño de 6 casos de pruebas para verificar el comportamiento del formulario, donde en cada uno incluye título, precondiciones, pasos con datos concretos, resultado esperado, prioridad y tipo de prueba.
- Propuso algunas reglas de validación, como que la contraseña debe tener al menos 8 caracteres y que la edad permitida está entre 13 y 120 años. Sin embargo, no aclaró si esas reglas realmente existen en el formulario o si son suposiciones.


## 5. Otra superficie: comparación con Cursor app (grok-4.7)
1. Ambos identificaron las reglas de validación y los valores límite, pero Cursor detalló más ejemplos y opciones disponibles en cada campo.
2. Ambos generaron los 6 casos solicitados con todos los elementos requeridos, aunque Cursor incluyó una prueba adicional del límite superior válido de edad (120 años).
3. Gemini describió los comportamientos esperados de forma general, mientras que Cursor incorporó los mensajes exactos obtenidos de la aplicación, cumpliendo mejor con la indicación de no inventarlos.

## 6. Mis 3 mejores casos (cargados en Qase, proyecto MiniModa)
Formato del título: `Registro: <qué se prueba>`
Captura de la suite en Qase con tus casos: `evidencias/qase-suite-casos.png`

### Caso 1: Registro exitoso con datos válidos
- Precondiciones: el usuario debe estar en https://minimoda-navy.vercel.app/registro con el formulario vacío y el correo a utilizar no debe estar registrado.
  - Pasos: 
  1. Ingresar "Juan Pérez" en el campo Nombre.
  2. Ingresar "juan.perez@test.com" en el campo Email.
  3. Ingresar "Password123" en el campo Contraseña.
  4. Ingresar "Password123" en el campo Confirmar contraseña.
  5. Ingresar "25" en el campo Edad.
  6. Seleccionar "Argentina" en el desplegable de País.
  7. Marcar la casilla Acepto los términos y condiciones.
  8. Hacer clic en el botón Crear cuenta.
- Resultado esperado: El sistema muestra el mensaje de éxito "¡Registro exitoso! Bienvenido/a a MiniModa, Juan Pérez. Te enviamos un email de bienvenida (ver Bandeja)."
- Evidencia: `evidencias/qase-MM-4-registro-alta-exitosa.png`

### Caso 2: Validación de límite inferior en Edad (Prueba negativa de frontera)
- Precondiciones: el usuario debe estar en https://minimoda-navy.vercel.app/registro con el formulario vacío
  - Pasos:
    1. Ingresar "Ana Pérez" en el campo Nombre.
    2. Ingresar "ana.perez@test.com" en el campo Email.
    3. Ingresar "Password123" en el campo Contraseña.
    4. Ingresar "Password123" en el campo Confirmar contraseña.
    5. Ingresar "12" en el campo Edad.
    6. Seleccionar "Argentina" en el desplegable de País.
    7. Marcar la casilla Acepto los términos y condiciones.
    8. Hacer clic en el botón Crear cuenta.
- Resultado esperado: El sistema impide el envío del formulario y muestra un mensaje "La edad debe estar entre 13 y 120"
- Evidencia: `evidencias/qase-MM-5-registro-password-7.png`

### Caso 3: Validación de longitud mínima de Contraseña
- Precondiciones: el usuario debe estar en https://minimoda-navy.vercel.app/registro con el formulario vacío
  - Pasos:
    1. Ingresar "Pedro Lopez" en el campo Nombre.
    2. Ingresar "pedro.lopez@test.com" en el campo Email.
    3. Ingresar "Pass123" en el campo Contraseña.
    4. Ingresar "Pass123" en el campo Confirmar contraseña.
    5. Ingresar "50" en el campo Edad.
    6. Seleccionar "Argentina" en el desplegable de País.
    7. Marcar la casilla Acepto los términos y condiciones.
    8. Hacer clic en el botón Crear cuenta.
- Resultado esperado: El sistema rechaza el registro debido a que no se cumple el requisito mínimo de 8 caracteres.
- Evidencia: `evidencias/qase-MM-6-registro-edad-12.png`

## 7. Mapa del harness
| Pieza | En lo que usé                                           |
|-------|---------------------------------------------------------|
| Modelo | Gemini: modo Automático (Gemini 3) / Cursor (grok-4.7)  |
| App | Gemini en Chrome / Cursor app                           |
| Harness | Ambos modelos pudieron acceder a la web para analizarla |
| MCP | No utilice.                                             |
| Skill | No utilice.                                             |

## 8. Entrega
- Link de tu repo (pegalo también en el Telegram): https://github.com/germanluniak/minimoda-test
