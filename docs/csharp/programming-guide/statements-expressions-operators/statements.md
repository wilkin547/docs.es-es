---
title: "Instrucciones (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, instrucciones"
  - "instrucciones [C#], acerca de las instrucciones"
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Instrucciones (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las acciones que realiza un programa se expresan en instrucciones.  Las acciones comunes incluyen la declaración de variables, la asignación de valores, la llamada a métodos, el recorrido en bucle de las colecciones y la creación de bifurcaciones a uno u otro bloque de código en función de una condición determinada.  El orden en que se ejecutan las instrucciones en un programa se denomina flujo de control o flujo de ejecución.  El flujo de control puede variar cada vez que se ejecuta un programa, dependiendo de cómo reacciona éste a la entrada que recibe en tiempo de ejecución.  
  
 Una instrucción puede estar compuesta por una única línea de código que finaliza en un punto y coma o por una serie de instrucciones de una línea incluidas en un bloque.  Un bloque de instrucciones se encierra entre corchetes {} y puede contener bloques anidados.  En el código siguiente se muestran dos ejemplos de instrucciones de una línea y un bloque de instrucciones de varias líneas:  
  
 [!code-cs[csProgGuideStatements#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_1.cs)]  
  
## Tipos de instrucciones  
 En la tabla siguiente se enumeran los diferentes tipos de instrucciones de C\# y sus palabras clave asociadas, con vínculos a temas que incluyen más información:  
  
|Categoría|Palabras clave de C\# \/ notas|  
|---------------|------------------------------------|  
|Instrucciones de declaración|Una instrucción de declaración introduce una nueva variable o constante.  Una declaración de variable puede asignar opcionalmente un valor a la variable.  En una declaración de constante, se requiere la asignación.<br /><br /> [!code-cs[csProgGuideStatements#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_2.cs)]|  
|Instrucciones de expresión|Las instrucciones de expresión que calculan un valor deben almacenar el valor en una variable.<br /><br /> [!code-cs[csProgGuideStatements#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_3.cs)]|  
|[Instrucciones de selección](../../../csharp/language-reference/keywords/selection-statements.md)|Las instrucciones de selección permiten crear bifurcaciones a diferentes secciones de código, en función de una o varias condiciones especificadas.  Para obtener más información, vea los temas siguientes:<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|[Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)|Las instrucciones de iteración permiten recorrer en bucle las colecciones como las matrices o bien realizar el mismo conjunto de instrucciones repetidamente hasta que se cumpla una condición especificada.  Para obtener más información, vea los temas siguientes:<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|[Instrucciones de salto](../../../csharp/language-reference/keywords/jump-statements.md)|Las instrucciones de salto transfieren el control a otra sección de código.  Para obtener más información, vea los temas siguientes:<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|[Instrucciones de control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md)|Las instrucciones de control de excepciones permiten recuperarse correctamente de condiciones excepcionales que se producen en tiempo de ejecución.  Para obtener más información, vea los temas siguientes:<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try\-catch](../../../csharp/language-reference/keywords/try-catch.md), [try\-finally](../../../csharp/language-reference/keywords/try-finally.md), [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[Checked y unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|Las instrucciones checked y unchecked permiten especificar si las operaciones numéricas pueden producir un desbordamiento cuando el resultado se almacena en una variable demasiado pequeña para contener el valor resultante.  Para obtener más información, vea [checked](../../../csharp/language-reference/keywords/checked.md) y [unchecked](../../../csharp/language-reference/keywords/unchecked.md).|  
|Instrucción `await`|Si marca un método con el modificador [async](../../../csharp/language-reference/keywords/async.md) , puede utilizar el operador [espera](../../../csharp/language-reference/keywords/await.md) en el método.  Cuando el control alcanza una expresión `await` en el método async, el control vuelve al llamador, y el progreso en el método se suspende hasta que la tarea aguardada complete.  Cuando finaliza la tarea, la ejecución se puede reanudar en el método.<br /><br /> Para obtener un ejemplo, vea la sección “métodos Async” [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md).  Para obtener más información, vea [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).|  
|Instrucción `yield return`|Un iterador realiza una iteración personalizada en una colección, como una lista o matriz.  Un iterador utiliza la instrucción [retorno de producción](../../../csharp/language-reference/keywords/yield.md) para devolver cada elemento de uno en uno.  Cuando se alcanza una instrucción `yield return` , la ubicación actual en el código se recuerda.  La ejecución se reinicia desde esa ubicación cuando el iterador se denomina la próxima vez.<br /><br /> Para obtener más información, vea [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).|  
|Instrucción `fixed`|La instrucción fixed evita que el recolector de elementos no utilizados vuelva a ubicar una variable móvil.  Para obtener más información, vea [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).|  
|Instrucción `lock`|La instrucción lock permite limitar el acceso a los bloques de código a solo un subproceso a la vez.  Para obtener más información, vea [lock](../../../csharp/language-reference/keywords/lock-statement.md).|  
|Instrucciones con etiquetas|Puede asignar una etiqueta a una instrucción y, a continuación, utilizar la palabra clave [goto](../../../csharp/language-reference/keywords/goto.md) para saltar a la instrucción con la etiqueta.  \(Vea el ejemplo de la fila siguiente.\)|  
|Instrucción vacía|La instrucción vacía está compuesta solo por un punto y coma.  No hace nada y se puede utilizar en lugares donde se requiere una instrucción pero no es necesario realizar ninguna acción.  En los ejemplos siguientes se muestran dos usos de una instrucción vacía:<br /><br /> [!code-cs[csProgGuideStatements#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_4.cs)]|  
  
## Instrucciones incrustadas  
 Algunas instrucciones, incluidas [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) y [foreach](../../../csharp/language-reference/keywords/foreach-in.md), siempre cuentan con instrucciones incrustadas a continuación.  Esta instrucción incrustada puede ser una instrucción única o varias instrucciones encerradas entre corchetes {} en un bloque de instrucciones.  Las instrucciones incrustadas de una línea también se pueden encerrar entre corchetes {}, tal como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideStatements#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_5.cs)]  
  
 Una instrucción incrustada que no se encierra entre corchetes {} no puede ser una instrucción de declaración ni una instrucción con etiquetas.  Esto se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideStatements#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_6.cs)]  
  
 Coloque la instrucción incrustada en un bloque para corregir el error:  
  
 [!code-cs[csProgGuideStatements#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_7.cs)]  
  
## Bloques de instrucciones anidados  
 Los bloques de instrucciones pueden estar anidados, tal como se muestra en el código siguiente:  
  
 [!code-cs[csProgGuideStatements#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_8.cs)]  
  
## Instrucciones inalcanzables  
 Si el compilador determina que el flujo de control nunca puede alcanzar una instrucción determinada bajo ninguna circunstancia, generará la advertencia CS0162, tal como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideStatements#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_9.cs)]  
  
## Secciones relacionadas  
  
-   [Palabras clave de instrucciones](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
-   [Expresiones](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
-   [Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)