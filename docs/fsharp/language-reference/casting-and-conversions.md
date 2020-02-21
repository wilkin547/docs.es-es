---
title: Conversiones
description: Obtenga información sobre F# cómo el lenguaje de programación proporciona operadores de conversión para las conversiones aritméticas entre varios tipos primitivos.
ms.date: 02/20/2020
ms.openlocfilehash: 5f9727d14a7ae070e0f0f71fa0a0abe04f662071
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543591"
---
# <a name="casting-and-conversions-f"></a>Conversiones (F#)

En este tema se describe la compatibilidad con las conversiones de tipos en F#.

## <a name="arithmetic-types"></a>Tipos aritméticos

F#proporciona operadores de conversión para las conversiones aritméticas entre varios tipos primitivos, como entre tipos de punto flotante y enteros. Los operadores de conversión integral y char tienen formularios comprobados y no comprobados; los operadores de punto flotante y el operador de conversión `enum` no. Los formularios no comprobados se definen en `Microsoft.FSharp.Core.Operators` y los formularios marcados se definen en `Microsoft.FSharp.Core.Operators.Checked`. Los formularios comprobados comprueban si hay desbordamiento y generan una excepción en tiempo de ejecución si el valor resultante supera los límites del tipo de destino.

Cada uno de estos operadores tiene el mismo nombre que el nombre del tipo de destino. Por ejemplo, en el código siguiente, en el que los tipos se anotan explícitamente, `byte` aparece con dos significados diferentes. La primera aparición es el tipo y el segundo es el operador de conversión.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

En la tabla siguiente se muestran los operadores F#de conversión definidos en.

|Operator|Descripción|
|--------|-----------|
|`byte`|Convertir en byte, un tipo sin signo de 8 bits.|
|`sbyte`|Convertir en bytes con signo.|
|`int16`|Convertir en un entero de 16 bits con signo.|
|`uint16`|Convertir en un entero de 16 bits sin signo.|
|`int32, int`|Convertir en un entero de 32 bits con signo.|
|`uint32`|Convertir en un entero de 32 bits sin signo.|
|`int64`|Convertir en un entero de 64 bits con signo.|
|`uint64`|Convertir en un entero de 64 bits sin signo.|
|`nativeint`|Convertir en un entero nativo.|
|`unativeint`|Convertir en un entero nativo sin signo.|
|`float, double`|Convertir en un número de punto flotante de IEEE de doble precisión de 64 bits.|
|`float32, single`|Convertir en un número de punto flotante de IEEE de precisión sencilla de 32 bits.|
|`decimal`|Convertir en `System.Decimal`.|
|`char`|Convertir en `System.Char`, un carácter Unicode.|
|`enum`|Convertir en un tipo enumerado.|

Además de los tipos primitivos integrados, puede usar estos operadores con tipos que implementan `op_Explicit` o `op_Implicit` métodos con las firmas adecuadas. Por ejemplo, el operador de conversión `int` funciona con cualquier tipo que proporcione un método estático `op_Explicit` que toma el tipo como parámetro y devuelve `int`. Como excepción especial a la regla general de que los métodos no se pueden sobrecargar por tipo de valor devuelto, puede hacerlo para `op_Explicit` y `op_Implicit`.

## <a name="enumerated-types"></a>Tipos enumerados

El operador `enum` es un operador genérico que toma un parámetro de tipo que representa el tipo del `enum` al que se va a convertir. Cuando se convierte a un tipo enumerado, la inferencia de tipos intenta determinar el tipo de `enum` al que se desea convertir. En el ejemplo siguiente, la variable `col1` no se anota explícitamente, pero su tipo se deduce de la prueba de igualdad posterior. Por consiguiente, el compilador puede deducir que se está convirtiendo en una enumeración `Color`. Como alternativa, puede proporcionar una anotación de tipo, como con `col2` en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

También puede especificar explícitamente el tipo de enumeración de destino como un parámetro de tipo, como en el código siguiente:

```fsharp
let col3 = enum<Color> 3
```

