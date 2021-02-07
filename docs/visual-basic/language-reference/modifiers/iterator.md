---
description: 'Más información acerca de: iterator (Visual Basic)'
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 7a3329ba23a3f2487343b332f3bb9c4b19c36496
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730530"
---
# <a name="iterator-visual-basic"></a>Iterador (Visual Basic)

Especifica que una función o un `Get` descriptor de acceso es un iterador.  
  
## <a name="remarks"></a>Observaciones  

 Un *iterador* realiza una iteración personalizada en una colección. Un iterador usa la instrucción [yield](../statements/yield-statement.md) para devolver cada elemento de la colección de uno en uno. Cuando `Yield` se alcanza una instrucción, se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.  
  
 Un iterador se puede implementar como una función o como un `Get` descriptor de acceso de una definición de propiedad. El `Iterator` modificador aparece en la declaración de la función de iterador o el `Get` descriptor de acceso.  
  
 Se llama a un iterador desde el código de cliente mediante un método [for each... Instrucción siguiente](../statements/for-each-next-statement.md).  
  
 El tipo de valor devuelto de una función de iterador o `Get` descriptor de acceso puede ser <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> .  
  
 Un iterador no puede tener ningún `ByRef` parámetro.  
  
 Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.  
  
 Un iterador puede ser una función anónima. Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Uso  

 El modificador `Iterator` se puede utilizar en los contextos siguientes:  
  
- [Instrucción Function](../statements/function-statement.md)  
  
- [Property Statement](../statements/property-statement.md)  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra una función de iterador. La función de iterador tiene una `Yield` instrucción que está dentro de un [... Siguiente](../statements/for-next-statement.md) bucle. Cada iteración del cuerpo de la instrucción [for each](../statements/for-each-next-statement.md) en `Main` crea una llamada a la `Power` función de iterador. Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador. El `Iterator` modificador está en la declaración de propiedad.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Para obtener más ejemplos, vea [iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Iteradores](../../programming-guide/concepts/iterators.md)
- [Instrucción Yield](../statements/yield-statement.md)
