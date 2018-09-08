---
title: Conversiones (F#)
description: 'Obtenga información sobre cómo el lenguaje de programación F # proporciona operadores de conversión para las conversiones aritméticas entre los distintos tipos primitivos.'
ms.date: 05/16/2016
ms.openlocfilehash: aca1a2523130ee485a7e7c9a6a45a410904cb246
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44188493"
---
# <a name="casting-and-conversions-f"></a>Conversiones (F#)

Este tema describe la compatibilidad con las conversiones de tipos en F #.

## <a name="arithmetic-types"></a>Tipos aritméticos

F # proporciona operadores de conversión para las conversiones aritméticas entre los distintos tipos primitivos, como entre valores enteros y tipos de punto flotante. Han comprobado los operadores de conversión de enteros y char y formularios desactivadas; los operadores de tipo flotante y el `enum` no lo hace el operador de conversión. Los formularios unchecked se definen en `Microsoft.FSharp.Core.Operators` y se definen las formas comprobadas en `Microsoft.FSharp.Core.Operators.Checked`. Los formularios activados comprobación el desbordamiento y generan una excepción en tiempo de ejecución si el valor resultante supera los límites del tipo de destino.

Cada uno de estos operadores tiene el mismo nombre que el nombre del tipo de destino. Por ejemplo, en el código siguiente, en el que los tipos se anotan explícitamente, `byte` aparece con dos significados diferentes. La primera aparición es el tipo y el segundo es el operador de conversión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

La siguiente tabla muestra los operadores de conversión definidos en F #.

|Operador|Descripción|
|--------|-----------|
|`byte`|Convertir en byte, un tipo sin signo de 8 bits.|
|`sbyte`|Convertir en byte con signo.|
|`int16`|Convertir en un entero de 16 bits con signo.|
|`uint16`|Convertir en un entero de 16 bits sin signo.|
|`int32, int`|Convertir en un entero de 32 bits con signo.|
|`uint32`|Convertir en un entero de 32 bits sin signo.|
|`int64`|Convertir en un entero de 64 bits con signo.|
|`uint64`|Convertir en un entero de 64 bits sin signo.|
|`nativeint`|Convertir en un entero nativo.|
|`unativeint`|Convertir en un entero nativo sin signo.|
|`float, double`|Convertir en un IEEE de doble precisión de 64 bits número de punto flotante.|
|`float32, single`|Convertir en número de punto flotante un IEEE de precisión sencilla de 32 bits.|
|`decimal`|Convertir en `System.Decimal`.|
|`char`|Convertir en `System.Char`, un carácter Unicode.|
|`enum`|Convertir en un tipo enumerado.|
Además de los tipos primitivos integrados, puede usar estos operadores con tipos que implementan `op_Explicit` o `op_Implicit` métodos con firmas adecuadas. Por ejemplo, el `int` operador de conversión funciona con cualquier tipo que proporciona un método estático `op_Explicit` que toma el tipo como parámetro y devuelve `int`. Como excepción especial a la regla general que no se puede sobrecargar métodos de tipo de valor devuelto, puede hacerlo para `op_Explicit` y `op_Implicit`.

## <a name="enumerated-types"></a>Tipos enumerados

El `enum` es un operador genérico que toma un parámetro de tipo que representa el tipo de la `enum` para convertir en. Cuando convierte en un tipo enumerado, escriba inferencia intenta determinar el tipo de la `enum` que desea convertir. En el ejemplo siguiente, la variable `col1` no está anotada explícitamente, pero su tipo se deduce de la prueba de igualdad más adelante. Por lo tanto, el compilador puede deducir que va a convertir en un `Color` enumeración. Como alternativa, puede proporcionar una anotación de tipo, como ocurre con `col2` en el ejemplo siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

También puede especificar explícitamente el tipo de enumeración de destino como un parámetro de tipo, como se muestra en el código siguiente:

```fsharp
let col3 = enum<Color> 3
```

Tenga en cuenta que la enumeración convierte trabajo sólo si el tipo subyacente de la enumeración es compatible con el tipo que se va a convertir. En el código siguiente, la conversión no se puede compilar debido a la discordancia entre `int32` y `uint32`.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

Para obtener más información, consulte [enumeraciones](enumerations.md).

## <a name="casting-object-types"></a>Convertir tipos de objeto

Conversión entre tipos en una jerarquía de objetos es fundamental para la programación orientada a objetos. Hay dos tipos básicos de conversiones: conversión de (conversión hacia arriba) y de conversión hacia abajo (conversión). Conversión de una jerarquía significa que la conversión de una referencia de objeto derivado a una referencia de objeto base. Dicha conversión garantiza que funcionar, siempre que la clase base se encuentra en la jerarquía de herencia de la clase derivada. Conversión de una jerarquía, desde una referencia de objeto base para una referencia de objeto derivado, se realiza correctamente sólo si el objeto es realmente una instancia del tipo correcto de destino (derivado) o un tipo derivado del tipo de destino.

F # proporciona operadores para estos tipos de conversiones. El `:>` operador convierte la jerarquía y el `:?>` operador convierte hacia abajo en la jerarquía.

### <a name="upcasting"></a>Conversión hacia arriba

En muchos lenguajes orientados a objetos, una conversión está implícita; en F #, las reglas son ligeramente diferentes. Una conversión se aplica automáticamente al pasar argumentos a métodos en un tipo de objeto. Sin embargo, para las funciones de enlazado a let en un módulo, una conversión no es automática, a menos que el tipo de parámetro se declara como un tipo flexible. Para obtener más información, consulte [tipos flexibles](flexible-Types.md).

El `:>` operador realiza una conversión de tipos, lo que significa que el éxito de la conversión se determina en tiempo de compilación estática. Si una conversión de tipos que usa `:>` se compila correctamente, es una conversión válida y no tiene ninguna posibilidad de error en tiempo de ejecución.

También puede usar el `upcast` operador para realizar este tipo de conversión. La expresión siguiente especifica una conversión hacia arriba en la jerarquía:

```fsharp
upcast expression
```

Cuando se usa el operador de conversión hacia arriba, el compilador intenta inferir el tipo que se va a convertir a partir del contexto. Si el compilador no puede determinar el tipo de destino, el compilador notifica un error.

### <a name="downcasting"></a>Convertir

El `:?>` operador realiza una conversión de tipos, lo que significa que el éxito de la conversión se determina en tiempo de ejecución dinámica. Una conversión de tipos que usa el `:?>` operador no se comprueba en tiempo de compilación; pero en tiempo de ejecución se realiza un intento para convertir al tipo especificado. Si el objeto es compatible con el tipo de destino, la conversión se realiza correctamente. Si el objeto no es compatible con el tipo de destino, el tiempo de ejecución genera una `InvalidCastException`.

También puede usar el `downcast` operador para realizar una conversión de tipo dinámico. La expresión siguiente especifica una conversión hacia abajo en la jerarquía a un tipo que se deduce del contexto de programa:

```fsharp
downcast expression
```

Como para el `upcast` (operador), si el compilador no puede inferir un tipo de destino específico en el contexto, notifica un error.

El código siguiente muestra el uso de la `:>` y `:?>` operadores. El código que ilustra el `:?>` operador se usa mejor cuando se sabe que conversión se realizará correctamente, ya que produce `InvalidCastException` si se produce un error en la conversión. Si no sabe que una conversión se realizará correctamente, una prueba de tipo que utiliza un `match` expresión es mejor porque evita la sobrecarga de generar una excepción.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

Dado que operadores genéricos `downcast` y `upcast` se basan en la inferencia de tipos para determinar el tipo de argumentos y valores devueltos, en el código anterior, puede reemplazar

```fsharp
let base1 = d1 :> Base1
```

with

```fsharp
let base1 = upcast d1
```

En el código anterior, el tipo de argumento y los tipos de valor devuelto son `Derived1` y `Base1`, respectivamente.

Para obtener más información acerca de las pruebas de tipo, consulte [expresiones de coincidencia](match-Expressions.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
