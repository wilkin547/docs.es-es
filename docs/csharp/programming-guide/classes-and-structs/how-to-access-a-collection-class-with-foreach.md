---
title: "C&#243;mo: Obtener acceso a una clase de colecci&#243;n mediante Foreach (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "clases de colección [C#], foreach (instrucción)"
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# C&#243;mo: Obtener acceso a una clase de colecci&#243;n mediante Foreach (Gu&#237;a de programaci&#243;n de C#)
En el ejemplo de código siguiente se muestra cómo se escribe una clase Collection no genérica que se puede usar con la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  En el ejemplo se define una clase de tokenización de cadenas.  
  
> [!NOTE]
>  Este ejemplo representa la práctica recomendada sólo cuando no se puede utilizar una clase de colección genérica.  Para obtener un ejemplo de cómo se implementa una clase Collection genérica con seguridad de tipos que admita <xref:System.Collections.Generic.IEnumerable%601>, vea [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
 En el ejemplo, el siguiente segmento de código usa la clase `Tokens` para dividir la frase "This is a sample sentence." en tokens usando ' ' y '\-' como separadores.  A continuación, el código muestra esos tokens mediante una instrucción `foreach`.  
  
 [!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## Ejemplo  
 Internamente, la clase `Tokens` usa una matriz para almacenar los tokens.  Como las matrices implementan las interfaces <xref:System.Collections.IEnumerator> e <xref:System.Collections.IEnumerable>, el ejemplo de código podría haber usado los métodos de enumeración de la matriz \(<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> y <xref:System.Collections.IEnumerator.Current%2A>\) en lugar de definirlos en la clase `Tokens`.  Las definiciones de los métodos se incluyen en el ejemplo para clarificar cómo están definidos y qué hace cada uno.  
  
 [!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 En C\#, no es necesario que una clase Collection implemente <xref:System.Collections.IEnumerable> y <xref:System.Collections.IEnumerator> para que sea compatible con `foreach`.  Si la clase tiene los miembros <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>y <xref:System.Collections.IEnumerator.Current%2A> necesarios, funcionará con `foreach`.  Omitir las interfaces tiene la ventaja de que permite definir un tipo de valor devuelto de `Current` que es más específico que <xref:System.Object>.  Esto proporciona seguridad de tipos.  
  
 Por ejemplo, cambie las siguientes líneas del ejemplo anterior.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Dado que `Current` devuelve una cadena, el compilador puede detectar cuándo se usa un tipo incompatible en una instrucción `foreach`, tal y como se muestra en el código siguiente.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 El inconveniente de omitir <xref:System.Collections.IEnumerable> e <xref:System.Collections.IEnumerator> es que la clase Collection ya no puede interactuar con las instrucciones `foreach` \(o equivalentes\) de otros lenguajes compatibles con Common Language Runtime.  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Matrices](../../../csharp/programming-guide/arrays/index.md)   
 [Colecciones](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)