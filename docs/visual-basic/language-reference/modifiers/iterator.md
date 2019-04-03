---
title: Iterador (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 499949d1f4c20e1f465355bd076ba39f1496779b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822705"
---
# <a name="iterator-visual-basic"></a>Iterador (Visual Basic)
Especifica que una función o `Get` descriptor de acceso es un iterador.  
  
## <a name="remarks"></a>Comentarios  
 Un *iterador* realiza una iteración personalizada en una colección. Un iterador usa la [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) instrucción para devolver cada elemento de la colección a la vez. Cuando un `Yield` se alcanza la instrucción, se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.  
  
 Un iterador se puede implementar como una función o como un `Get` descriptor de acceso de una definición de propiedad. El `Iterator` modificador aparece en la declaración de la función de iterador o `Get` descriptor de acceso.  
  
 Llamar a un iterador desde código de cliente mediante un [For Each... Instrucción Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 El tipo de valor devuelto de una función de iterador o `Get` descriptor de acceso puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Un iterador no puede tener ninguno `ByRef` parámetros.  
  
 Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.  
  
 Un iterador puede ser una función anónima. Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Uso  
 El modificador `Iterator` se puede utilizar en los contextos siguientes:  
  
-   [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra una función de iterador. La función de iterador tiene una `Yield` instrucción que está dentro de un [para... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle. Cada iteración de la [para cada](../../../visual-basic/language-reference/statements/for-each-next-statement.md) cuerpo de instrucción en `Main` crea una llamada a la `Power` función de iterador. Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador. El `Iterator` modificador está en la declaración de propiedad.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Para obtener ejemplos adicionales, consulte [iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Iteradores](../../programming-guide/concepts/iterators.md)
- [Yield (instrucción)](../../../visual-basic/language-reference/statements/yield-statement.md)
