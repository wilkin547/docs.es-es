---
title: "Convenciones de c&#243;digo de C# (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, convenciones de código"
  - "convenciones de código, C#"
  - "Visual C#, convenciones de código"
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# Convenciones de c&#243;digo de C# (Gu&#237;a de programaci&#243;n de C#)
La [Especificación del lenguaje C\#](http://go.microsoft.com/fwlink/?LinkId=199552) no define un estándar de codificación.  Sin embargo, Microsoft utiliza las instrucciones de este tema para desarrollar ejemplos y documentación.  
  
 Las convenciones de codificación tienen los objetivos siguientes:  
  
-   Crean una apariencia coherente en el código, para que los lectores puedan centrarse en el contenido, no en el diseño.  
  
-   Permiten a los lectores comprender el código más rápidamente al hacer suposiciones basadas en la experiencia anterior.  
  
-   Facilitan la copia, el cambio y el mantenimiento del código.  
  
-   Muestran los procedimientos recomendados de C\#.  
  
## Convenciones de nomenclatura  
  
-   En breves ejemplos que no incluyen [directivas using](../../../csharp/language-reference/keywords/using-directive.md), utilice calificaciones de espacio de nombres.  Si sabe que un espacio de nombres se importa en un proyecto de forma predeterminada, no es necesario completar los nombres de ese espacio de nombres.  Los nombres completos pueden partirse después de un punto \(.\) si son demasiado largos para una sola línea, como se muestra en el ejemplo siguiente.  
  
     [!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]  
  
-   No es necesario cambiar los nombres de objetos que se crearon con las herramientas del diseñador de Visual Studio para que se ajusten a otras directrices.  
  
## Convenciones de diseño  
 Un buen diseño utiliza un formato que destaque la estructura del código y haga que el código sea más fácil de leer.  Las muestras y ejemplos de Microsoft cumplen las convenciones siguientes:  
  
-   Utilice la configuración del Editor de código predeterminada \(sangría automática, sangrías de 4 caracteres, tabulaciones guardadas como espacios\).  Para obtener más información, vea [Opciones, editor de texto, C\#, formato](/visual-studio/ide/reference/options-text-editor-csharp-formatting).  
  
-   Escriba solo una instrucción por línea.  
  
-   Escriba solo una declaración por línea.  
  
-   Si a las líneas de continuación no se les aplica sangría automáticamente, hágalo con una tabulación \(cuatro espacios\).  
  
-   Agregue al menos una línea en blanco entre las definiciones de método y las de propiedad.  
  
-   Utilice paréntesis para que las cláusulas de una expresión sean evidentes, como se muestra en el código siguiente.  
  
     [!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]  
  
## Convenciones de los comentarios  
  
-   Coloque el comentario en una línea independiente, no al final de una línea de código.  
  
-   Comience el texto del comentario con una letra mayúscula.  
  
-   Finalice el texto del comentario con un punto.  
  
-   Inserte un espacio entre el delimitador de comentario \(\/\/\) y el texto del comentario, como se muestra en el ejemplo siguiente.  
  
     [!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]  
  
-   No cree bloques con formato de asteriscos alrededor de comentarios.  
  
## Convenciones de lenguaje  
 En las secciones siguientes se describen las prácticas que sigue el equipo C\# para preparar las muestras y ejemplos de código.  
  
### String \(Tipo de datos\)  
  
-   Utilice el operador `+` para concatenar cadenas cortas, como se muestra en el código siguiente.  
  
     [!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]  
  
-   Para anexar cadenas en bucles, especialmente cuando se trabaja con grandes cantidades de texto, utilice un objeto <xref:System.Text.StringBuilder>.  
  
     [!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]  
  
### Variables locales con asignación implícita de tipos  
  
-   Utilice [tipos implícitos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) para las variables locales cuando el tipo de la variable sea obvio desde el lado derecho de la asignación, o cuando el tipo exacto no sea importante.  
  
     [!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]  
  
-   No utilice [var](../../../csharp/language-reference/keywords/var.md) cuando el tipo no sea evidente desde el lado derecho de la asignación.  
  
     [!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]  
  
-   No confíe en el nombre de variable para especificar el tipo de la variable.  Puede no ser correcto.  
  
     [!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]  
  
-   Evite el uso de `var` en lugar de [dynamic](../../../csharp/language-reference/keywords/dynamic.md).  
  
-   Utilice tipos implícitos para determinar el tipo de la variable de bucle en bucles [for](../../../csharp/language-reference/keywords/for.md) y [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
     En el ejemplo siguiente se usan tipos implícitos en una instrucción `for`.  
  
     [!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]  
  
     En el ejemplo siguiente se usan tipos implícitos en una instrucción `foreach`.  
  
     [!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]  
  
### Tipo de datos sin signo  
  
-   En general, utilice `int` en lugar de tipos sin signo.  El uso de `int` es común en todo C\#, y es más fácil interactuar con otras bibliotecas cuando se usa `int`.  
  
### Matrices  
  
-   Utilice sintaxis concisa para inicializar las matrices en la línea de declaración.  
  
     [!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]  
  
### Delegados  
  
-   Utilice sintaxis concisa para crear instancias de un tipo de delegado.  
  
     [!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]  
  
     [!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]  
  
### Instrucciones try\-catch y using en el control de excepciones  
  
-   Utilice una instrucción [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) en la mayoría de casos de control de excepciones.  
  
     [!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]  
  
-   Simplifique el código mediante el uso de la [instrucción using](../../../csharp/language-reference/keywords/using-statement.md) de C\#.  Si tiene una instrucción [try\-finally](../../../csharp/language-reference/keywords/try-finally.md) en la que el único código del bloque `finally` es una llamada al método <xref:System.IDisposable.Dispose%2A>, utilice en su lugar una instrucción `using`.  
  
     [!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]  
  
### Operadores && y &#124;&#124;  
  
-   Para evitar excepciones y aumentar el rendimiento omitiendo las comparaciones innecesarias, utilice [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) en lugar de [&](../../../csharp/language-reference/operators/and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) en lugar de                                       [&#124;](../../../csharp/language-reference/operators/or-operator.md) cuando realice comparaciones, como se muestra en el ejemplo siguiente.  
  
     [!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]  
  
### New \(Operador\)  
  
-   Utilice la forma concisa de la creación de instancias de objeto con tipos implícitos, como se muestra en la siguiente declaración.  
  
     [!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]  
  
     La línea anterior es equivalente a la siguiente declaración.  
  
     [!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]  
  
-   Utilice inicializadores de objeto para simplificar la creación de objetos.  
  
     [!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]  
  
### Control de eventos  
  
-   Si va a definir un controlador de eventos que no es necesario quitar más tarde, utilice una expresión lambda.  
  
     [!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]  
  
     [!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]  
  
### Miembros estáticos  
  
-   Llame a miembros [estáticos](../../../csharp/language-reference/keywords/static.md) con el nombre de clase: *ClassName.StaticMember*.  Esta práctica hace que el código sea más legible al clarificar el acceso estático.  No califique un miembro estático definido en una clase base con el nombre de una clase derivada.  Mientras el código se compila, su legibilidad se presta a confusión, y puede interrumpirse en el futuro si se agrega a un miembro estático con el mismo nombre a la clase derivada.  
  
### Consultas LINQ  
  
-   Utilice nombres descriptivos para las variables de consulta.  En el ejemplo siguiente, se utiliza `seattleCustomers` para los clientes que se encuentran en Seattle.  
  
     [!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]  
  
-   Utilice alias para asegurarse de que los nombres de propiedad de tipos anónimos se escriben correctamente con mayúscula o minúscula, usando para ello la grafía Pascal.  
  
     [!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]  
  
-   Cambie el nombre de las propiedades cuando puedan ser ambiguos en el resultado.  Por ejemplo, si la consulta devuelve un nombre de cliente y un identificador de distribuidor, en lugar de dejarlos como `Name` e `ID` en el resultado, cambie su nombre para aclarar que `Name` es el nombre de un cliente e `ID` es el identificador de un distribuidor.  
  
     [!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]  
  
-   Utilice tipos implícitos en la declaración de variables de consulta y variables de intervalo.  
  
     [!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]  
  
-   Alinee las cláusulas de consulta bajo la cláusula [from](../../../csharp/language-reference/keywords/from-clause.md), como se muestra en los ejemplos anteriores.  
  
-   Utilice cláusulas [where](../../../csharp/language-reference/keywords/where-clause.md) antes de otras cláusulas de consulta para asegurarse de que las cláusulas de consulta posteriores operan en un conjunto de datos reducido y filtrado.  
  
     [!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]  
  
-   Utilice varias cláusulas `from` en lugar de una cláusula [join](../../../csharp/language-reference/keywords/join-clause.md) para acceder a colecciones internas.  Por ejemplo, una colección de objetos `Student` podría contener cada uno un conjunto de resultados de exámenes.  Cuando se ejecuta la siguiente consulta, devuelve cada resultado superior a 90, además del apellido del alumno que recibió la puntuación.  
  
     [!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]  
  
## Seguridad  
 Siga las instrucciones de [Secure Coding Guidelines](../Topic/Secure%20Coding%20Guidelines.md).  
  
## Vea también  
 [Convenciones de código de Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)   
 [Secure Coding Guidelines](../Topic/Secure%20Coding%20Guidelines.md)