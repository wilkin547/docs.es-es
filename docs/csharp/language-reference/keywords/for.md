---
description: 'for (instrucción): Referencia de C#'
title: 'for (instrucción): Referencia de C#'
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: be9ecdc08d54c9cde1c49656a16e0d85a6d7084d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126936"
---
# <a name="for-c-reference"></a>for (Referencia de C#)

La instrucción `for` ejecuta una instrucción o un bloque de instrucciones mientras una expresión booleana especificada se evalúa como `true`.

En cualquier punto del bloque de instrucciones `for`, se puede salir del bucle mediante la instrucción [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la instrucción [continue](continue.md). También se puede salir de un bucle `for` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).

## <a name="structure-of-the-for-statement"></a>Estructura de la instrucción `for`

La instrucción `for` define las secciones *inicializador*, *condición* e *iterador*:

```csharp
for (initializer; condition; iterator)
    body
```

Las tres secciones son opcionales. El cuerpo del bucle es una instrucción o un bloque de instrucciones.

En el siguiente ejemplo se muestra la instrucción `for` con todas las secciones definidas:

[!code-csharp-interactive[for loop example](snippets/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a>La sección *inicializador*

Las instrucciones de la sección *inicializador* se ejecutan solo una vez, antes de entrar en el bucle. La sección *inicializador* es cualquiera de las siguientes:

- La declaración e inicialización de una variable de bucle local, a la que no se puede tener acceso desde fuera del bucle.

- Ninguna, una o varias expresiones de instrucción de la siguiente lista, separadas por comas:

  - instrucción [assignment](../operators/assignment-operator.md)

  - invocación de un método

  - expresión de [incremento](../operators/arithmetic-operators.md#increment-operator-) de prefijo o sufijo, como `++i` o `i++`

  - expresión de [decremento](../operators/arithmetic-operators.md#decrement-operator---) de prefijo o sufijo, como `--i` o `i--`

  - creación de un objeto mediante el operador [new](../operators/new-operator.md)

  - expresión [await](../operators/await.md)

La sección *inicializador* del ejemplo anterior declara e inicializa la variable de bucle local `i`:

```csharp
int i = 0
```

### <a name="the-condition-section"></a>La sección *condición*

La sección *condición*, si está presente, debe ser una expresión booleana. Dicha expresión se evalúa antes de cada iteración del bucle. Si la sección *condición* no está presente o la expresión booleana se evalúa como `true`, se ejecutará la siguiente iteración del bucle; en caso contrario, se sale del bucle.

La sección *condición* del ejemplo anterior determina si el bucle finaliza en función del valor de la variable de bucle local:

```csharp
i < 5
```

### <a name="the-iterator-section"></a>La sección *iterador*

La sección *iterador* define lo que sucede después de cada iteración del cuerpo del bucle. La sección *iterador* contiene ninguna o más de las siguientes expresiones de instrucción, separadas por comas:

- instrucción [assignment](../operators/assignment-operator.md)

- invocación de un método

- expresión de [incremento](../operators/arithmetic-operators.md#increment-operator-) de prefijo o sufijo, como `++i` o `i++`

- expresión de [decremento](../operators/arithmetic-operators.md#decrement-operator---) de prefijo o sufijo, como `--i` o `i--`

- creación de un objeto mediante el operador [new](../operators/new-operator.md)

- expresión [await](../operators/await.md)

La sección *iterador* del ejemplo anterior incrementa la variable de bucle local:

```csharp
i++
```

## <a name="examples"></a>Ejemplos

En el ejemplo siguiente se muestran varios usos menos comunes de las secciones de la instrucción `for`: asignar un valor a una variable de bucle externa en la sección *inicializador*, invocar un método en las secciones *inicializador* e *iterador*, y cambiar los valores de dos variables en la sección *iterador*. Haga clic en **Ejecutar** para ejecutar el código de ejemplo. Después, puede modificar el código y volver a ejecutarlo.

[!code-csharp-interactive[not typical for loop example](snippets/IterationKeywordsExamples.cs#6)]

En el ejemplo siguiente se define el bucle `for` infinito:

[!code-csharp[infinite for loop example](snippets/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [La declaración for](~/_csharplang/spec/statements.md#the-for-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [foreach, in](foreach-in.md)
