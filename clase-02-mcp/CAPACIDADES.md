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

El caso quedó guardado en `casos/CP-001-agregar-un-producto-con-stock-al-carrito.md`.

## Tiempo ahorrado frente a hacerlo a mano

La automatización eliminó la necesidad de abrir el navegador, buscar el producto, verificar su stock y agregar el producto al carrito. Para este recorrido, la ejecución automática lo hizo en un tiempo de 36 segundos mientras que manualmente fue de 55 segundos.

Por su parte, la generación del caso mediante el MCP el agente lo resolvió en apenas 8 segundos mientras que manualmente la generacion del caso se realizó en 3 minutos 47 segundos.

Por lo que el ahorro de tiempo es considerable mucho mas a la hora de generar un caso de pruebas desde cero y de forma manual. Ya que para la primer parte de la prueba solo se ahorraron 19 segundos y para la segunda la diferencia fue aún mayor dado que el ahorro fue de 3 minutos 39 segundos.

## Límites encontrados
Durante el proceso, fue necesario autorizar manualmente en múltiples ocasiones la ejecución de tareas y la creación de los MCP debido a la gestión de permisos del entorno, lo que interrumpió la continuidad del flujo de trabajo del agente.