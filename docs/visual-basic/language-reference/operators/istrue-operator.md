---
title: IsTrue (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: cb8ad8cb4a1ec13611edfcc3de7f4b7eb33fc553
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829933"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue (Operador) (Visual Basic)
Determina si una expresión es `True`.  
  
 No se puede llamar a `IsTrue` explícitamente en el código, pero el de Visual Basic compilador puede usar para generar código desde `OrElse` cláusulas. Si se define una clase o estructura y, a continuación, utilizar una variable de ese tipo en un `OrElse` cláusula, debe definir `IsTrue` en esa clase o estructura.  
  
 El compilador considera que el `IsTrue` y `IsFalse` operadores como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
## <a name="compiler-use-of-istrue"></a>Uso del compilador de IsTrue  
 Cuando haya definido una clase o estructura, puede usar una variable de ese tipo en un `For`, `If`, `Else If`, o `While` instrucción, o en un `When` cláusula. Si lo hace, el compilador requiere un operador que convierte su tipo en un `Boolean` para que pueda probar una condición de valor. Busca un operador adecuado en el orden siguiente:  
  
1.  Un operador de conversión de ampliación de la clase o estructura a `Boolean`.  
  
2.  Un operador de conversión de ampliación de la clase o estructura a `Boolean?`.  
  
3.  El `IsTrue` operador en la clase o estructura.  
  
4.  Una conversión de restricción a `Boolean?` que no implica una conversión de `Boolean` a `Boolean?`.  
  
5.  Un operador de conversión de restricción de la clase o estructura a `Boolean`.  
  
 Si no ha definido ninguna conversión a `Boolean` o un `IsTrue` operador, el compilador señala un error.  
  
> [!NOTE]
>  El `IsTrue` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para el `IsFalse` y `IsTrue` operadores.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vea también

- [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md)
