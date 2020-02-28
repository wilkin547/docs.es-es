---
title: 'Coincidencia de patrones: Guía de C#'
description: Información sobre las expresiones de coincidencia de patrones en C#
ms.date: 04/10/2019
ms.technology: csharp-fundamentals
ms.assetid: 1e575c32-2e2b-4425-9dca-7d118f3ed15b
ms.openlocfilehash: db509a0ebf1e205e9996ba8102757fe8c0b9ea3a
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501629"
---
# <a name="pattern-matching"></a>Coincidencia de modelos

Los patrones comprueban que un valor tenga una determinada *forma* y pueden *extraer* información del valor cuando tiene la forma coincidente. La coincidencia de patrones proporciona una sintaxis más concisa para los algoritmos que se usan actualmente. Ya se crean algoritmos de coincidencia de patrones mediante la sintaxis existente. Se escriben instrucciones `if` o `switch` que comprueban valores. Luego, si esas instrucciones coinciden, se extrae y se usa la información de ese valor. Los nuevos elementos de sintaxis son extensiones de instrucciones con las que ya está familiarizado: `is` y `switch`. Estas nuevas extensiones combinan la comprobación de un valor y la extracción de esa información.

En este artículo se tratará la nueva sintaxis para mostrar cómo permite escribir un código conciso y legible. La coincidencia de patrones permite expresiones donde se separan el código y los datos, a diferencia de los diseños orientados a objetos, donde los datos y los métodos que los manipulan están estrechamente unidos.

