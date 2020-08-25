---
title: Unidades de medida
description: 'Obtenga información sobre cómo los valores de punto flotante y entero con signo en F # pueden tener asociadas unidades de medida, que se suelen usar para indicar la longitud, el volumen y la masa.'
ms.date: 08/15/2020
ms.openlocfilehash: 0262f89e80697dd86161c93fe37381122972b56f
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811579"
---
# <a name="units-of-measure"></a>Unidades de medida

Los valores de punto flotante y entero con signo en F # pueden tener asociadas unidades de medida, que se suelen usar para indicar la longitud, el volumen, la masa, etc. Mediante el uso de cantidades con unidades, se habilita el compilador para comprobar que las relaciones aritméticas tienen las unidades correctas, lo que ayuda a evitar errores de programación.

## <a name="syntax"></a>Sintaxis

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Comentarios

La sintaxis anterior define el *nombre de unidad* como unidad de medida. El elemento opcional se utiliza para definir una nueva medida en términos de unidades definidas previamente. Por ejemplo, la línea siguiente define la medida `cm` (centímetro).

```fsharp
[<Measure>] type cm
```

En la línea siguiente se define la medida `ml` (milliliter) como un centímetro cúbico ( `cm^3` ).

```fsharp
[<Measure>] type ml = cm^3
```

En la sintaxis anterior, *Measure* es una fórmula que implica unidades. En las fórmulas que implican unidades, se admiten las potencias enteras (positivas y negativas), los espacios entre las unidades indican un producto de las dos unidades, `*` también indica un producto de unidades e `/` indica un cociente de unidades. En el caso de una unidad recíproca, puede usar una potencia entera negativa o una `/` que indique una separación entre el numerador y el denominador de una fórmula de unidad. Varias unidades del denominador deben ir entre paréntesis. Las unidades separadas por espacios después de un `/` se interpretan como parte del denominador, pero las unidades que siguen a un `*` se interpretan como parte del numerador.

Puede usar 1 en expresiones unitarias, ya sea solo para indicar una cantidad sin dimensiones, o junto con otras unidades, como en el numerador. Por ejemplo, las unidades de una tasa se escribirían como `1/s` , donde `s` indica segundos. No se usan paréntesis en las fórmulas unitarias. No se especifican constantes de conversión numéricas en las fórmulas unitarias; sin embargo, puede definir constantes de conversión con unidades por separado y usarlas en cálculos con comprobación unitaria.

Las fórmulas de unidad que significan lo mismo pueden escribirse de varias formas equivalentes. Por lo tanto, el compilador convierte las fórmulas unitarias en un formato coherente, que convierte las potencias negativas en recíprocos, agrupa las unidades en un solo numerador y un denominador, y alphabetizes las unidades en el numerador y el denominador.

Por ejemplo, las fórmulas de unidad `kg m s^-2` y `m /s s * kg` se convierten en `kg m/s^2` .

En las expresiones de punto flotante se usan unidades de medida. El uso de números de punto flotante junto con unidades de medida asociadas agrega otro nivel de seguridad de tipos y ayuda a evitar los errores de no coincidencia de unidad que se pueden producir en las fórmulas cuando se utilizan números de punto flotante débilmente tipados. Si escribe una expresión de punto flotante que utiliza unidades, las unidades de la expresión deben coincidir.

Puede anotar literales con una fórmula de unidad entre corchetes angulares, tal como se muestra en los ejemplos siguientes.

```fsharp
1.0<cm>
55.0<miles/hour>
```

No se coloca un espacio entre el número y el corchete angular; sin embargo, puede incluir un sufijo literal como `f` , como en el ejemplo siguiente.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Esta anotación cambia el tipo del literal de su tipo primitivo (como `float` ) a un tipo de dimensión, como `float<cm>` o, en este caso, `float<miles/hour>` . Una anotación de unidad de `<1>` indica una cantidad sin dimensiones y su tipo es equivalente al tipo primitivo sin un parámetro de unidad.

