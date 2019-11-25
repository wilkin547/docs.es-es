---
title: Operador TypeOf
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
ms.openlocfilehash: 22af5b8f8488ca44e388596530decd52e33525dc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350893"
---
# <a name="typeof-operator-visual-basic"></a>TypeOf (Operador, Visual Basic)
Checks whether the runtime type of an expression's result is type-compatible with the specified type.
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Devuelto. Valor `Boolean`.  
  
 `objectexpression`  
 Requerido. Cualquier expresión que se evalúa como un tipo de referencia.  
  
 `typename`  
 Requerido. Cualquier nombre de tipo de datos.  
  
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
- [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
