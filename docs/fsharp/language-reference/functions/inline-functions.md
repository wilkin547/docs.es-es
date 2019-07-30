---
title: Funciones insertadas
description: Obtenga información sobre cómo F# usar las funciones insertadas que se integran directamente en el código de llamada.
ms.date: 05/16/2016
ms.openlocfilehash: 2830d1ada5b3005c3fcae975a44e85a7c84554f7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630681"
---
# <a name="inline-functions"></a>Funciones insertadas

*Las funciones insertadas* son funciones que se integran directamente en el código de llamada.

## <a name="using-inline-functions"></a>Usar funciones insertadas

Cuando se usan parámetros de tipo estático, cualquier función que esté parametrizada por parámetros de tipo debe estar alineada. Esto garantiza que el compilador puede resolver estos parámetros de tipo. Cuando se usan parámetros de tipo genérico normales, no hay ninguna restricción.

Aparte de habilitar el uso de restricciones de miembro, las funciones insertadas pueden ser útiles para optimizar el código. Sin embargo, el uso excesivo de las funciones insertadas puede hacer que el código sea menos resistente a los cambios en las optimizaciones del compilador y la implementación de las funciones de la biblioteca. Por esta razón, debe evitar el uso de funciones insertadas para la optimización a menos que haya intentado todas las demás técnicas de optimización. Hacer que una función o un método insertado a veces puede mejorar el rendimiento, pero no siempre es el caso. Por lo tanto, también debe usar medidas de rendimiento para comprobar que la realización de cualquier función insertada en realidad tiene un efecto positivo.

El `inline` modificador se puede aplicar a las funciones en el nivel superior, en el nivel de módulo o en el nivel de método de una clase.

En el ejemplo de código siguiente se muestra una función insertada en el nivel superior, un método de instancia insertado y un método estático insertado.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a>Funciones insertadas e inferencia de tipos

La presencia de `inline` afecta a la inferencia de tipos. Esto se debe a que las funciones insertadas pueden tener parámetros de tipo resueltos estáticamente, mientras que las funciones no insertadas no pueden. En el ejemplo de código siguiente se muestra `inline` un caso en el que resulta útil porque se está usando una función que tiene un parámetro de `float` tipo resuelto estáticamente, el operador de conversión.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

Sin el `inline` modificador, la inferencia de tipos fuerza a la función a tomar un tipo específico, `int`en este caso. Pero con el `inline` modificador, la función también se deduce para tener un parámetro de tipo resuelto estáticamente. Con el `inline` modificador, se deduce que el tipo es el siguiente:

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

Esto significa que la función acepta cualquier tipo que admita una conversión a **float**.

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
- [Restricciones](../generics/constraints.md)
- [Parámetros de tipo resueltos estáticamente](../generics/statically-resolved-type-parameters.md)
