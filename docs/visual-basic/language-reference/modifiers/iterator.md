---
title: "Iterador (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Iterator"
helpviewer_keywords: 
  - "Iterator (palabra clave) [Visual Basic]"
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Iterador (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que una función o un descriptor de `Get` es un iterador.  
  
## Comentarios  
 *Un iterador* realiza una iteración personalizada en una colección.  Un iterador utiliza la instrucción de [producción](../../../visual-basic/language-reference/statements/yield-statement.md) para devolver todos los elementos de la colección de uno en uno.  Cuando se alcanza una instrucción de `Yield` , la ubicación actual en el código se conserva.  La ejecución se reinicia desde esa ubicación la próxima vez que la función de iterador se denomina.  
  
 Un iterador se puede implementar como función o como descriptor de `Get` de una definición de propiedad.  El modificador de `Iterator` aparece en la declaración de la función de iterador o de descriptor de acceso `Get` .  
  
 Se llama a un iterador de código de cliente mediante [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Tipo de valor devuelto de una función de iterador o el descriptor de `Get` puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Un iterador no puede tener ningún parámetro de `ByRef` .  
  
 Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático, o destructor estático.  
  
 Un iterador puede ser una función anónima.  Para obtener más información, vea [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Para obtener más información sobre los iteradores, vea [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Uso  
 El modificador `Iterator` se puede utilizar en estos contextos:  
  
-   [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## Ejemplo  
 El ejemplo siguiente se muestra una función de iterador.  La función de iterador tiene una instrucción de `Yield` que está dentro de un bucle de [For… Next](../../../visual-basic/language-reference/statements/for-next-statement.md) .  Cada iteración del cuerpo de instrucción de [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) en `Main` crea una llamada a la función de iterador de `Power` .  Cada llamada a la función de iterador continúa a la ejecución siguiente de la instrucción de `Yield` , que durante la siguiente iteración del bucle de `For…Next` .  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## Ejemplo  
 El ejemplo siguiente se muestra un descriptor de acceso de `Get` que sea un iterador.  El modificador de `Iterator` está en la declaración de propiedad.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 Para obtener otros ejemplos, vea [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Vea también  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>   
 [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Yield \(Instrucción\)](../../../visual-basic/language-reference/statements/yield-statement.md)