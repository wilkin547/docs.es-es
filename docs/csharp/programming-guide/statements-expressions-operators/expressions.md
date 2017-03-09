---
title: "Expresiones (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, expresiones"
  - "expresiones [C#]"
ms.assetid: c7d8feb0-0e58-4f94-8bf6-4d070550a832
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# Expresiones (Gu&#237;a de programaci&#243;n de C#)
Una *expresión* es una secuencia de uno o más operandos y cero o más operadores que se pueden evaluar como un valor, objeto, método o espacio de nombres único.  Las expresiones pueden constar de un valor literal, una invocación de método, un operador y sus operandos o un *nombre simple*.  Los nombres simples pueden ser el nombre de una variable, miembro de tipo, parámetro de método, espacio de nombres o tipo.  
  
 Las expresiones pueden utilizar operadores que, a su vez, utilizan otras expresiones como parámetros o llamadas a métodos cuyos parámetros son, a su vez, otras llamadas a métodos, de modo que pueden variar de simples a muy complejas.  A continuación se muestran dos ejemplos de expresiones:  
  
```  
((x < 10) && ( x > 5)) || ((x > 20) && (x < 25))   
System.Convert.ToInt32("35")  
```  
  
## Valores de expresión  
 En la mayoría de los contextos donde se utilizan expresiones, por ejemplo en instrucciones o parámetros de método, se espera que la expresión se evalúe como algún valor.  Si x e y son enteros, la expresión `x + y` se evalúa como un valor numérico.  La expresión `new MyClass()` se evalúa como una referencia a una nueva instancia de un objeto `MyClass`.  La expresión `myClass.ToString()` se evalúa como una cadena porque éste es el tipo de valor devuelto del método.  Sin embargo, aunque un nombre de espacio de nombres se clasifique como una expresión, no se evalúa como un valor y por tanto nunca puede ser el resultado final de una expresión.  No puede pasar un nombre de espacio de nombres a un parámetro de método, utilizarlo en una nueva expresión ni asignarlo a una variable.  Solo puede utilizarlo como una subexpresión en una expresión mayor.  Lo mismo sucede con los tipos \(a diferencia de los objetos <xref:System.Type?displayProperty=fullName> \), los nombres de grupo de métodos \(a diferencia de los métodos específicos\) y los descriptores de acceso [add](../../../csharp/language-reference/keywords/add.md) y [remove](../../../csharp/language-reference/keywords/remove.md) de eventos.  
  
 Todos los valores tienen un tipo asociado.  Por ejemplo, si x e y son variables de tipo `int`, el valor de la expresión `x + y` también es de tipo `int`.  Si el valor se asigna a una variable de un tipo diferente, o si x e y son de tipos diferentes, se aplican las reglas de conversión de tipos.  Para obtener más información sobre el funcionamiento de estas conversiones, vea [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
## Desbordamientos  
 Las expresiones numéricas pueden producir desbordamientos si el valor es mayor que el valor máximo del tipo del valor.  Para obtener más información, vea [Checked y unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) y [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
## Prioridad y asociatividad de los operadores  
 Las reglas de asociatividad y prioridad de operadores rigen la manera en la que se evalúa una expresión.  Para obtener más información, vea [Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md).  
  
 La mayoría de las expresiones, excepto las expresiones de asignación y las expresiones de invocación de método, se deben incrustar en una instrucción.  Para obtener más información, vea [Instrucciones](../../../csharp/programming-guide/statements-expressions-operators/statements.md).  
  
## Literales y nombres simples  
 Los dos tipos de expresiones más simples son literales y nombres simples.  Un literal es un valor constante que no tiene ningún nombre.  Por ejemplo, en el código siguiente, `5` y `"Hello World"` son valores literales:  
  
 [!code-cs[csProgGuideStatements#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/expressions_1.cs)]  
  
 Para obtener más información sobre literales, vea [Tipos](../../../csharp/language-reference/keywords/types.md).  
  
 En el ejemplo anterior, tanto `i` como `s` son nombres simples que identifican variables locales.  Cuando estas variables se utilizan en una expresión, el nombre de variable se evalúa como el valor almacenado actualmente en la ubicación de la variable en memoria.  Esto se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideStatements#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/expressions_2.cs)]  
  
## Expresiones de invocación  
 En el ejemplo de código siguiente, la llamada a `DoWork` es una expresión de invocación.  
  
```  
DoWork();  
```  
  
 Una invocación de método requiere el nombre del método, ya sea un nombre como en el ejemplo anterior o el resultado de otra expresión, seguido de paréntesis y los parámetros del método.  Para obtener más información, vea [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md).  Una invocación de delegado utiliza el nombre de un delegado y los parámetros de método entre paréntesis.  Para obtener más información, vea [Delegados](../../../csharp/programming-guide/delegates/index.md).  Las invocaciones de método e invocaciones de delegado se evalúan como el valor que devuelve el método, si devuelve alguno.  Los métodos que devuelven un valor nulo no se pueden utilizar en lugar de un valor en una expresión.  
  
## Expresiones de consulta  
 A las expresiones de consulta se les aplican las mismas reglas que a las expresiones en general.  Para obtener más información, consulte [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
## Expresiones lambda  
 Las expresiones lambda representan "métodos insertados" que no tienen nombre pero pueden tener parámetros de entrada y varias instrucciones.  Se utilizan mucho en LINQ para pasar argumentos a métodos.  Las expresiones lambda se compilan en delegados o árboles de expresión, dependiendo del contexto en el que se utilicen.  Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
## Árboles de expresión  
 Los árboles de expresión permiten representar las expresiones como estructuras de datos.  Los proveedores LINQ los utilizan en gran medida para convertir expresiones de consulta en código significativo en otro contexto, como una base de datos SQL.  Para obtener más información, consulte [Árboles de expresión](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Comentarios  
 Siempre que se identifica un acceso a una variable, propiedad de objeto o indizador de objeto desde una expresión, el valor de ese elemento se utiliza como valor de la expresión.  Una expresión se puede colocar en cualquier parte de C\# donde se requiera un valor u objeto, siempre que la expresión finalmente se evalúe como el tipo requerido.  
  
## Capítulo destacado del libro  
 [variables y expresiones](http://go.microsoft.com/fwlink/?LinkId=221228) en [Principio Visual c\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)   
 [Tipos](../../../csharp/programming-guide/types/index.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)