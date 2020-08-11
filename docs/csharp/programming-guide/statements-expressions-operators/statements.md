---
title: 'Instrucciones: Guía de programación de C#'
description: Aprenda sobre las instrucciones en la programación de C#. Vea una lista de tipos de instrucciones y examine ejemplos de código y recursos adicionales.
ms.date: 07/20/2015
helpviewer_keywords:
- statements [C#], about statements
- C# language, statements
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
ms.openlocfilehash: 3f8ac88525c44f9572f4f647145ad251537aba57
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556753"
---
# <a name="statements-c-programming-guide"></a>Instrucciones (Guía de programación de C#)

Las acciones que realiza un programa se expresan en instrucciones. Entre las acciones comunes se incluyen declarar variables, asignar valores, llamar a métodos, recorrer colecciones en bucle y crear una bifurcación a uno u otro bloque de código, en función de una condición determinada. El orden en el que se ejecutan las instrucciones en un programa se denomina flujo de control o flujo de ejecución. El flujo de control puede variar cada vez que se ejecuta un programa, en función de cómo reacciona el programa a la entrada que recibe en tiempo de ejecución.

Una instrucción puede constar de una sola línea de código que finaliza en un punto y coma o de una serie de instrucciones de una sola línea en un bloque. Un bloque de instrucciones se incluye entre llaves {} y puede contener bloques anidados. En el código siguiente se muestran dos ejemplos de instrucciones de una sola línea y un bloque de instrucciones de varias líneas:

[!code-csharp[csProgGuideStatements#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#1)]

## <a name="types-of-statements"></a>Tipos de instrucciones

En la tabla siguiente se muestran los distintos tipos de instrucciones de C# y sus palabras clave asociadas, con vínculos a temas que incluyen más información:

|Categoría|Palabras clave de C# / notas|
|--------------|---------------------------|
|[Instrucciones de declaración](#declaration-statements)|Una instrucción de declaración introduce una variable o constante nueva. Una declaración de variable puede asignar opcionalmente un valor a la variable. En una declaración de constante, se requiere la asignación.|
|[Instrucciones de expresión](#expression-statements)|Las instrucciones de expresión que calculan un valor deben almacenar el valor en una variable.|
|Instrucciones de selección|Las instrucciones de selección permiten crear bifurcaciones a diferentes secciones de código, en función de una o varias condiciones especificadas. Para obtener más información, vea los temas siguientes: <ul><li>[if](../../language-reference/keywords/if-else.md)</li><li>[else](../../language-reference/keywords/if-else.md)</li><li>[switch](../../language-reference/keywords/switch.md)</li><li>[case](../../language-reference/keywords/switch.md)</li></ul>|
|Instrucciones de iteración|Las instrucciones de iteración permiten recorrer en bucle colecciones, como matrices, o realizar el mismo conjunto de instrucciones repetidas veces hasta que se cumpla una condición especificada. Para obtener más información, vea los temas siguientes: <ul><li>[do](../../language-reference/keywords/do.md)</li><li>[for](../../language-reference/keywords/for.md)</li><li>[foreach](../../language-reference/keywords/foreach-in.md)</li><li>[in](../../language-reference/keywords/foreach-in.md)</li><li>[while](../../language-reference/keywords/while.md)</li></ul>|
|Instrucciones de salto|Las instrucciones de salto transfieren el control a otra sección de código. Para obtener más información, vea los temas siguientes: <ul><li>[break](../../language-reference/keywords/break.md)</li><li>[continue](../../language-reference/keywords/continue.md)</li><li>[default](../../language-reference/keywords/switch.md)</li><li>[goto](../../language-reference/keywords/goto.md)</li><li>[return](../../language-reference/keywords/return.md)</li><li>[yield](../../language-reference/keywords/yield.md)</li></ul>|
|Instrucciones para el control de excepciones|Las instrucciones para el control de excepciones permiten recuperarse correctamente de condiciones excepcionales producidas en tiempo de ejecución. Para obtener más información, vea los temas siguientes: <ul><li>[throw](../../language-reference/keywords/throw.md)</li><li>[try-catch](../../language-reference/keywords/try-catch.md)</li><li>[try-finally](../../language-reference/keywords/try-finally.md)</li><li>[try-catch-finally](../../language-reference/keywords/try-catch-finally.md)</li></ul>|
|[Checked y unchecked](../../language-reference/keywords/checked-and-unchecked.md)|Las instrucciones checked y unchecked permiten especificar si las operaciones numéricas pueden producir un desbordamiento cuando el resultado se almacena en una variable que es demasiado pequeña para contener el valor resultante. Para obtener más información, vea [checked](../../language-reference/keywords/checked.md) y [unchecked](../../language-reference/keywords/unchecked.md).|
|Instrucción `await`|Si marca un método con el modificador [async](../../language-reference/keywords/async.md) , puede usar el operador [await](../../language-reference/operators/await.md) en el método. Cuando el control alcanza una expresión `await` en el método asincrónico, el control se devuelve al autor de llamada y el progreso del método se suspende hasta que se completa la tarea esperada. Cuando se completa la tarea, la ejecución puede reanudarse en el método.<br /><br /> Para obtener un ejemplo sencillo, vea la sección "Métodos asincrónicos" de [Métodos](../classes-and-structs/methods.md). Para obtener más información, vea [Programación asincrónica con Async y Await](../concepts/async/index.md).|
|Instrucción `yield return`|Un iterador realiza una iteración personalizada en una colección, como una lista o matriz. Un iterador utiliza la instrucción [yield return](../../language-reference/keywords/yield.md) para devolver cada elemento de uno en uno. Cuando se alcanza una instrucción `yield return`, se recuerda la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama el iterador.<br /><br /> Para obtener más información, consulta [Iteradores](../concepts/iterators.md).|
|Instrucción `fixed`|La instrucción fixed impide que el recolector de elementos no utilizados cambie la ubicación de una variable móvil. Para obtener más información, vea [fixed](../../language-reference/keywords/fixed-statement.md).|
|Instrucción `lock`|La instrucción lock permite limitar el acceso a bloques de código a un solo subproceso de cada vez. Para obtener más información, vea [lock](../../language-reference/keywords/lock-statement.md).|
|Instrucciones con etiqueta|Puede asignar una etiqueta a una instrucción y, después, usar la palabra clave [goto](../../language-reference/keywords/goto.md) para saltar a la instrucción con etiqueta. (Vea el ejemplo de la línea siguiente).|
|[Instrucción vacía](#the-empty-statement)|La instrucción vacía consta únicamente de un punto y coma. No hace nada y se puede usar en lugares en los que se requiere una instrucción, pero no es necesario realizar ninguna acción.|

## <a name="declaration-statements"></a>Instrucciones de declaración

En el código siguiente se muestran ejemplos de declaraciones de variables con y sin una asignación inicial, y una declaración constante con la inicialización necesaria.

[!code-csharp[csProgGuideStatements#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#23)]

## <a name="expression-statements"></a>Instrucciones de expresión

En el código siguiente se muestran ejemplos de instrucciones de expresión, que incluyen la asignación, la creación de objetos con asignación y la invocación de método.

[!code-csharp[csProgGuideStatements#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#24)]

## <a name="the-empty-statement"></a>Instrucción vacía

En los ejemplos siguientes se muestran dos usos de una instrucción vacía:

[!code-csharp[csProgGuideStatements#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#25)]

## <a name="embedded-statements"></a>Instrucciones insertadas

Algunas instrucciones, incluidas [do](../../language-reference/keywords/do.md), [while](../../language-reference/keywords/while.md), [for](../../language-reference/keywords/for.md) y [foreach](../../language-reference/keywords/foreach-in.md), siempre van seguidas de una instrucción insertada. Esta instrucción insertada puede ser una sola instrucción o varias instrucciones incluidas entre llaves {} en un bloque de instrucciones. Las instrucciones insertadas de una sola línea también pueden ir entre llaves {}, como se muestra en el siguiente ejemplo:

[!code-csharp[csProgGuideStatements#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#26)]

Una instrucción insertada que no está incluida entre llaves {} no puede ser una instrucción de declaración o una instrucción con etiqueta. Esto se muestra en el ejemplo siguiente:

[!code-csharp[csProgGuideStatements#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#27)]

Coloque la instrucción insertada en un bloque para solucionar el error:

[!code-csharp[csProgGuideStatements#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#28)]

## <a name="nested-statement-blocks"></a>Bloques de instrucciones anidadas

Los bloques de instrucciones pueden anidarse, como se muestra en el código siguiente:

[!code-csharp[csProgGuideStatements#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#29)]

## <a name="unreachable-statements"></a>Instrucciones inaccesibles

Si el compilador determina que el flujo de control no puede alcanzar nunca una instrucción determinada bajo ninguna circunstancia, producirá una advertencia CS0162, como se muestra en el ejemplo siguiente:

[!code-csharp[csProgGuideStatements#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#22)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [Instrucciones](~/_csharplang/spec/statements.md) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Palabras clave de instrucciones](../../language-reference/keywords/statement-keywords.md)
- [Operadores y expresiones de C#](../../language-reference/operators/index.md)
