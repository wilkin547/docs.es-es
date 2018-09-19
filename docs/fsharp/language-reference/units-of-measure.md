---
title: Unidades de medida (F#)
description: 'Obtenga información de punto flotante cómo y valores enteros con signo en F # pueden tener asociados a las unidades de medida, que normalmente se utilizan para indicar la longitud, el volumen y masivo.'
ms.date: 05/16/2016
ms.openlocfilehash: ad2193e25f3c0cee6e73cd529ab43d1e4b6b549b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45972522"
---
# <a name="units-of-measure"></a>Unidades de medida

Punto flotante y los valores enteros con signo en F # puede tener asociadas unidades de medida, que normalmente se utilizan para indicar la longitud, el volumen, masa, y así sucesivamente. Mediante el uso de las cantidades con unidades, permitir que el compilador comprobar que las relaciones aritméticas tienen las unidades correctas, que ayuda a evitar errores de programación.

## <a name="syntax"></a>Sintaxis

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Comentarios

Define la sintaxis anterior *nombre de la unidad* como una unidad de medida. La parte opcional se utiliza para definir una nueva medida en términos de unidades definidas previamente. Por ejemplo, la línea siguiente define la medida `cm` (centímetro).

```fsharp
[<Measure>] type cm
```

La línea siguiente define la medida `ml` (mililitro) como un centímetro cúbico (`cm^3`).

```fsharp
[<Measure>] type ml = cm^3
```

En la sintaxis anterior, *medida* es una fórmula que implica unidades. En las fórmulas que impliquen unidades, se admiten potencias enteras (positivas y negativas), espacios entre unidades indican un producto de las dos unidades, `*` también indica un producto de unidades, y `/` indica un cociente de unidades. Para una unidad recíproca, puede usar una potencia de entero negativo o un `/` que indica una separación entre el numerador y denominador de una fórmula de la unidad. Varias unidades en el denominador deben estar entre paréntesis. Unidades separan por espacios después de un `/` se interpretan como parte del denominador, pero las unidades después un `*` se interpretan como parte del numerador.

Puede usar 1 en las expresiones de unidad, ya sea por sí solo para indicar una cantidad sin dimensiones, o junto con otras unidades, como se muestra en el numerador. Por ejemplo, las unidades para un índice se escribiría como `1/s`, donde `s` indica los segundos. No se emplean paréntesis en las fórmulas de la unidad. No se especifica las constantes de conversión numérica en las fórmulas de la unidad; Sin embargo, puede definir constantes de conversión con unidades por separado y utilizarlos en cálculos con comprobación de unidad.

Las fórmulas de la unidad que significan lo mismo pueden escribirse de diferentes formas equivalentes. Por lo tanto, el compilador convierte las fórmulas de la unidad en un formato coherente, lo que convierte potencias negativas recíprocos, unidades de grupos en un solo numerador y denominador y se ordenan alfabéticamente las unidades en el numerador y denominador.

Por ejemplo, las fórmulas de unidades `kg m s^-2` y `m /s s * kg` se convierten en `kg m/s^2`.

Utilice las unidades de medida en expresiones de punto flotante. El uso de números de punto flotante junto con los asociados unidades de medida agrega otro nivel de seguridad de tipos y ayuda a evitar los errores de coincidencia de unidad que se pueden producir en las fórmulas cuando usas débilmente tipada números de punto flotante. Si escribe un flotante expresión de punto que usa unidades, las unidades en la expresión deben coincidir.

Puede anotar literales con una fórmula de la unidad en corchetes angulares, como se muestra en los ejemplos siguientes.

```fsharp
1.0<cm>
55.0<miles/hour>
```

No colocar un espacio entre el número y el corchete angular; Sin embargo, puede incluir un sufijo literal como `f`, como en el ejemplo siguiente.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Este tipo de anotación cambia el tipo del literal desde su tipo primitivo (como `float`) a un tipo con dimensiones, como `float<cm>` o, en este caso, `float<miles/hour>`. La anotación de una unidad `<1>` indica una cantidad sin dimensiones y su tipo es equivalente al tipo primitivo sin un parámetro de la unidad.

El tipo de una unidad de medida es un punto flotante o un tipo entero junto con una anotación de unidad adicional, indicado entre corchetes con signo. Por lo tanto, al escribir el tipo de conversión de `g` (gramos) a `kg` (kg), se describen los tipos como sigue.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Las unidades de medida se usan para la comprobación de unidades en tiempo de compilación, pero no se conservan en el entorno de tiempo de ejecución. Por lo tanto, no afectan al rendimiento.

Las unidades de medida se pueden aplicar a cualquier tipo, no solo los tipos de punto; de flotante Sin embargo, solo los tipos de punto flotante, firma tipos enteros y tipos decimales admiten cantidades con dimensiones. Por lo tanto, solo tiene sentido utilizar unidades de medida en los tipos primitivos y los agregados que contienen estos tipos primitivos.

El ejemplo siguiente muestra el uso de unidades de medida.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

El ejemplo de código siguiente muestra cómo convertir de un número de punto flotante sin dimensiones en un valor de punto flotante con dimensiones. Solo multiplique por 1,0, aplicando las dimensiones para la versión 1.0. Esto se puede abstraer en una función como `degreesFahrenheit`.

Además, al pasar valores con dimensiones a funciones que esperan números de punto flotante sin dimensiones, debe anular las unidades o convertir `float` utilizando el `float` operador. En este ejemplo, se divide por `1.0<degC>` para los argumentos de `printf` porque `printf` espera cantidades sin dimensiones.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

La sesión de ejemplo siguiente muestra las entradas y salidas de este código.

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Usar unidades genéricas

Puede escribir funciones genéricas que funcionan con datos que tienen una unidad de medida asociada. Para ello, especifica un tipo junto con una unidad genérico como un parámetro de tipo, como se muestra en el siguiente ejemplo de código.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a>Crear tipos agregados con unidades genéricas

El código siguiente muestra cómo crear un tipo agregado que consta de los valores de punto flotante individuales que tienen unidades que son genéricas. Esto permite que un solo tipo crearse que funciona con una variedad de unidades. También, unidades genéricas conservan la seguridad de tipos asegurándose de que un tipo genérico que tiene un conjunto de unidades es un tipo diferente que el mismo tipo genérico con un conjunto diferente de unidades. La base de esta técnica es que la `Measure` atributo puede aplicarse al parámetro de tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a>Unidades en tiempo de ejecución

Las unidades de medida se usan para la comprobación de tipos estáticos. Cuando se compilan los valores de punto flotante, se eliminan las unidades de medida, por lo que se pierden las unidades de tiempo de ejecución. Por lo tanto, cualquier intento de implementar la funcionalidad que depende de las unidades de la comprobación en tiempo de ejecución no es posible. Por ejemplo, implementar un `ToString` función para imprimir las unidades no es posible.

## <a name="conversions"></a>Conversiones

Para convertir un tipo que tiene unidades (por ejemplo, `float<'u>`) a un tipo que no tenga unidades, puede usar la función de conversión estándar. Por ejemplo, puede usar `float` para convertir en un `float` valor que no tenga unidades, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Para convertir un valor sin unidades en un valor que tiene unidades, puede multiplicar por un valor de 1 ó 1.0 que se anota con las unidades adecuadas. Sin embargo, para escribir los niveles de interoperabilidad, también hay algunas funciones explícitas que puede usar para convertir valores sin unidades en valores con unidades. Estos son en el [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) módulo. Por ejemplo, para convertir de un sin unidades `float` a un `float<cm>`, utilice [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), tal y como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a>Unidades de medida en la biblioteca básica de F #

Una biblioteca de la unidad está disponible en el `FSharp.Data.UnitSystems.SI` espacio de nombres. Incluye las unidades en su forma de símbolos de ambos (como `m` medidor) en el `UnitSymbols` subespacio de nombres y su nombre completo (como `meter` medidor) en el `UnitNames` subespacio de nombres.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
