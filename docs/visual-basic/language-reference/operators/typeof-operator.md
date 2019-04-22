---
title: TypeOf (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 7162fcc24595bbb16d268d5d9e1ea4d82f6e67fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829868"
---
# <a name="typeof-operator-visual-basic"></a>TypeOf (Operador, Visual Basic)
Compara una variable de referencia de objeto a un tipo de datos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = TypeOf objectexpression Is typename  
```  
  
```  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Devuelto. Valor `Boolean`.  
  
 `objectexpression`  
 Obligatorio. Cualquier expresión que se evalúa como un tipo de referencia.  
  
 `typename`  
 Obligatorio. Cualquier nombre de tipo de datos.  
  
## <a name="remarks"></a>Comentarios  
 El operador `TypeOf` determina si el tipo en tiempo de ejecución de `objectexpression` es compatible con `typename`. La compatibilidad depende de la categoría del tipo de `typename`. En la tabla siguiente se muestra cómo se determina la compatibilidad.  
  
|Categoría de tipo de `typename`|Criterio de compatibilidad|  
|---------------------------------|-----------------------------|  
|Clase|`objectexpression` es de tipo `typename` o hereda de `typename`|  
|Estructura|`objectexpression` es de tipo `typename`|  
|Interfaz|`objectexpression` implementa `typename` o hereda de una clase que implementa `typename`|  
  
 Si el tipo en tiempo de ejecución de `objectexpression` satisface el criterio de compatibilidad, `result` es `True`. En caso contrario, `result` es `False`.  Si `objectexpression` es null, entonces `TypeOf`...`Is` devuelve `False` y ...`IsNot` devuelve `True`.  
  
 `TypeOf` siempre se usa con la palabra clave `Is` para construir una expresión `TypeOf`...`Is`, o con la palabra clave `IsNot` para construir una expresión `TypeOf`...`IsNot`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan expresiones `TypeOf`...`Is` para probar la compatibilidad de tipo de dos variables de referencia de objeto con diversos tipos de datos.  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 La variable `refInteger` tiene un tipo en tiempo de ejecución de `Integer`. Es compatible con `Integer` pero no con `Double`. La variable `refForm` tiene un tipo en tiempo de ejecución de <xref:System.Windows.Forms.Form>. Es compatible con <xref:System.Windows.Forms.Form> porque es su tipo, con <xref:System.Windows.Forms.Control> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.Windows.Forms.Control>, y con <xref:System.ComponentModel.IComponent> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.ComponentModel.Component>, que implementa <xref:System.ComponentModel.IComponent>. Sin embargo, `refForm` no es compatible con <xref:System.Windows.Forms.Label>.  
  
## <a name="see-also"></a>Vea también

- [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
