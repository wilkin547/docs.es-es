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
ms.openlocfilehash: 0cce36073b53442bce63f966f3bd94bd5d70d2a8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406332"
---
# <a name="typeof-operator-visual-basic"></a>TypeOf (Operador, Visual Basic)
Comprueba si el tipo en tiempo de ejecución del resultado de una expresión es compatible con el tipo especificado.
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a>Partes  
 `result`  
 Devuelto. Valor `Boolean`.  
  
 `objectexpression`  
 Necesario. Cualquier expresión que se evalúa como un tipo de referencia.  
  
 `typename`  
 Necesario. Cualquier nombre de tipo de datos.  
  
## <a name="remarks"></a>Observaciones  
 El operador `TypeOf` determina si el tipo en tiempo de ejecución de `objectexpression` es compatible con `typename`. La compatibilidad depende de la categoría del tipo de `typename`. En la tabla siguiente se muestra cómo se determina la compatibilidad.  
  
|Categoría de tipo de `typename`|Criterio de compatibilidad|  
|---------------------------------|-----------------------------|  
|Class|`objectexpression` es de tipo `typename` o hereda de `typename`|  
|Estructura|`objectexpression` es de tipo `typename`|  
|Interfaz|`objectexpression` implementa `typename` o hereda de una clase que implementa `typename`|  
  
 Si el tipo en tiempo de ejecución de `objectexpression` satisface el criterio de compatibilidad, `result` es `True`. En caso contrario, `result` es `False`.  Si `objectexpression` es null, entonces `TypeOf`...`Is` devuelve `False` y ...`IsNot` devuelve `True`.  
  
 `TypeOf` siempre se usa con la palabra clave `Is` para construir una expresión `TypeOf`...`Is`, o con la palabra clave `IsNot` para construir una expresión `TypeOf`...`IsNot`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan expresiones `TypeOf`...`Is` para probar la compatibilidad de tipo de dos variables de referencia de objeto con diversos tipos de datos.  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 La variable `refInteger` tiene un tipo en tiempo de ejecución de `Integer`. Es compatible con `Integer` pero no con `Double`. La variable `refForm` tiene un tipo en tiempo de ejecución de <xref:System.Windows.Forms.Form>. Es compatible con <xref:System.Windows.Forms.Form> porque es su tipo, con <xref:System.Windows.Forms.Control> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.Windows.Forms.Control>, y con <xref:System.ComponentModel.IComponent> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.ComponentModel.Component>, que implementa <xref:System.ComponentModel.IComponent>. Sin embargo, `refForm` no es compatible con <xref:System.Windows.Forms.Label>.  
  
## <a name="see-also"></a>Consulte también

- [Operador is](is-operator.md)
- [Operador IsNot](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores y expresiones](../../programming-guide/language-features/operators-and-expressions/index.md)
