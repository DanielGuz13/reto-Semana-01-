° Reto Semana 3: Analizador de Ventas 📊

    - Descripción del Programa.
    Este programa es una herramienta de procesamiento de datos diseñada para generar reportes consolidados de ventas.
    Recibe un flujo de datos en formato CSV que contiene transacciones diarias (fecha, producto, cantidad y precio unitario) y genera un reporte limpio, unificado y ordenado por ingreso total.

    - Instrucciones de uso.
    parsear_linea(linea):
    Es una función de validación y extracción. Recibe una línea de texto del CSV y utiliza `.split(',')` para separar sus componentes. Implementa un bloque `try/except` para intentar convertir la cantidad a entero y el precio a decimal (`float`). Si la línea contiene errores, carece de columnas o tiene datos corruptos, captura el error (`ValueError`) e ignora esa fila silenciosamente retornando `None`, evitando que el programa colapse.

    procesar_ventas(lineas):
    Esta función actúa como el "cerebro" lógico de la agrupación. Utiliza un diccionario para consolidar las ventas usando el nombre del producto como clave, sumando las unidades y calculando el ingreso acumulado. Al finalizar, calcula el precio promedio y utiliza `sorted()` con una expresión `lambda` para ordenar los productos de mayor a menor rentabilidad.

    imprimir_reporte(resultados):
    Se encarga de formatear la salida. Imprime los datos en formato CSV a la salida estándar, aplicando las reglas de negocio para que las unidades sean números enteros y los valores monetarios (ingreso total y precio promedio) tengan exactamente dos decimales.

    Procesamiento de datos (Bloque `main`):
    Es el motor del programa. En lugar de cargar todo el archivo en memoria, lee los datos a través de la entrada estándar (`sys.stdin`), los envía a la función de procesamiento y finalmente llama a la función de impresión para entregar el reporte consolidado.

  -Ejemplo de entrada:
    fecha,producto,cantidad,precio_unitario
    2026-01-01,Laptop,2,15000.00
    2026-01-02,Mouse,10,250.00
    2026-01-03,Laptop,1,14500.00
    2026-01-04,Teclado,5,800.00
    2026-01-05,Mouse,8,250.00
   

    -Salida esperada:
    producto,unidades_vendidas,ingreso_total,precio_promedio
    Laptop,3,44500.00,14833.33
    Mouse,18,4500.00,250.00
    Teclado,5,4000.00,800.00