Tenga en cuenta que las conversiones de enumeración funcionan solo si el tipo subyacente de la enumeración es compatible con el tipo que se va a convertir. En el código siguiente, la conversión no se compila debido a la falta de coincidencia entre `int32` y `uint32`.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

Para obtener más información, vea [enumeraciones](enumerations.md).

## <a name="casting-object-types"></a>Convertir tipos de objeto

La conversión entre tipos en una jerarquía de objetos es fundamental para la programación orientada a objetos. Hay dos tipos básicos de conversiones: conversión hacia arriba (conversión) y conversión hacia abajo (downcasting). La conversión de una jerarquía significa la conversión de una referencia de objeto derivada a una referencia de objeto base. Se garantiza que este tipo de conversión funciona siempre y cuando la clase base se encuentra en la jerarquía de herencia de la clase derivada. La conversión de una jerarquía de una referencia de objeto base a una referencia de objeto derivada solo se realiza correctamente si el objeto es realmente una instancia del tipo de destino (derivado) correcto o un tipo derivado del tipo de destino.

F#proporciona operadores para estos tipos de conversiones. El operador `:>` convierte hacia arriba la jerarquía y el operador `:?>` convierte en la jerarquía.

### <a name="upcasting"></a>Convertir

En muchos lenguajes orientados a objetos, la conversión cruzada es implícita; en F#, las reglas son ligeramente diferentes. La conversión se aplica automáticamente cuando se pasan argumentos a métodos en un tipo de objeto. Sin embargo, en el caso de las funciones enlazadas a un módulo, la conversión cruzada no es automática, a menos que el tipo de parámetro se declare como un tipo flexible. Para obtener más información, vea [tipos flexibles](flexible-Types.md).

El operador `:>` realiza una conversión estática, lo que significa que el éxito de la conversión se determina en tiempo de compilación. Si una conversión que usa `:>` se compila correctamente, es una conversión válida y no tiene posibilidad de errores en tiempo de ejecución.

También puede usar el operador `upcast` para realizar esta conversión. La expresión siguiente especifica una conversión hacia arriba en la jerarquía:

```fsharp
upcast expression
```

Cuando se usa el operador de conversión, el compilador intenta deducir el tipo al que se va a convertir desde el contexto. Si el compilador no puede determinar el tipo de destino, el compilador informa de un error. Es posible que se requiera una anotación de tipo.

### <a name="downcasting"></a>Downcasting

El operador `:?>` realiza una conversión dinámica, lo que significa que el éxito de la conversión se determina en tiempo de ejecución. Una conversión que usa el operador `:?>` no se comprueba en tiempo de compilación; pero en tiempo de ejecución, se realiza un intento de conversión al tipo especificado. Si el objeto es compatible con el tipo de destino, la conversión se realiza correctamente. Si el objeto no es compatible con el tipo de destino, el motor en tiempo de ejecución genera un `InvalidCastException`.

También puede usar el operador `downcast` para realizar una conversión de tipos dinámica. La expresión siguiente especifica una conversión hacia abajo en la jerarquía hasta un tipo que se deduce del contexto del programa:

```fsharp
downcast expression
```

Como en el caso del operador `upcast`, si el compilador no puede inferir un tipo de destino específico del contexto, notifica un error. Es posible que se requiera una anotación de tipo.

En el código siguiente se muestra el uso de los operadores `:>` y `:?>`. El código muestra que el operador de `:?>` se utiliza mejor cuando sabe que la conversión se realizará correctamente, ya que produce `InvalidCastException` si se produce un error en la conversión. Si no sabe que una conversión se realizará correctamente, una prueba de tipo que use una expresión `match` es mejor porque evita la sobrecarga de generar una excepción.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

Dado que los operadores genéricos `downcast` y `upcast` dependen de la inferencia de tipos para determinar el argumento y el tipo de valor devuelto, en el código anterior, puede reemplazar

```fsharp
let base1 = d1 :> Base1
```

con

```fsharp
let base1: Base1 = upcast d1
```

Tenga en cuenta que se requiere una anotación de tipo, ya que `upcast` por sí misma no pudo determinar la clase base.

## <a name="see-also"></a>Consulte también

- [Referencia del lenguaje F#](index.md)
