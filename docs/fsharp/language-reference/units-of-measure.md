---
title: Unidades de medida (F#)
description: 'Obtenga información acerca de punto flotante cómo y valores enteros con signo en F # pueden tener asociadas unidades de medida, que se usan normalmente para indicar la longitud, el volumen y masa.'
ms.date: 05/16/2016
ms.openlocfilehash: 3e47c92100c1dd99161be709a065913f501854f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="units-of-measure"></a>Unidades de medida

Punto flotante y valores enteros con signo en F # puede tener asociadas unidades de medida, que se usan normalmente para indicar la longitud, el volumen, masa, y así sucesivamente. Al usar cantidades con unidades, se habilita al compilador comprobar que las relaciones aritméticas tienen las unidades correctas, lo que ayuda a evitar errores de programación.


## <a name="syntax"></a>Sintaxis

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Comentarios
Define la sintaxis anterior *nombre de la unidad* como una unidad de medida. La parte opcional se utiliza para definir una nueva medida en términos de unidades definidos previamente. Por ejemplo, la línea siguiente define la medida `cm` (cm).

```fsharp
[<Measure>] type cm
```

La línea siguiente define la medida `ml` (mililitro) un como centímetro cúbico (`cm^3`).

```fsharp
[<Measure>] type ml = cm^3
```

En la sintaxis anterior, *medida* es una fórmula que implica unidades. En las fórmulas que requieren unidades, se admiten potencias enteras (positivas y negativas), espacios entre unidades indican un producto de las dos unidades, `*` también indica un producto de unidades, y `/` indica un cociente de unidades. Para una unidad recíproca, puede usar una potencia de entero negativo o una `/` que indica una separación entre el numerador y el denominador de una fórmula de la unidad. Varias unidades en el denominador deben ir entre paréntesis. Unidades separan por espacios después de un `/` se interpretan como parte del denominador, pero las unidades después de un `*` se interpretan como parte del numerador.

Puede usar 1 en las expresiones de unidad, ya sea por sí solo para indicar una cantidad sin dimensiones, o junto con otras unidades, como se muestra en el numerador. Por ejemplo, las unidades para una velocidad se escribiría como `1/s`, donde `s` indica los segundos. No se emplean paréntesis en las fórmulas de la unidad. No especificar constantes de conversión numérica en las fórmulas de unidades; Sin embargo, puede definir constantes de conversión con unidades por separado y utilizarlos en cálculos con comprobación de unidad.

Fórmulas de unidades que significan lo mismo pueden escribirse de diferentes formas equivalentes. Por lo tanto, el compilador convierte fórmulas de unidades en un formato coherente, que convierte potencias negativas recíprocos, unidades se agrupan en un solo numerador y denominador y se ordenan alfabéticamente las unidades en el numerador y el denominador.

Por ejemplo, las fórmulas de unidades `kg m s^-2` y `m /s s * kg` se convierten en `kg m/s^2`.

Usar unidades de medida en expresiones de punto flotante. Uso de números de punto flotante junto con asociados unidades de medida agrega otro nivel de seguridad de tipos y ayuda a evita los errores de falta de coincidencia de unidad que se pueden producir en las fórmulas cuando se utiliza con tipos débiles números de punto flotante. Si escribe un flotante expresión de punto que utiliza unidades, las unidades en la expresión deben coincidir.

Puede anotar literales con una fórmula de unidad en corchetes angulares, tal como se muestra en los ejemplos siguientes.

```fsharp
1.0<cm>
55.0<miles/hour>
```

No incluir un espacio entre el número y el corchete angular de cierre; Sin embargo, puede incluir un sufijo literal como `f`, como en el ejemplo siguiente.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Este tipo de anotación cambia el tipo del literal desde su tipo primitivo (como `float`) a un tipo con dimensiones, como `float<cm>` o, en este caso, `float<miles/hour>`. La anotación de unidad `<1>` indica una cantidad sin dimensiones y su tipo es equivalente al tipo primitivo sin un parámetro de unidad.

El tipo de una unidad de medida es un punto flotante o tipo entero con signo junto con una anotación de unidad adicional, indicada entre paréntesis. Por lo tanto, al escribir el tipo de conversión de `g` (g) a `kg` (kilogramos), se describen los tipos como sigue.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Unidades de medida que se usan para la comprobación de unidades en tiempo de compilación pero no se conservan en el entorno de tiempo de ejecución. Por lo tanto, no afectan al rendimiento.

Unidades de medida se pueden aplicar a cualquier tipo, no solo los tipos de punto; flotante Sin embargo, solo los tipos de punto flotante, firma tipos enteros y tipos decimales admiten cantidades con dimensiones. Por lo tanto, solo tiene sentido utilizar unidades de medida en los tipos primitivos y los agregados que contengan estos tipos primitivos.

En el ejemplo siguiente se muestra el uso de unidades de medida.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
En el ejemplo de código siguiente se muestra cómo convertir un número de punto flotante sin dimensiones en un valor de punto flotante con dimensiones. Solo multiplique por 1,0, aplicar las dimensiones a la versión 1.0. Esto se puede abstraer en una función como `degreesFahrenheit`.

Además, al pasar valores con dimensiones a funciones que esperan números de punto flotante sin dimensiones, debe anular las unidades o convertir a `float` utilizando el `float` operador. En este ejemplo, se divide por `1.0<degC>` para los argumentos con `printf` porque `printf` espera cantidades sin dimensiones.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

La sesión de ejemplo siguiente muestra las entradas y salidas de a este código.

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Usar unidades genéricas
Puede escribir funciones genéricas que funcionan con datos que tienen una unidad de medida asociada. Para ello, especificando un tipo junto con una unidad genérica como un parámetro de tipo, como se muestra en el ejemplo de código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a>Crear tipos agregados con unidades genéricas
El código siguiente muestra cómo crear un tipo agregado que consta de valores de punto flotante individuales que tienen unidades que son genéricas. Esto permite que un tipo único al crearse que funciona con una variedad de unidades. Además, unidades genéricas conservan la seguridad de tipos al garantizar que un tipo genérico que tiene un conjunto de unidades es un tipo diferente que el mismo tipo genérico con un conjunto diferente de unidades. La base de esta técnica es que la `Measure` atributo se puede aplicar al parámetro de tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a>Unidades en tiempo de ejecución
Unidades de medida se utilizan para la comprobación de tipos estáticos. Cuando se compilan los valores de punto flotante, se eliminan las unidades de medida, por lo que las unidades se pierden en tiempo de ejecución. Por lo tanto, cualquier intento de implementar la funcionalidad que depende de la comprobación de las unidades en tiempo de ejecución no es posible. Por ejemplo, implementar un `ToString` función para imprimir las unidades no es posible.


## <a name="conversions"></a>Conversiones
Para convertir un tipo que tiene unidades (por ejemplo, `float<'u>`) a un tipo que no tiene unidades, puede utilizar la función de conversión estándar. Por ejemplo, puede usar `float` para convertir en un `float` valor que no tiene unidades, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Para convertir un valor sin unidades en un valor que contiene unidades, puede multiplicar por un valor de 1 ó 1,0 que se anota con las unidades correspondientes. Sin embargo, para escribir niveles de interoperabilidad, también hay algunas funciones explícitas que puede utilizar para convertir los valores sin unidades en valores con unidades. Se trata de la [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) módulo. Por ejemplo, para convertir de una sin unidades `float` a una `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), tal y como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a>Unidades de medida en el módulo de F # Power
Una biblioteca de unidades está disponible en F # PowerPack. La biblioteca de unidad incluye las unidades y constantes físicas.


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)
