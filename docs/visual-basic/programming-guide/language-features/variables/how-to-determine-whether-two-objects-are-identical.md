---
title: 'Cómo: Determinar si dos objetos son idénticos'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 5deebd4ffc5b277c94f5ae36c00fd6e5010a1551
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348599"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Cómo: Determinar si dos objetos son idénticos (Visual Basic)
En Visual Basic, dos referencias a variables se consideran idénticas si sus punteros son iguales, es decir, si ambas variables apuntan a la misma instancia de clase en la memoria. Por ejemplo, en una aplicación Windows Forms, es posible que desee realizar una comparación para determinar si la instancia actual (`Me`) es la misma que una instancia determinada, como `Form2`.  
  
 Visual Basic proporciona dos operadores para comparar los punteros. El [operador is](../../../../visual-basic/language-reference/operators/is-operator.md) devuelve `True` si los objetos son idénticos, y el [operador IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) devuelve `True` si no lo son.  
  
## <a name="determining-if-two-objects-are-identical"></a>Determinar si dos objetos son idénticos  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Para determinar si dos objetos son idénticos  
  
1. Configure una expresión `Boolean` para probar los dos objetos.  
  
2. En la expresión de prueba, utilice el operador `Is` con los dos objetos como operandos.  
  
     `Is` devuelve `True` si los objetos apuntan a la misma instancia de clase.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Determinar si dos objetos no son idénticos  
 A veces, desea realizar una acción si los dos objetos no son idénticos y puede resultar difícil combinar `Not` y `Is`, por ejemplo `If Not obj1 Is obj2`. En tal caso, puede usar el operador `IsNot`.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Para determinar si dos objetos no son idénticos  
  
1. Configure una expresión `Boolean` para probar los dos objetos.  
  
2. En la expresión de prueba, utilice el operador `IsNot` con los dos objetos como operandos.  
  
     `IsNot` devuelve `True` si los objetos no señalan a la misma instancia de clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se prueban pares de variables de `Object` para ver si señalan a la misma instancia de clase.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 En el ejemplo anterior se muestra el siguiente resultado.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Vea también

- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Is (operador)](../../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Determinar si dos objetos están relacionados](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
