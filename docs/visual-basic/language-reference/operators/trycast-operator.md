---
title: TryCast (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: d8825b8eee35ea514d4001a6a5c1cc5139c67454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600155"
---
# <a name="trycast-operator-visual-basic"></a>TryCast (Operador) (Visual Basic)
Introduce una operación de conversión de tipos que no produce una excepción.  
  
## <a name="remarks"></a>Comentarios  
 Si se produce un error en un intento de conversión, `CType` y `DirectCast` ambos producen un <xref:System.InvalidCastException> error. Esto puede afectar negativamente al rendimiento de la aplicación. `TryCast` Devuelve [nada](../../../visual-basic/language-reference/nothing.md), de modo que en lugar de tener que controlar una posible excepción, solo necesita comprobar el resultado devuelto con `Nothing`.  
  
 Usa el `TryCast` palabra clave de la misma forma que usa el [CType (función)](../../../visual-basic/language-reference/functions/ctype-function.md) y [DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) (palabra clave). Proporcione una expresión como el primer argumento y un tipo para convertir como segundo argumento. `TryCast` sólo funciona en tipos de referencia, como clases e interfaces. Requiere una relación de herencia o implementación entre los dos tipos. Esto significa que un tipo debe heredar de o implementar la otra.  
  
## <a name="errors-and-failures"></a>Errores y errores  
 `TryCast` genera un error del compilador si detecta que no existe ninguna relación de herencia o implementación. Pero la falta de un error del compilador no garantiza una conversión correcta. Si la conversión deseada es de restricción, podría producirse un error en tiempo de ejecución. Si esto ocurre, `TryCast` devuelve [nada](../../../visual-basic/language-reference/nothing.md).  
  
## <a name="conversion-keywords"></a>Palabras clave para conversiones  
 Una comparación de las palabras clave de conversión de tipo es como sigue.  
  
|Palabra clave|Tipos de datos|Relación de argumentos|Error de tiempo de ejecución|  
|---|---|---|---|  
|[Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Los tipos de datos|De ampliación o conversión de restricción se debe definir entre los dos tipos de datos|Produce <xref:System.InvalidCastException>|  
|[DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md)|Los tipos de datos|Un tipo debe heredar de tipo ni lo implementa otro|Produce <xref:System.InvalidCastException>|  
|`TryCast`|Solo los tipos de referencia|Un tipo debe heredar de tipo ni lo implementa otro|Devuelve [nada](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
