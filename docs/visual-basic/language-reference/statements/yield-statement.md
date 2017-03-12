---
title: "Yield (Instrucci&#243;n) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Yield"
helpviewer_keywords: 
  - "iteradores, instrucción Yield [Visual Basic]"
  - "iteradores [Visual Basic]"
  - "Yield (instrucción) [Visual Basic]"
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Yield (Instrucci&#243;n) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Envía el siguiente elemento de una colección a una instrucción de `For Each...Next`.  
  
## Sintaxis  
  
```  
Yield expression  
```  
  
#### Parámetros  
  
|||  
|-|-|  
|Término|Definición|  
|`expression`|Requerido.  Una expresión que es implícitamente convertible al tipo de función de iterador o de descriptor de acceso `Get` que contiene la instrucción de `Yield`.|  
  
## Comentarios  
 La instrucción de `Yield` devuelve un elemento de una colección al mismo tiempo.  La instrucción de `Yield` se incluye en una función de iterador o un descriptor de acceso de `Get`, que realizan iteraciones personalizadas en una colección.  
  
 Se utiliza una función de iterador mediante [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o una consulta LINQ.  Cada iteración del bucle de `For Each` llama a la función de iterador.  Cuando una instrucción de `Yield` se consigue en la función de iterador, se devuelve `expression`, y la ubicación actual en el código se conserva.  La ejecución se reinicia desde esa ubicación la próxima vez que la función de iterador se denomina.  
  
 Una conversión implícita debe existir del tipo de `expression` en la instrucción de `Yield` el tipo de valor devuelto del iterador.  
  
 Puede utilizar una instrucción de `Exit Function` o de `Return` para finalizar la iteración.  
  
 La “producción” no es una palabra reservada y tiene un significado especial únicamente cuando se utiliza en una función de `Iterator` o un descriptor de acceso de `Get`.  
  
 Para obtener más información sobre las funciones de iterador y los descriptores de `Get`, vea [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Las funciones de iterador y los descriptores de acceso  
 La declaración de una función de iterador o un descriptor de `Get` debe cumplir los requisitos siguientes:  
  
-   Debe incluir un modificador de [Iterador](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   El tipo de valor devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.  
  
-   No puede tener ningún parámetro de `ByRef`.  
  
 Una función de iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático, o destructor estático.  
  
 Una función de iterador puede ser una función anónima.  Para obtener más información, vea [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Control de excepciones  
 Una instrucción de `Yield` puede estar dentro de un bloque de `Try` de [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  Un bloque `Try` que tenga una instrucción `Yield` puede tener bloques `Catch` y un bloque `Finally`.  
  
 Una instrucción `Yield` no puede estar dentro de un bloque `Catch` o `Finally`.  
  
 Si el cuerpo de `For Each` \(fuera de la función de iterador\) produce una excepción, un bloque de `Catch` en la función de iterador no se ejecuta, pero un bloque de `Finally` en la función de iterador se ejecuta.  Un bloque `Catch` dentro de una función iteradora detecta las excepciones que se producen dentro de la función iteradora.  
  
## Implementación técnica  
 El código siguiente devuelve `IEnumerable (Of String)` de una función de iterador a continuación recorre en iteración los elementos de `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 La llamada a `MyIteratorFunction` no se ejecuta el cuerpo de la función.  En su lugar la llamada devuelve `IEnumerable(Of String)` en la variable de `elements`.  
  
 En una iteración del bucle de `For Each`, el método de <xref:System.Collections.IEnumerator.MoveNext%2A> se llama para `elements`.  Esta llamada se ejecuta el cuerpo de `MyIteratorFunction` hasta que se alcanza la siguiente instrucción de `Yield`.  La instrucción de `Yield` devuelve una expresión que determina no solo el valor de la variable de `element` para el consumo del cuerpo del bucle pero también la propiedad de <xref:System.Collections.Generic.IEnumerator%601.Current%2A> de elementos, que es `IEnumerable (Of String)`.  
  
 En cada iteración del bucle de `For Each`, la ejecución del cuerpo de iterador continúa de donde se quedó, de nuevo deteniéndose cuando llega a una instrucción de `Yield`.  El bucle de `For Each` completa al final de la función de iterador o una instrucción de `Return` o de `Exit Function` se alcance.  
  
## Ejemplo  
 El ejemplo siguiente tiene una instrucción de `Yield` que está dentro de un bucle de [For… Next](../../../visual-basic/language-reference/statements/for-next-statement.md).  Cada iteración del cuerpo de instrucción de [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) en `Main` crea una llamada a la función de iterador de `Power`.  Cada llamada a la función de iterador continúa a la ejecución siguiente de la instrucción de `Yield`, que durante la siguiente iteración del bucle de `For…Next`.  
  
 El tipo de valor devuelto del método de iterador es <xref:System.Collections.Generic.IEnumerable%601>, tipo de interfaz del iterador.  Cuando se llama al método de iterador, devuelve un objeto enumerable que contiene los potencias de un número.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/yield-statement_1.vb)]  
  
## Ejemplo  
 El ejemplo siguiente se muestra un descriptor de acceso de `Get` que sea un iterador.  La declaración de propiedad incluye un modificador de `Iterator`.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/yield-statement_2.vb)]  
  
 Para obtener otros ejemplos, vea [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Requisitos  
 [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs-dev11-long-md.md)]  
  
## Vea también  
 [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Instrucciones](../../../visual-basic/language-reference/statements/index.md)