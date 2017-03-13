---
title: "Variables locales con asignaci&#243;n impl&#237;cita de tipos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "variables locales con asignación implícita de tipos [C#]"
  - "var [C#]"
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Variables locales con asignaci&#243;n impl&#237;cita de tipos (Gu&#237;a de programaci&#243;n de C#)
A las variables locales se les puede asignar un "tipo" deducido `var` en lugar de un tipo explícito.  La palabra clave `var` indica al compilador que deduzca el tipo de la variable a partir de la expresión que se encuentra en el lado derecho de la instrucción de inicialización.  El tipo deducido puede ser un tipo integrado, un tipo anónimo, un tipo definido por el usuario o un tipo definido en la biblioteca de clases de .NET Framework.  Para obtener más información sobre cómo inicializar matrices con `var`, vea [Matrices con tipo implícito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
 En los ejemplos siguientes se muestran varias maneras de declarar variables locales con `var`:  
  
 [!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]  
  
 Es importante entender que la palabra clave `var` no significa "variant" ni indica que la variable tenga establecimiento flexible de tipos ni que sea de enlace en tiempo de ejecución.  Simplemente significa que el compilador determina y asigna el tipo más adecuado.  
  
 La palabra clave `var` se puede usar en los siguientes contextos:  
  
-   En variables locales \(variables declaradas en el ámbito de método\), como se mostraba en el ejemplo anterior.  
  
-   En una instrucción de inicialización [for](../../../csharp/language-reference/keywords/for.md).  
  
    ```  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   En una instrucción de inicialización [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
    ```  
    foreach(var item in list){...}  
    ```  
  
-   En una instrucción [using](../../../csharp/language-reference/keywords/using-statement.md).  
  
    ```  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 Para obtener más información, vea [Cómo: Usar matrices y variables locales con tipo implícito en expresiones de consulta](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).  
  
## Var y los tipos anónimos  
 En muchos casos, el uso de `var` es opcional y es simplemente una comodidad sintáctica.  Sin embargo, cuando una variable se inicializa con un tipo anónimo, debe declarar la variable como `var` si necesita tener acceso a las propiedades del objeto en un punto posterior.  Éste es un escenario común en expresiones de consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  Para obtener más información, consulte [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 Desde la perspectiva del código fuente, un tipo anónimo no tiene nombre.  Por tanto, si una variable de consulta se ha inicializado con `var`, la única manera de tener acceso a las propiedades de la secuencia de objetos devuelta consiste en utilizar `var` como el tipo de la variable de iteración en la instrucción `foreach`.  
  
 [!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]  
  
## Comentarios  
 Las restricciones siguientes se aplican a las declaraciones de variable con tipo implícito:  
  
-   `var` solo se puede utilizar cuando una variable local se declara y se inicializa en la misma instrucción; la variable no se puede inicializar como null, como un grupo de métodos ni como una función anónima.  
  
-   `var` no se puede usar en campos en el ámbito de clase.  
  
-   Las variables declaradas con `var` no se pueden utilizar en la expresión de inicialización.  Es decir, esta expresión `: int i = (i = 20);` es válida, si bien genera un error en tiempo de compilación: `var i = (i = 20);`  
  
-   No es posible inicializar varias variables con tipo implícito en la misma instrucción.  
  
-   Si un tipo denominado `var` está dentro del ámbito, la palabra clave `var` se resolverá como ese nombre de tipo y no se tratará como parte de una declaración de variable local tipificada implícitamente.  
  
 Quizás piense que `var` también puede ser útil con expresiones de consulta en las que es difícil determinar el tipo construido exacto de la variable de consulta.  Esto puede suceder en las operaciones de agrupación y ordenación.  
  
 La palabra clave `var` también puede ser útil cuando es incómodo escribir el tipo específico de la variable en el teclado, cuando es obvio o cuando no mejora la legibilidad del código.  Un ejemplo de cómo `var` es útil en este sentido son los tipos genéricos anidados como los que se usan en las operaciones de agrupación.  En la consulta siguiente, el tipo de la variable de consulta es `IEnumerable<IGrouping<string, Student>>`.  Siempre y cuando usted y las otras personas que deben mantener el código lo entiendan, no hay ningún problema con el hecho de utilizar tipos implícitos por comodidad y brevedad.  
  
 [!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]  
  
 Sin embargo, el uso de `var` tiene al menos el potencial de dificultar la compresión de su código a otros programadores.  Por esa razón, en la documentación de C\# generalmente `var` solo se utiliza cuando es necesario.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Matrices con tipo implícito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)   
 [Cómo: Usar matrices y variables locales con tipo implícito en expresiones de consulta](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [for](../../../csharp/language-reference/keywords/for.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [using \(Instrucción\)](../../../csharp/language-reference/keywords/using-statement.md)