Para mostrar estas nuevas expresiones, vamos a trabajar con estructuras que representan formas geométricas mediante instrucciones de coincidencia de patrones. Probablemente esté familiarizado con la creación de jerarquías de clases y de [métodos virtuales y métodos invalidados](methods.md#inherited) para personalizar el comportamiento de los objetos según el tipo de tiempo de ejecución del objeto.

Esas técnicas no son posibles en el caso de los datos que no están estructurados en una jerarquía de clases. Cuando los datos y los métodos están separados, se necesitan otras herramientas. Las nuevas construcciones de *coincidencia de patrones* permiten una sintaxis más limpia para examinar los datos y manipular el flujo de control basándose en cualquier condición de esos datos. Ya escribe instrucciones `if` y `switch` que comprueban el valor de una variable. Escribe instrucciones `is` que comprueban el tipo de una variable. La *coincidencia de patrones* agrega nuevas capacidades a esas instrucciones.

En este artículo se creará un método que calcula el área de distintas formas geométricas. Pero se hará sin recurrir a técnicas orientadas a objetos y sin crear una jerarquía de clases para las diferentes formas.
En lugar de esto se usará la *coincidencia de patrones*.
Conforme avance en este ejemplo, compare este código con cómo se estructuraría como una jerarquía de objetos. Cuando los datos que se deben consultar y manipular no son una jerarquía de clases, la coincidencia de patrones permite diseños elegantes.

En lugar de empezar con una definición de forma abstracta y agregar diferentes clases de formas concretas, se comenzará con simples definiciones solo de datos para cada una de las formas geométricas:

[!code-csharp[ShapeDefinitions](../../samples/csharp/PatternMatching/Shapes.cs#01_ShapeDefinitions "Shape definitions")]

A partir de estas estructuras se va a escribir un método que calcula el área de alguna forma.

## <a name="the-is-type-pattern-expression"></a>Expresión de patrón de tipo `is`

Antes de C# 7.0, había que comprobar cada tipo en una serie de instrucciones `if` e `is`:

[!code-csharp[ClassicIsExpression](../../samples/csharp/PatternMatching/GeometricUtilities.cs#02_ClassicIsExpression "Classic type pattern using is")]

El código anterior es una expresión clásica del *patrón de tipo*: se prueba una variable para determinar su tipo y se realiza una acción diferente basada en ese tipo.

Este código se simplifica con extensiones de la expresión `is` para asignar una variable si la prueba se realiza correctamente:

[!code-csharp[IsPatternExpression](../../samples/csharp/PatternMatching/GeometricUtilities.cs#03_IsPatternExpression "is pattern expression")]

En esta versión actualizada, la expresión `is` prueba la variable y la asigna a una nueva variable del tipo correcto. Observe también que esta versión incluye el tipo `Rectangle`, que es un elemento `struct`. La nueva expresión `is` funciona con tipos de valor y con tipos de referencia.

Las reglas del lenguaje para las expresiones de coincidencia de patrones ayudan a evitar el uso indebido de los resultados de una expresión de coincidencia. En el ejemplo anterior, las variables `s`, `c` y `r` solo están en el ámbito y se asignan definitivamente cuando las expresiones de coincidencia de patrones respectivas tienen resultados `true`. Si intenta usar una de las variables en otra ubicación, el código genera errores del compilador.

Vamos a examinar detenidamente esas dos reglas, a partir del ámbito. La variable `c` está en el ámbito únicamente en la rama `else` de la primera instrucción `if`. La variable `s` está en el ámbito en el método `ComputeAreaModernIs`. Eso se debe a que cada rama de una instrucción `if` establece un ámbito independiente para las variables. Pero la propia instrucción `if` no. Eso significa que las variables declaradas en la instrucción `if` están en el mismo ámbito que la instrucción `if` (el método en este caso). Este comportamiento no es específico de la coincidencia de patrones, sino que es el definido para los ámbitos de variable y las instrucciones `if` y `else`.

Las variables `c` y `s` se asignan cuando las respectivas instrucciones `if` son true debido al mecanismo when true asignado definitivamente.

> [!TIP]
> En los ejemplos de este tema se usa la construcción recomendada, donde una expresión de coincidencia de patrones `is` asigna definitivamente la variable de coincidencia en la rama `true` de la instrucción `if`.
> Se podría invertir la lógica al decir `if (!(shape is Square s))` y la variable `s` se asignaría definitivamente solo en la rama `false`. Aunque esto es C# válido, no se recomienda, porque es más confuso para seguir la lógica.

Estas reglas significan que es poco probable que se acceda accidentalmente al resultado de una expresión de coincidencia de patrones cuando no ha habido coincidencia de ese patrón.

## <a name="using-pattern-matching-switch-statements"></a>Uso de instrucciones de coincidencia de patrones `switch`

Con el tiempo, es posible que tenga que admitir otros tipos de formas. A medida que crece el número de condiciones que se está probando, puede resultar pesado el uso de expresiones de coincidencia de patrones `is`. Además de necesitar instrucciones `if` en cada tipo que se quiere comprobar, las expresiones `is` solo se pueden probar si la entrada coincide con un único tipo. En este caso, las expresiones de coincidencia de patrones `switch` son una mejor opción. 

La instrucción tradicional `switch` era una expresión de patrón: admitía el patrón de constante.
Se podía comparar una variable con cualquier constante usada en una instrucción `case`:

[!code-csharp[ClassicSwitch](../../samples/csharp/PatternMatching/GeometricUtilities.cs#04_ClassicSwitch "Classic switch statement")]

El único patrón admitido por la instrucción `switch` era el patrón de constante. Se limitaba aún más a tipos numéricos y al tipo `string`.
Esas restricciones se han eliminado y ahora se puede escribir una instrucción `switch` con el patrón de tipos:

[!code-csharp[Switch Type Pattern](../../samples/csharp/PatternMatching/GeometricUtilities.cs#05_SwitchTypePattern "Compute with `switch` expression")]

La instrucción de coincidencia de patrones `switch` usa una sintaxis familiar para los desarrolladores que han empleado la instrucción de estilo C tradicional `switch`. Cada `case` se evalúa y se ejecuta el código debajo de la condición que coincide con la variable de entrada. La ejecución de código no puede "pasar explícitamente" de una expresión case a la siguiente; la sintaxis de la instrucción `case` exige que cada `case` termine con `break`, `return` o `goto`.

> [!NOTE]
> Las instrucciones `goto` para saltar a otra etiqueta solo son válidas para el patrón de constante, la instrucción switch clásica.

Hay nuevas e importantes reglas que rigen la instrucción `switch`. Las restricciones respecto al tipo de la variable en la expresión `switch` se han eliminado.
Se puede usar cualquier tipo, como `object` en este ejemplo. Las expresiones case ya no se limitan a valores constantes. La eliminación de esa limitación significa que la reordenación de secciones `switch` puede cambiar el comportamiento de un programa.

Cuando se limitaba a valores constantes, más de una etiqueta `case` podía coincidir con el valor de la expresión `switch`. Eso sumado a la regla de que cada sección `switch` no debe pasar explícitamente a la sección siguiente, el resultado era que las secciones `switch` se podían reorganizar en cualquier orden sin afectar al comportamiento.
Ahora, con expresiones `switch` más generalizadas, el orden de cada sección importa. Las expresiones `switch` se evalúan en orden textual. La ejecución se transfiere a la primera etiqueta `switch` que coincide con la expresión `switch`.  
El caso `default` solo se ejecutará si no coincide ninguna otra etiqueta case. El caso `default` se evalúa en último lugar, independientemente de su orden textual. Si no hay ningún caso `default` y ninguna de las instrucciones `case` coincide, la ejecución continúa en la instrucción siguiente a la instrucción `switch`. No se ejecuta el código de ninguna de las etiquetas `case`.

## <a name="when-clauses-in-case-expressions"></a>Cláusulas `when` en expresiones `case`

Puede crear casos especiales para las formas que tengan área 0 mediante una cláusula `when` en la etiqueta `case`. Un cuadrado con una longitud de lado de 0 o un círculo con un radio de 0 tiene un área 0. Esa condición se especifica mediante una cláusula `when` en la etiqueta `case`:  

[!code-csharp[ComputeDegenerateShapes](../../samples/csharp/PatternMatching/GeometricUtilities.cs#07_ComputeDegenerateShapes "Compute shapes with 0 area")]

Este cambio muestra algunos puntos importantes sobre la nueva sintaxis. En primer lugar, se pueden aplicar varias etiquetas `case` a una sección `switch`. El bloque de instrucciones se ejecuta cuando cualquiera de esas etiquetas es `true`. En esta instancia, si la expresión `switch` es un círculo o un cuadrado con área 0, el método devuelve la constante 0.

Este ejemplo presenta dos variables distintas en las dos etiquetas `case` del primer bloque `switch`. Observe que las instrucciones de este bloque `switch` no usan las variables `c` (para el círculo) ni `s` (para el cuadrado).
Ninguna de esas variables se ha asignado definitivamente en este bloque `switch`.
Si alguno de estos casos coincide, claramente se ha asignado una de las variables.
Pero no es posible saber *cuál* se ha asignado en tiempo de compilación, ya que cualquiera de los casos podría coincidir en tiempo de ejecución. Por ese motivo, la mayoría de las veces en que se usan varias etiquetas `case` para el mismo bloque, no se presenta una nueva variable en la instrucción `case` o solo se usará la variable en la cláusula `when`.

Una vez agregadas esas formas con área 0, se van a agregar un par de tipos de formas más: un rectángulo y un triángulo:

[!code-csharp[AddRectangleAndTriangle](../../samples/csharp/PatternMatching/GeometricUtilities.cs#09_AddRectangleAndTriangle "Add rectangle and triangle")]

 Este conjunto de cambios agrega etiquetas `case` para el caso degenerado y etiquetas y bloques para cada una de las nuevas formas. 

Por último, puede agregar un caso `null` para garantizar que el argumento no sea `null`:

[!code-csharp[NullCase](../../samples/csharp/PatternMatching/GeometricUtilities.cs#10_NullCase "Add null case")]

El comportamiento especial del patrón `null` es interesante porque la constante `null` del patrón no tiene un tipo, pero se puede convertir a cualquier tipo de referencia o tipo que acepte valores NULL. En lugar de convertir `null` en cualquier tipo, el lenguaje define que un valor `null` no coincidirá con ningún patrón de tipo, independientemente del tipo de tiempo de compilación de la variable. Este comportamiento hace que el nuevo patrón de tipo basado en `switch` sea coherente con la instrucción `is`: las instrucciones `is` siempre devuelven `false` cuando el valor que se está comprobando es `null`. También es más sencillo: una vez que haya comprobado el tipo, no necesita una comprobación de NULL adicional. Puede comprobar esto en que no existen comprobaciones de NULL en ninguno de los bloques de casos de los ejemplos anteriores: no son necesarias, ya que la coincidencia del patrón de tipo garantiza un valor distinto de NULL.

## <a name="var-declarations-in-case-expressions"></a>Declaraciones `var` en expresiones `case`

La introducción de `var` como una de las expresiones de coincidencia presenta nuevas reglas para la coincidencias de patrones.

La primera regla es que la declaración `var` sigue las reglas de inferencia de tipo normal: El tipo se infiere para que sea el tipo estático de la expresión switch. De esa regla, el tipo siempre coincide.

La segunda regla es que una declaración `var` no tiene la comprobación de valores NULL que incluyen otras expresiones de patrón de tipo. Esto significa que la variable puede ser NULL y se necesita una comprobación de valores NULL en ese caso.

Esas dos reglas implican que, en muchos casos, una declaración `var` en una expresión `case` coincide con las mismas condiciones que una expresión `default`.
Dado que se prefiere cualquier caso que no sea default al caso `default`, el caso `default` nunca se ejecutará.

> [!NOTE]
> El compilador no emite una advertencia en esos casos en que se ha escrito un caso `default` pero nunca se ejecutará. Esto es coherente con el comportamiento actual de la instrucción `switch` donde se han enumerado todos los casos posibles.

La tercera regla presenta usos donde un caso `var` puede resultar útil. Imagine que va a realizar una coincidencia de patrones donde la entrada es una cadena y busca valores de comando conocidos. Podría escribir algo parecido a esto:

[!code-csharp[VarCaseExpression](../../samples/csharp/PatternMatching/Program.cs#VarCaseExpression "use a var case expression to filter white space")]

El caso `var` coincide con `null`, la cadena vacía, o cualquier cadena que contenga solo espacios en blanco. Tenga en cuenta que el código anterior usa el operador `?.` para asegurarse de que no genera por accidente una <xref:System.NullReferenceException>. El caso `default` controla cualquier otro valor de cadena que no entienda este analizador de comandos.

Este es un ejemplo en que puede que quiera considerar el uso de una expresión de caso `var` que sea distinta de una expresión `default`.

## <a name="conclusions"></a>Conclusiones

Las *construcciones de coincidencia de patrones* permiten administrar fácilmente el flujo de control entre distintas variables y tipos que no están relacionados mediante una jerarquía de herencia. También se puede controlar la lógica para usar cualquier condición que se pruebe en la variable. Permite patrones y expresiones que se van a necesitar más a menudo a medida que se crean aplicaciones más distribuidas, donde los datos y los métodos que los manipulan están separados. Observará que las estructuras de forma usadas en este ejemplo no contienen métodos, solo propiedades de solo lectura.
La coincidencia de patrones funciona con cualquier tipo de datos. Se escriben expresiones que examinan el objeto y se toman decisiones de flujo de control basadas en esas condiciones.

Compare el código de este ejemplo con el diseño que se obtendría al crear una jerarquía de clases para un elemento `Shape` abstracto y formas derivadas concretas cada una con su propia implementación de un método virtual para calcular el área. A menudo encontrará que las expresiones de coincidencia de patrones pueden ser una herramienta muy útil al trabajar con datos y querer separar las preocupaciones sobre almacenamiento de datos de las preocupaciones sobre comportamiento.

## <a name="see-also"></a>Vea también

- [Tutorial: Uso de las características de coincidencia de patrones para ampliar los tipos de datos](tutorials/pattern-matching.md)
