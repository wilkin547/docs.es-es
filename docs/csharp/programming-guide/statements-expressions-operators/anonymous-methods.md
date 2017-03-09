---
title: "M&#233;todos an&#243;nimos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "métodos anónimos [C#]"
  - "delegados [C#], métodos anónimos"
  - "métodos [C#], anónimos"
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# M&#233;todos an&#243;nimos (Gu&#237;a de programaci&#243;n de C#)
En versiones de C\# anteriores a la versión 2.0, la única manera de declarar un [delegado](../../../csharp/language-reference/keywords/delegate.md) era utilizar [métodos con nombre](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).  C\# 2.0 introdujo los métodos anónimos, mientras que, en C\# 3.0 y versiones posteriores, las expresiones lambda reemplazan a los métodos anónimos como la manera preferente de escribir código insertado.  No obstante, la información sobre los métodos anónimos de este tema también se aplica a las expresiones lambda.  Hay un caso en el que un método anónimo proporciona una funcionalidad que no se encuentra en las expresiones lambda.  Los métodos anónimos permiten omitir la lista de parámetros.  Esto significa que los métodos anónimos pueden convertirse en delegados con diversas firmas.  Esto no es posible con expresiones lambda.  Para obtener más información sobre las expresiones lambda, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 La creación de métodos anónimos es básicamente una forma de pasar un bloque de código como parámetro de delegado.  A continuación se describen dos ejemplos de esto:  
  
 [!code-cs[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#6)]  
  
 [!code-cs[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#5)]  
  
 Mediante los métodos anónimos, se reduce la sobrecarga de codificación a la hora de crear instancias de delegados, ya que no es necesario crear un método independiente.  
  
 Por ejemplo, especificar un bloque de código en vez de un delegado puede ser útil en el caso de que la creación de un método pueda suponer una sobrecarga innecesaria.  Un buen ejemplo es cuando se inicia un nuevo subproceso.  Esta clase crea un subproceso y también contiene el código que el subproceso ejecuta sin crear un método adicional para el delegado.  
  
 [!code-cs[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#7)]  
  
## Comentarios  
 El ámbito de los parámetros de un método anónimo es el *bloque del método anónimo*.  
  
 Es un error utilizar una instrucción de salto, como [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) o [continue](../../../csharp/language-reference/keywords/continue.md), en un bloque de método anónimo si el destino está fuera del bloque.  También es un error utilizar una instrucción de salto, como `goto`, `break` o `continue`, fuera de un bloque de método anónimo si el destino está dentro del bloque.  
  
 Las variables locales y los parámetros cuyo ámbito contiene una declaración de método anónimo se denominan variables *externas* del método anónimo.  Por ejemplo, en el segmento de código siguiente, `n` es una variable externa:  
  
 [!code-cs[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#8)]  
  
 Una referencia a la variable externa `n` se dice que es  *capturado* cuando se crea el delegado.  A diferencia de las variables locales, la duración de una variable capturada se extiende hasta que los delegados que hacen referencia a los métodos anónimos son elegibles para la recolección.  
  
 Un método anónimo no puede tener acceso a los parámetros [ref](../../../csharp/language-reference/keywords/ref.md) u [out](../../../csharp/language-reference/keywords/out.md) de un ámbito externo.  
  
 No se puede obtener acceso a código no seguro dentro del *bloque de método anónimo*.  
  
 No se permite el uso de métodos anónimos en el lado izquierdo del operador [is](../../../csharp/language-reference/keywords/is.md).  
  
## Ejemplo  
 El ejemplo siguiente muestra las dos maneras de crear instancias de un delegado:  
  
-   Asociar el delegado a un método anónimo.  
  
-   Asociar el delegado a un método con nombre \(`DoWork`\).  
  
 En cada uno de los casos, se muestra un mensaje cuando se invoca al delegado.  
  
 [!code-cs[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#4)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Delegados con métodos con nombre y delegados con métodos anónimos](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)