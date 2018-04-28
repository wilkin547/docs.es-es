---
title: Conversiones (F#)
description: 'Obtenga información acerca de cómo el lenguaje de programación de F # proporciona operadores de conversión para las conversiones aritméticas entre distintos tipos primitivos.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 410c7da2b7ae8a09c58e8c89b24d0093a7f33a5c
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="casting-and-conversions-f"></a>Conversiones (F#)

Este tema describe la compatibilidad con las conversiones de tipos en F #.

## <a name="arithmetic-types"></a>Tipos aritméticos
F # proporciona operadores de conversión para las conversiones aritméticas entre distintos tipos primitivos, como entre enteros y tipos de punto flotante. Los operadores de conversión de enteros y char se comprobaron y formularios no está activadas; el punto flotante operadores y `enum` operador de conversión no tienen que serlo. Los formularios no está activados se definen en `Microsoft.FSharp.Core.Operators` y la activada, los formularios se definen en `Microsoft.FSharp.Core.Operators.Checked`. Las formas comprobadas comprobación el desbordamiento y generan una excepción en tiempo de ejecución si el valor resultante supera los límites del tipo de destino.

Cada uno de estos operadores tiene el mismo nombre que el nombre del tipo de destino. Por ejemplo, en el código siguiente, en el que los tipos se anotan explícitamente, `byte` aparece con dos significados diferentes. La primera aparición es el tipo y el segundo es el operador de conversión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

La siguiente tabla muestra los operadores de conversión definidos en F #.

|Operador|Descripción|
|--------|-----------|
|`byte`|Convertir en un byte, un tipo sin signo de 8 bits.|
|`sbyte`|Convertir en un byte con signo.|
|`int16`|Convertir en un entero de 16 bits con signo.|
|`uint16`|Convertir en un entero de 16 bits sin signo.|
|`int32, int`|Convertir en un entero de 32 bits con signo.|
|`uint32`|Convertir en un entero de 32 bits sin signo.|
|`int64`|Convertir en un entero de 64 bits con signo.|
|`uint64`|Convertir en un entero de 64 bits sin signo.|
|`nativeint`|Convertir en un entero nativo.|
|`unativeint`|Convertir en un entero nativo sin signo.|
|`float, double`|Convertir en un IEEE de doble precisión de 64 bits números de punto flotante.|
|`float32, single`|Convertir en un IEEE de precisión sencilla de 32 bits números de punto flotante.|
|`decimal`|Convertir en `System.Decimal`.|
|`char`|Convertir en `System.Char`, un carácter Unicode.|
|`enum`|Convertir a un tipo enumerado.|
Además de los tipos primitivos integrados, puede utilizar estos operadores con tipos que implementan `op_Explicit` o `op_Implicit` métodos con firmas adecuadas. Por ejemplo, el `int` operador de conversión funciona con cualquier tipo que proporciona un método estático `op_Explicit` que toma el tipo como un parámetro y devuelve `int`. Como una excepción especial para el que no se pueden sobrecargar métodos por tipo de valor devuelto por regla general, también puede hacer esto para `op_Explicit` y `op_Implicit`.

## <a name="enumerated-types"></a>Tipos enumerados
El `enum` es un operador genérico que toma un parámetro de tipo que representa el tipo de la `enum` para convertir en. Cuando convierte en un tipo enumerado, escriba inferencia intenta determinar el tipo de la `enum` que desea convertir. En el ejemplo siguiente, la variable `col1` no está anotada explícitamente, pero su tipo se deduce de la prueba de igualdad posterior. Por lo tanto, el compilador puede deducir que va a convertir en un `Color` enumeración. Como alternativa, puede proporcionar una anotación de tipo, al igual que con `col2` en el ejemplo siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
También puede especificar explícitamente el tipo de enumeración de destino como un parámetro de tipo, como en el código siguiente:

```fsharp
let col3 = enum<Color> 3
```

Tenga en cuenta que la enumeración convierte trabajo solo si el tipo subyacente de la enumeración es compatible con el tipo que se va a convertir. En el código siguiente, la conversión no se puede compilar debido a la falta de correspondencia entre `int32` y `uint32`.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

Para obtener más información, consulte [enumeraciones](enumerations.md).

## <a name="casting-object-types"></a>Conversión de tipos de objeto
Conversión entre tipos en una jerarquía de objetos, es fundamental para la programación orientada a objetos. Hay dos tipos básicos de conversiones: (conversión hacia arriba) de conversión y conversión en tipos inferiores (conversión). Conversión de una jerarquía significa que la conversión de una referencia a objeto derivada a una referencia de objeto base. Se garantiza que una conversión de tipos para que funcione como la clase base está en la jerarquía de herencia de la clase derivada. Conversión de una jerarquía, de una referencia de objeto base para una referencia de objeto derivado, se realiza correctamente sólo si el objeto es realmente una instancia del tipo de destino correcto (derivado) o un tipo derivado del tipo de destino.

F # proporciona operadores para estos tipos de conversiones. El `:>` operador convierte hacia arriba en la jerarquía y el `:?>` operador convierte hacia abajo en la jerarquía.

### <a name="upcasting"></a>Conversión hacia arriba
En muchos lenguajes orientados a objetos, una conversión es implícita; en F #, las reglas son ligeramente diferentes. Conversión hacia arriba se aplica automáticamente cuando se pasan argumentos a los métodos en un tipo de objeto. Sin embargo, para las funciones enlazadas a permiten en un módulo, una conversión no es automática, a menos que el tipo de parámetro se declara como un tipo flexible. Para obtener más información, consulte [tipos flexibles](flexible-Types.md).

El `:>` operador realiza una conversión de tipos, lo que significa que el éxito de la conversión se determina en tiempo de compilación estática. Si una conversión que utiliza `:>` se compila correctamente, es una conversión válida y no tiene ninguna posibilidad de error en tiempo de ejecución.

También puede usar el `upcast` operador para realizar este tipo de conversión. La expresión siguiente especifica una conversión hacia arriba en la jerarquía:

```fsharp
upcast expression
```

Cuando se usa el upcast (operador), el compilador intenta inferir el tipo que se va a convertir a partir del contexto. Si el compilador no puede determinar el tipo de destino, el compilador informa de un error.

### <a name="downcasting"></a>Convertir a tipo heredado
El `:?>` operador realiza una conversión de tipos, lo que significa que el éxito de la conversión se determina en tiempo de ejecución dinámica. Una conversión que utiliza el `:?>` operador no se comprueba en tiempo de compilación; pero en tiempo de ejecución, se realiza un intento para convertir al tipo especificado. Si el objeto es compatible con el tipo de destino, la conversión se realiza correctamente. Si el objeto no es compatible con el tipo de destino, el tiempo de ejecución genera un `InvalidCastException`.

También puede usar el `downcast` operador que se va a realizar una conversión de tipo dinámico. La expresión siguiente especifica una conversión hacia abajo en la jerarquía a un tipo que se deduce del contexto de programa:

```fsharp
downcast expression
```

Igual que en el `upcast` (operador), si el compilador no puede inferir un tipo de destino específico en el contexto, notifica un error.

El código siguiente muestra el uso de la `:>` y `:?>` operadores. El código que muestra la `:?>` operador se usa mejor cuando se sabe que conversión se realizará correctamente, porque produce `InvalidCastException` si se produce un error en la conversión. Si no sabe que una conversión se realizará correctamente, una prueba de tipo que utiliza un `match` expresión es mejor porque evita la sobrecarga de generar una excepción.

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
[Referencia del lenguaje F#](index.md)