El tipo de una unidad de medida es un tipo de punto flotante o entero con signo junto con una anotación de unidad adicional, indicado entre corchetes. Por lo tanto, al escribir el tipo de una conversión de `g` (gramos) a `kg` (kilogramos), se describen los tipos de la siguiente manera.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Las unidades de medida se utilizan para la comprobación unitaria en tiempo de compilación pero no se conservan en el entorno en tiempo de ejecución. Por lo tanto, no afectan al rendimiento.

Las unidades de medida se pueden aplicar a cualquier tipo, no solo a los tipos de punto flotante; sin embargo, solo los tipos de punto flotante, los tipos enteros con signo y los tipos decimales admiten cantidades dimensionales. Por lo tanto, solo tiene sentido utilizar unidades de medida en los tipos primitivos y en los agregados que contienen estos tipos primitivos.

En el ejemplo siguiente se muestra el uso de unidades de medida.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

En el ejemplo de código siguiente se muestra cómo convertir un número de punto flotante no dimensional en un valor de punto flotante de dimensión. Solo tiene que multiplicar por 1,0 y aplicar las dimensiones a 1,0. Puede abstraerlo en una función como `degreesFahrenheit` .

Además, cuando pase valores con dimensiones a funciones que esperan números de punto flotante sin dimensiones, debe cancelar las unidades o convertirlos en `float` mediante el `float` operador. En este ejemplo, se divide por `1.0<degC>` para los argumentos en `printf` porque `printf` espera cantidades no dimensionales.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

En la sesión de ejemplo siguiente se muestran los resultados de las entradas y en este código.

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Uso de unidades genéricas

Puede escribir funciones genéricas que operan en datos que tienen una unidad de medida asociada. Para ello, especifique un tipo junto con una unidad genérica como parámetro de tipo, tal y como se muestra en el ejemplo de código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a>Crear tipos de agregado con unidades genéricas

En el código siguiente se muestra cómo crear un tipo de agregado que consta de valores de punto flotante individuales que tienen unidades que son genéricas. Esto permite crear un único tipo que funciona con una variedad de unidades. Además, las unidades genéricas conservan la seguridad de tipos asegurándose de que un tipo genérico que tiene un conjunto de unidades es un tipo diferente del mismo tipo genérico con un conjunto de unidades diferente. La base de esta técnica es que el `Measure` atributo se puede aplicar al parámetro de tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a>Unidades en tiempo de ejecución

Las unidades de medida se utilizan para la comprobación de tipos estáticos. Cuando se compilan los valores de punto flotante, se eliminan las unidades de medida, por lo que las unidades se pierden en tiempo de ejecución. Por lo tanto, no es posible cualquier intento de implementar la funcionalidad que depende de la comprobación de las unidades en tiempo de ejecución. Por ejemplo, `ToString` no es posible implementar una función para imprimir las unidades.

## <a name="conversions"></a>Conversiones

Para convertir un tipo que tiene unidades (por ejemplo, `float<'u>` ) en un tipo que no tiene unidades, puede usar la función de conversión estándar. Por ejemplo, puede usar `float` para convertir en un `float` valor que no tiene unidades, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Para convertir un valor sin unidades en un valor que tiene unidades, puede multiplicar por un valor 1 o 1,0 anotado con las unidades adecuadas. Sin embargo, para escribir capas de interoperabilidad, también hay algunas funciones explícitas que puede usar para convertir valores sin unidades en valores con unidades. Se encuentran en el módulo [FSharp. Core. LanguagePrimitives](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) . Por ejemplo, para convertir de una unidad `float` a una `float<cm>` , use [floatwithmeasure (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure), tal y como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a>Unidades de medida en la biblioteca básica de F #

Una biblioteca de unidades está disponible en el `FSharp.Data.UnitSystems.SI` espacio de nombres. Incluye las unidades SI en su forma de símbolo (como `m` para el medidor) en el `UnitSymbols` subespacio de nombres y su nombre completo (como `meter` para el medidor) en el `UnitNames` subespacio de nombres.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
