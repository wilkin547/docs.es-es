---
title: '&amp;= (Operador)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: db42f7be7225b866eacf5b73066754e91cd1a0f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371991"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operador = (Visual Basic)
Concatena una `String` expresión a una `String` variable o propiedad y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Partes  
 `variableorproperty`  
 Necesario. Cualquier `String` variable o propiedad.  
  
 `expression`  
 Necesario. Cualquier expresión `String` .  
  
## <a name="remarks"></a>Observaciones  
 El elemento del lado izquierdo del `&=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md). El `&=` operador concatena la `String` expresión de su derecha a la `String` variable o propiedad de su izquierda, y asigna el resultado a la variable o propiedad de su izquierda.  
  
## <a name="overloading"></a>Sobrecarga  
 El [operador de&](concatenation-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del `&` operador afecta al comportamiento del `&=` operador. Si el código utiliza `&=` en una clase o estructura que sobrecarga `&` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `&=` operador para concatenar dos `String` variables y asignar el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Consulte también

- [& (operador)](concatenation-operator.md)
- [Operador + =](addition-assignment-operator.md)
- [Operadores de asignación](assignment-operators.md)
- [Operadores de concatenación](concatenation-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
