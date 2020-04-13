---
title: Procedimiento para convertir de forma segura mediante la coincidencia de patrones y los operadores is y as
description: Aprenda a usar técnicas de coincidencia de patrones para convertir de forma segura las variables en otro tipo. Puede usar la coincidencia de patrones y los operadores is y as para convertir tipos de forma segura.
ms.date: 09/05/2018
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.openlocfilehash: 60e69a8ef55484e3b04f1674c35a1c5dadfa3b7c
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81120993"
---
# <a name="how-to-safely-cast-by-using-pattern-matching-and-the-is-and-as-operators"></a>Procedimiento para convertir de forma segura mediante la coincidencia de patrones y los operadores is y as

Dado que los objetos son polimórficos, es posible que una variable de un tipo de clase base contenga un [tipo](../programming-guide/types/index.md) derivado. Para acceder a los miembros de instancia del tipo derivado, es necesario volver a [convertir](../programming-guide/types/casting-and-type-conversions.md) el valor en el tipo derivado. Pero una conversión conlleva el riesgo de producir una <xref:System.InvalidCastException>. C# proporciona instrucciones de [coincidencia de patrones](../pattern-matching.md) que realizan una conversión condicionalmente, solo si se va a realizar correctamente. C# además proporciona los operadores [is](../language-reference/operators/type-testing-and-cast.md#is-operator) y [as](../language-reference/operators/type-testing-and-cast.md#as-operator) para probar si un valor es de un tipo determinado.

En el ejemplo siguiente se muestra cómo usar la instrucción `is` de coincidencia de patrones.

[!code-csharp[Pattern matching is statement](../../../samples/snippets/csharp/how-to/safelycast/patternmatching/Program.cs#PatternMatchingIs)]

El ejemplo anterior muestra una serie de características de sintaxis de coincidencia de patrones. La instrucción `if (a is Mammal m)` combina la prueba con una asignación de inicialización. La asignación solo se produce cuando la prueba se realiza correctamente. La variable `m` solo está en ámbito en la instrucción `if` insertada donde se ha asignado. No se puede acceder a `m` más adelante en el mismo método. En el ejemplo anterior también se muestra cómo usar el operador [`as`](../language-reference/operators/type-testing-and-cast.md#as-operator) para convertir un objeto en un tipo especificado.

También puede usar la misma sintaxis para probar si un [tipo de valor que admite valores NULL](../language-reference/builtin-types/nullable-value-types.md) tiene un valor, como se muestra en el ejemplo siguiente:

[!code-csharp[Pattern matching with nullable types](../../../samples/snippets/csharp/how-to/safelycast/nullablepatternmatching/Program.cs#PatternMatchingNullable)]

El ejemplo anterior muestra otras características de coincidencia de patrones para usar con conversiones. Puede probar una variable para el patrón null si busca específicamente el valor `null`. Cuando el valor de runtime de la variable es `null`, una instrucción `is` que busca un tipo siempre devuelve `false`. La instrucción `is` de coincidencia de patrones no permite un tipo de valor que acepta valores NULL, como `int?` o `Nullable<int>`, pero puede probar con cualquier otro tipo de valor. Los patrones `is` del ejemplo anterior no se limitan a los tipos de valor que admiten un valor NULL. También puede usar esos patrones para probar si una variable de un tipo de referencia tiene un valor o es `null`.

En el ejemplo anterior también se muestra cómo usar el patrón de tipo en una instrucción `switch` donde la variable puede ser uno de muchos tipos diferentes.

Si quiere probar si una variable es de un tipo determinado, pero no asignarla a una nueva variable, puede usar los operadores `is` y `as` para los tipos de referencia y los tipos que aceptan valores NULL. El código siguiente muestra cómo usar las instrucciones `is` y `as` que formaban parte del lenguaje C# antes de la incorporación de la coincidencia de patrones para probar si una variable es de un tipo determinado:

[!code-csharp[testing variable types with the is and as statements](../../../samples/snippets/csharp/how-to/safelycast/asandis/Program.cs#IsAndAs)]

Como puede ver al comparar este código con el código de coincidencia de patrones, la sintaxis de coincidencia de patrones proporciona características más sólidas mediante la combinación de la prueba y la asignación en una sola instrucción. Use la sintaxis de coincidencia de patrones siempre que sea posible.

Eche un vistazo al código de nuestro [repositorio de GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/safelycast) y pruebe estos ejemplos. O bien, puede descargar los ejemplos [como un archivo ZIP](../../../samples/snippets/csharp/how-to/safelycast.zip).
