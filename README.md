# Tarea 3 · La factura bajo el microscopio
Pareja: (nombre 1) y (nombre 2) · GitHub: (usuario 1), (usuario 2)

## Reto 1 · Compilar desde la terminal
- Comando usado y resultado (captura: capturas/reto1.png)
- ¿Qué es Factura.java? Es el archivo de código fuente
¿Y Factura.class? Es el archivo que se convierte en bytecode
¿Quién ejecuta el .class? Lo ejecuta JVM, es quien interpreta el bytecode
- ¿Por qué no se ha generado Factura.class la primera vez?
Porque el archivo comete errores

## Reto 2 · Errores de compilación
| Nº | Línea | Mensaje de javac | Tipo (léxico / sintaxis / semántica) | Corrección |
|----|-------|------------------|--------------------------------------|------------|
| 1  | 15 | error: illegal character: '#' | sintaxis | double precio = nextDouble(); |
| 2  | 17 | error: ';' expected / int cantidad = sc.nextInt() | sintaxis | int cantidad = sc.nextInt(); |
| 3  | 29 |   | semántica | double total = (base - descuento) * (1 + IVA); |
Captura del programa funcionando: capturas/reto2.png

## Reto 3 · Depuración del error lógico
| Variable | Valor esperado | Valor real |
|----------|----------------|------------|
| descuento |    18,00      |     6,00   |
| total     |    123,42     |   137,94   |
- Línea del error y explicación: Linea 27, el programa no hacia bien el cacula ya que no tenia encuenta la suma del descuento por no ser añadida
- Corrección: añadir  "descuento = descuento + base * 0.05;"
- Mi propia prueba (producto, precio, cantidad, socio → total):
Captura del depurador: capturas/reto3.png

## Reto 4 · Reutilización
- Métodos creados y para qué sirve cada uno: static double calcularDescuento(double base, boolean socio) --> Esto es la declaración de un método en Java. Sirve para calcular un descuento según el precio y si el cliente es socio o no.
    static double aplicarIVA(double importe) -> Esto es la declaración de un método en Java que sirve para calcular el IVA de un importe o devolver el precio con el IVA incluido, según cómo se programe el método.
- ¿Qué ventaja tiene frente al código anterior? -> La principal diferencia entre el primer programa Factura y el segundo es que el primero está organizado en métodos y el segundo tiene casi toda la lógica dentro del main.
Comparación de los dos programas
Característica	Primero	Segundo
Organización	Utiliza métodos separados.	Tiene casi todo dentro de main.
Descuento	Lo calcula con calcularDescuento().	Lo calcula directamente con if.
IVA	Lo calcula con aplicarIVA().	Lo calcula directamente en main.
Reutilización	Puedes utilizar los métodos en otros programas.	Para reutilizar los cálculos tendrías que copiar el código o reorganizarlo.
Facilidad para principiantes	Requiere entender los métodos.	Es más sencillo para empezar.
Mantenimiento	Es más fácil modificar cada cálculo por separado.	Si el programa crece, puede resultar más difícil de mantener.
Errores	Permite probar los cálculos por separado.	Es más difícil comprobar cada parte de forma independiente.

## Reto 5 · ¿Qué lenguaje elegirías?
- Caso A (web de la tienda):
- Caso B (propuesta en ensamblador):
