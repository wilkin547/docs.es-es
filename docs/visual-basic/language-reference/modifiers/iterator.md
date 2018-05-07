---
title: Iterador (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 565508046b3fa2dc52acf8c5204153beffc15d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iterator-visual-basic"></a>Iterador (Visual Basic)
Especifica que una función o `Get` descriptor de acceso es un iterador.  
  
## <a name="remarks"></a>Comentarios  
 Un *iterador* realiza una iteración personalizada en una colección. Un iterador utiliza la [producen](../../../visual-basic/language-reference/statements/yield-statement.md) instrucción para devolver cada elemento en la colección a la vez. Cuando un `Yield` se alcanza la instrucción, se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.  
  
 Un iterador se puede implementar como una función o como un `Get` descriptor de acceso de una definición de propiedad. El `Iterator` modificador aparece en la declaración de la función de iterador o `Get` descriptor de acceso.  
  
 Llamar a un iterador de código de cliente mediante un [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 El tipo de valor devuelto de una función de iterador o `Get` descriptor de acceso puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Un iterador no puede tener ningún `ByRef` parámetros.  
  
 Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.  
  
 Un iterador puede ser una función anónima. Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Uso  
 El modificador `Iterator` se puede utilizar en los contextos siguientes:  
  
-   [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una función de iterador. La función de iterador tiene una `Yield` que esté dentro de un [para... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle. Cada iteración de la [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) cuerpo de instrucción en `Main` crea una llamada a la `Power` función del iterador. Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador. El `Iterator` modificador está en la declaración de propiedad.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 Para obtener ejemplos adicionales, vea [iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [Iteradores](../../programming-guide/concepts/iterators.md)  
 [Yield (instrucción)](../../../visual-basic/language-reference/statements/yield-statement.md)
