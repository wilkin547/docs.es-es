---
title: "Instrucciones (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- statements [C#], about statements
- C# language, statements
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 166130ca7a63127d0bd1df8328dc08b4a8cd7845
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="statements-c-programming-guide"></a>Instrucciones (Guía de programación de C#)
Las acciones que realiza un programa se expresan en instrucciones. Entre las acciones comunes se incluyen declarar variables, asignar valores, llamar a métodos, recorrer colecciones en bucle y crear una bifurcación a uno u otro bloque de código, en función de una condición determinada. El orden en el que se ejecutan las instrucciones en un programa se denomina flujo de control o flujo de ejecución. El flujo de control puede variar cada vez que se ejecuta un programa, en función de cómo reacciona el programa a la entrada que recibe en tiempo de ejecución.  
  
 Una instrucción puede constar de una sola línea de código que finaliza en un punto y coma o de una serie de instrucciones de una sola línea en un bloque. Un bloque de instrucciones se incluye entre llaves {} y puede contener bloques anidados. En el código siguiente se muestran dos ejemplos de instrucciones de una sola línea y un bloque de instrucciones de varias líneas:  
  
 [!code-csharp[csProgGuideStatements#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_1.cs)]  
  
## <a name="types-of-statements"></a>Tipos de instrucciones  
 En la tabla siguiente se muestran los distintos tipos de instrucciones de C# y sus palabras clave asociadas, con vínculos a temas que incluyen más información:  
  
|Categoría|Palabras clave de C# / notas|  
|--------------|---------------------------|  
|Instrucciones de declaración|Una instrucción de declaración introduce una variable o constante nueva. Una declaración de variable puede asignar opcionalmente un valor a la variable. En una declaración de constante, se requiere la asignación.<br /><br /> [!code-csharp[csProgGuideStatements#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_2.cs)]|  
|Instrucciones de expresión|Las instrucciones de expresión que calculan un valor deben almacenar el valor en una variable.<br /><br /> [!code-csharp[csProgGuideStatements#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_3.cs)]|  
|[Instrucciones de selección](../../../csharp/language-reference/keywords/selection-statements.md)|Las instrucciones de selección permiten crear bifurcaciones a diferentes secciones de código, en función de una o varias condiciones especificadas. Para obtener más información, vea los temas siguientes:<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|[Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)|Las instrucciones de iteración permiten recorrer en bucle colecciones, como matrices, o realizar el mismo conjunto de instrucciones repetidas veces hasta que se cumpla una condición especificada. Para obtener más información, vea los temas siguientes:<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|[Instrucciones de salto](../../../csharp/language-reference/keywords/jump-statements.md)|Las instrucciones de salto transfieren el control a otra sección de código. Para obtener más información, vea los temas siguientes:<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|[Instrucciones para el control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md)|Las instrucciones para el control de excepciones permiten recuperarse correctamente de condiciones excepcionales producidas en tiempo de ejecución. Para obtener más información, vea los temas siguientes:<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try-catch](../../../csharp/language-reference/keywords/try-catch.md), [try-finally](../../../csharp/language-reference/keywords/try-finally.md), [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[Checked y unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|Las instrucciones checked y unchecked permiten especificar si las operaciones numéricas pueden producir un desbordamiento cuando el resultado se almacena en una variable que es demasiado pequeña para contener el valor resultante. Para obtener más información, vea [checked](../../../csharp/language-reference/keywords/checked.md) y [unchecked](../../../csharp/language-reference/keywords/unchecked.md).|  
|Instrucción `await`|Si marca un método con el modificador [async](../../../csharp/language-reference/keywords/async.md) , puede usar el operador [await](../../../csharp/language-reference/keywords/await.md) en el método. Cuando el control alcanza una expresión `await` en el método asincrónico, el control se devuelve al autor de llamada y el progreso del método se suspende hasta que se completa la tarea esperada. Cuando se completa la tarea, la ejecución puede reanudarse en el método.<br /><br /> Para obtener un ejemplo sencillo, vea la sección "Métodos asincrónicos" de [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md). Para obtener más información, vea [Programación asincrónica con Async y Await](../../../csharp/programming-guide/concepts/async/index.md).|  
|Instrucción `yield return`|Un iterador realiza una iteración personalizada en una colección, como una lista o matriz. Un iterador usa la instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) para devolver cada elemento de uno en uno. Cuando se alcanza una instrucción `yield return`, se recuerda la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama el iterador.<br /><br /> Para más información, vea [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).|  
|Instrucción `fixed`|La instrucción fixed impide que el recolector de elementos no utilizados cambie la ubicación de una variable móvil. Para obtener más información, vea [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).|  
|Instrucción `lock`|La instrucción lock permite limitar el acceso a bloques de código a un solo subproceso de cada vez. Para obtener más información, vea [lock](../../../csharp/language-reference/keywords/lock-statement.md).|  
|Instrucciones con etiqueta|Puede asignar una etiqueta a una instrucción y, después, usar la palabra clave [goto](../../../csharp/language-reference/keywords/goto.md) para saltar a la instrucción con etiqueta. (Vea el ejemplo de la línea siguiente).|  
|Instrucción vacía|La instrucción vacía consta únicamente de un punto y coma. No hace nada y se puede usar en lugares en los que se requiere una instrucción, pero no es necesario realizar ninguna acción. En los ejemplos siguientes se muestran dos usos de una instrucción vacía:<br /><br /> [!code-csharp[csProgGuideStatements#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_4.cs)]|  
  
## <a name="embedded-statements"></a>Instrucciones insertadas  
 Algunas instrucciones, incluidas [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) y [foreach](../../../csharp/language-reference/keywords/foreach-in.md), siempre van seguidas de una instrucción insertada. Esta instrucción insertada puede ser una sola instrucción o varias instrucciones incluidas entre llaves {} en un bloque de instrucciones. Las instrucciones insertadas de una sola línea también pueden ir entre llaves {}, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStatements#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_5.cs)]  
  
 Una instrucción insertada que no está incluida entre llaves {} no puede ser una instrucción de declaración o una instrucción con etiqueta. Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStatements#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_6.cs)]  
  
 Coloque la instrucción insertada en un bloque para solucionar el error:  
  
 [!code-csharp[csProgGuideStatements#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_7.cs)]  
  
## <a name="nested-statement-blocks"></a>Bloques de instrucciones anidados  
 Los bloques de instrucciones pueden anidarse, como se muestra en el código siguiente:  
  
 [!code-csharp[csProgGuideStatements#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_8.cs)]  
  
## <a name="unreachable-statements"></a>Instrucciones inaccesibles  
 Si el compilador determina que el flujo de control no puede alcanzar nunca una instrucción determinada bajo ninguna circunstancia, producirá una advertencia CS0162, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStatements#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_9.cs)]  
  
## <a name="related-sections"></a>Secciones relacionadas  
  
-   [Palabras clave de instrucciones](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
-   [Expresiones](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
-   [Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)
