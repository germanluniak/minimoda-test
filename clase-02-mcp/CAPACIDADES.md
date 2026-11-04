# Capacidades del agente MCP 

## Playwright MCP

El agente tomó el control del navegador a través de Playwright MCP para poner a prueba de forma integral el flujo de compra de la tienda. Sin necesidad de guías visuales o coordenadas fijas, navegó la interfaz interpretando la estructura accesible de cada pantalla para identificar botones y componentes por sus roles reales.

En cuestión de segundos, recorrió la portada, localizó un producto específico y validó sus detalles clave —como variante, precio promocional y stock disponible— para luego agregarlo al carrito. Finalmente, corroboró de forma autónoma que el contador de la cabecera, las cantidades e importes del resumen de compra coincidieran con precisión, demostrando capacidad plena para interactuar, auditar y documentar procesos web complejos de principio a fin.

## MCP de casos de prueba

Se usó el MCP local `casos-de-prueba` para generar un archivo Markdown con el caso de prueba **Agregar un producto con stock al carrito**. El caso define:

- El requisito funcional.
- Los pasos de ejecución.
- Datos de prueba de un producto y variante con stock.
- El resultado esperado en el carrito.
- Prioridad alta.

El caso quedó guardado en `casos/2026-11-04T19-17-39-523Z-agregar-un-producto-con-stock-al-carrito.md`.

## Tiempo ahorrado frente a hacerlo a mano

La automatización eliminó la necesidad de abrir el navegador, buscar el producto, verificar su stock y transcribir manualmente los datos del carrito. Para este recorrido, la ejecución automática supuso un ahorro de 3 a 5 minutos frente a una comprobación manual.

Por su parte, la generación del caso mediante el MCP local tomó solo unos segundos tras ingresar los datos. Redactar y detallar a mano cada paso de ejecución, prerrequisitos y resultados esperados suele tomar entre 10 y 15 minutos.

En conjunto, el ahorro total para esta prueba y su documentación se sitúa entre 13 y 20 minutos. Esta cifra es una estimación orientativa que variará según la complejidad del flujo o la experiencia del QA.

## Límites encontrados
Durante el proceso, fue necesario autorizar manualmente en múltiples ocasiones la ejecución de tareas y la creación de los MCP debido a la gestión de permisos del entorno, lo que interrumpió la continuidad del flujo de trabajo del agente.