---
title: IsNot (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.isnot
helpviewer_keywords: IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isnot-operator-visual-basic"></a>IsNot (Operador) (Visual Basic)
Compara dos variables de referencia de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Valor `Boolean`.  
  
 `object1`  
 Obligatorio. Cualquier `Object` variable o expresión.  
  
 `object2`  
 Obligatorio. Cualquier `Object` variable o expresión.  
  
## <a name="remarks"></a>Comentarios  
 El `IsNot` operador determina si dos referencias de objeto hacen referencia a objetos diferentes. Sin embargo, no realiza las comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la misma instancia objeto exacta, `result` es `False`; si no lo hacen, `result` es `True`.  
  
 `IsNot`es el opuesto de la `Is` operador. La ventaja de `IsNot` es que puede evitar sintaxis extraña con `Not` y `Is`, que puede ser difícil de leer.  
  
 Puede usar el `Is` y `IsNot` operadores a los objetos de tiempo de compilación y en tiempo de ejecución de prueba.  
  
> [!NOTE]
>  El `IsNot` no se puede usar el operador para comparar expresiones devueltas desde el `TypeOf` operador. En su lugar, debe utilizar el `Not` y `Is` operadores.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se utiliza la `Is` operador y el `IsNot` operador que se va a realizar la comparación de la misma.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)  
 [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Comprobar si dos objetos son iguales](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
