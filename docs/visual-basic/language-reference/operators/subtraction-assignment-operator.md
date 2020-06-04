---
title: -= (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: 4f403cd8a28f8d9d0ba1d24b0792a352a9c961db
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406410"
---
# <a name="--operator-visual-basic"></a>-= (Operador, Visual Basic)
Resta el valor de una expresión del valor de una variable o propiedad y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a>Partes  
 `variableorproperty`  
 Necesario. Cualquier variable o propiedad numérica.  
  
 `expression`  
 Necesario. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Observaciones  
 El elemento del lado izquierdo del `-=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).  
  
 El `-=` operador resta primero el valor de la expresión (en el lado derecho del operador) del valor de la variable o de la propiedad (en el lado izquierdo del operador). A continuación, el operador asigna el resultado de la operación a la variable o propiedad.  
  
## <a name="overloading"></a>Sobrecarga  
 Se puede *sobrecargar*el [operador-(Visual Basic)](subtraction-operator.md) , lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del `-` operador afecta al comportamiento del `-=` operador. Si el código utiliza `-=` en una clase o estructura que sobrecarga `-` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `-=` operador para restar una `Integer` variable de otra y asignar el resultado a la última variable.  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Consulte también

- [Operador-(Visual Basic)](subtraction-operator.md)
- [Operadores de asignación](assignment-operators.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
