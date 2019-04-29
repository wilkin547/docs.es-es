---
title: Procedimiento Determinar si dos objetos son idénticos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: aae053ae0473ed6ced0f28da3d5e5afc0be629df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769088"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Procedimiento Determinar si dos objetos son idénticos (Visual Basic)
En Visual Basic, dos referencias de variables se consideran idénticas si sus punteros son iguales, es decir, si ambas variables señalan a la misma instancia de clase en la memoria. Por ejemplo, en una aplicación Windows Forms, es posible que desee realizar una comparación para determinar si la instancia actual (`Me`) es el mismo que una instancia concreta, como `Form2`.  
  
 Visual Basic proporciona dos operadores para comparar los punteros. El [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) devuelve `True` si los objetos son idénticos y el [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md) devuelve `True` si no lo son.  
  
## <a name="determining-if-two-objects-are-identical"></a>Determinar si dos objetos son idénticos  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Para determinar si dos objetos son idénticos  
  
1. Configurar un `Boolean` expresión para probar los dos objetos.  
  
2. En la expresión de prueba, use el `Is` operador con los dos objetos como operandos.  
  
     `Is` Devuelve `True` si los objetos de punto a la misma instancia de clase.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Determinar si dos objetos no son idénticos  
 A veces desea realizar una acción si los dos objetos no son idénticos, y puede ser difícil combinar `Not` y `Is`, por ejemplo `If Not obj1 Is obj2`. En tal caso puede usar el `IsNot` operador.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Para determinar si dos objetos no son idénticos  
  
1. Configurar un `Boolean` expresión para probar los dos objetos.  
  
2. En la expresión de prueba, use el `IsNot` operador con los dos objetos como operandos.  
  
     `IsNot` Devuelve `True` si los objetos no señalan a la misma instancia de clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se prueba pares de `Object` variables para ver si señalan a la misma instancia de clase.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 El ejemplo anterior muestra el siguiente resultado.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Vea también

- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Is (operador)](../../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Cómo: Determinar si dos objetos están relacionados](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
