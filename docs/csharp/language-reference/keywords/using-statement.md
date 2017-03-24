---
title: "using (Instrucci&#243;n, Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "using (instrucción) [C#]"
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# using (Instrucci&#243;n, Referencia de C#)
Proporciona una sintaxis adecuada que garantiza el uso correcto de los objetos <xref:System.IDisposable>.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar la instrucción using.  
  
 [!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## Comentarios  
 <xref:System.IO.File> y <xref:System.Drawing.Font> son ejemplos de tipos administrados que obtienen acceso a recursos no administrados \(en este caso, identificadores de archivo y contextos de dispositivo\).  Existen muchos más tipos de recursos no administrados y tipos de biblioteca de clases que los encapsulan.  Todos estos tipos deben implementar la interfaz <xref:System.IDisposable>.  
  
 Como norma, cuando utilice un objeto `IDisposable`, declárelo y cree instancias del mismo en una instrucción `using`.  La instrucción `using` llama al método <xref:System.IDisposable.Dispose%2A> en el objeto de la forma correcta y, si se utiliza tal y como se ha explicado anteriormente, también hace que el propio objeto salga del ámbito en cuanto se llama a <xref:System.IDisposable.Dispose%2A>.  Dentro del bloque `using`, el objeto es de sólo lectura y no puede modificarse ni reasignarse.  
  
 La instrucción `using` garantiza que se llame a <xref:System.IDisposable.Dispose%2A>, aunque se produzca una excepción mientras se llama a los métodos del objeto.  Puede conseguir el mismo resultado colocando el objeto dentro de un bloque try y llamando a continuación a <xref:System.IDisposable.Dispose%2A> en un bloque finally; de hecho, esta es la forma en que el compilador traduce la instrucción `using`.  El ejemplo de código anterior se extiende al siguiente código en tiempo de compilación \(tenga en cuenta las llaves adicionales para crear el ámbito limitado del objeto\):  
  
 [!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 Se pueden declarar varias instancias de un tipo en una instrucción `using`, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 Puede crear instancias del objeto de recursos y, a continuación, pasar la variable a la instrucción `using`, pero no es un procedimiento recomendado.  En este caso, el objeto permanece en el ámbito después de que el control abandone el bloque `using`, aunque es probable que ya no tenga acceso a sus recursos no administrados.  En otras palabras, ya no se inicializará completamente.  Si intenta utilizar el objeto fuera del bloque `using`, se arriesga a que se inicie una excepción.  Por esta razón, suele ser mejor crear instancias del objeto en la instrucción `using` y limitar su ámbito al bloque `using`.  
  
 [!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [using \(directiva\)](../../../csharp/language-reference/keywords/using-directive.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)   
 [Implementing a Dispose Method](../Topic/Implementing%20a%20Dispose%20Method.md)