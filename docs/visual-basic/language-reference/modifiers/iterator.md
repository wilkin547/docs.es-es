---
title: Iterador
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 9d7eaf186bae544031487ce027505e1e0d4ae0f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351521"
---
# <a name="iterator-visual-basic"></a>Iterador (Visual Basic)
Especifica que una función o un descriptor de acceso `Get` es un iterador.  
  
## <a name="remarks"></a>Comentarios  
 Un *iterador* realiza una iteración personalizada en una colección. Un iterador usa la instrucción [yield](../../../visual-basic/language-reference/statements/yield-statement.md) para devolver cada elemento de la colección de uno en uno. Cuando se alcanza una instrucción `Yield`, se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.  
  
 Un iterador se puede implementar como una función o como `Get` descriptor de acceso de una definición de propiedad. El modificador `Iterator` aparece en la declaración de la función de iterador o de `Get` descriptor de acceso.  
  
 Se llama a un iterador desde el código de cliente mediante un método [for each... Instrucción siguiente](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 El tipo de valor devuelto de una función de iterador o `Get` descriptor de acceso puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Un iterador no puede tener ningún parámetro `ByRef`.  
  
 Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.  
  
 Un iterador puede ser una función anónima. Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Uso  
 El modificador `Iterator` se puede utilizar en los contextos siguientes:  
  
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una función de iterador. La función de iterador tiene una instrucción `Yield` que está dentro de un [... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle. Cada iteración del cuerpo de la instrucción [for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) en `Main` crea una llamada a la función de iterador `Power`. Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador. El modificador `Iterator` está en la declaración de propiedad.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Para obtener más ejemplos, vea [iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Iteradores](../../programming-guide/concepts/iterators.md)
- [Yield (instrucción)](../../../visual-basic/language-reference/statements/yield-statement.md)
