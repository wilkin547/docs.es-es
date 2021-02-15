---
description: 'Más información acerca de cómo: determinar si dos objetos son idénticos (Visual Basic)'
title: Procedimiento para determinar si dos objetos son idénticos
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 91f431b5a7e4cf51135c060ca0aebf1b3b968b25
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481901"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Cómo: Determinar si dos objetos son idénticos (Visual Basic)

En Visual Basic, dos referencias a variables se consideran idénticas si sus punteros son iguales, es decir, si ambas variables apuntan a la misma instancia de clase en la memoria. Por ejemplo, en una aplicación Windows Forms, es posible que desee realizar una comparación para determinar si la instancia actual ( `Me` ) es la misma que una instancia determinada, como `Form2` .  
  
 Visual Basic proporciona dos operadores para comparar los punteros. El [operador is](../../../language-reference/operators/is-operator.md) devuelve `True` si los objetos son idénticos y el [Operador IsNot](../../../language-reference/operators/isnot-operator.md) devuelve `True` si no lo son.  
  
## <a name="determining-if-two-objects-are-identical"></a>Determinar si dos objetos son idénticos  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Para determinar si dos objetos son idénticos  
  
1. Configure una `Boolean` expresión para probar los dos objetos.  
  
2. En la expresión de prueba, utilice el `Is` operador con los dos objetos como operandos.  
  
     `Is` Devuelve `True` si los objetos apuntan a la misma instancia de clase.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Determinar si dos objetos no son idénticos  

 A veces, desea realizar una acción si los dos objetos no son idénticos y puede resultar complicado combinar `Not` y `Is` , por ejemplo `If Not obj1 Is obj2` . En tal caso, puede usar el `IsNot` operador.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Para determinar si dos objetos no son idénticos  
  
1. Configure una `Boolean` expresión para probar los dos objetos.  
  
2. En la expresión de prueba, utilice el `IsNot` operador con los dos objetos como operandos.  
  
     `IsNot` Devuelve `True` si los objetos no señalan a la misma instancia de clase.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se prueban pares de `Object` variables para ver si señalan a la misma instancia de clase.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 En el ejemplo anterior se muestra el siguiente resultado.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Consulte también

- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Variables de objeto](object-variables.md)
- [Valores de las variables de objeto](object-variable-values.md)
- [Operador Is](../../../language-reference/operators/is-operator.md)
- [Operador IsNot](../../../language-reference/operators/isnot-operator.md)
- [Procedimiento para determinar si dos objetos están relacionados](how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase y MyClass](../../program-structure/me-my-mybase-and-myclass.md)
