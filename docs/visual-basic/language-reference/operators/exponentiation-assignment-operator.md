---
title: ^= (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: e631cc9a484b56ee059449ca1fbd9fc69405333d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371406"
---
# <a name="-operator-visual-basic"></a>^= (Operador, Visual Basic)
Eleva el valor de una variable o propiedad a la potencia de una expresión y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Partes  
 `variableorproperty`  
 Necesario. Cualquier variable o propiedad numérica.  
  
 `expression`  
 Necesario. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Observaciones  
 El elemento del lado izquierdo del `^=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).  
  
 El `^=` operador genera primero el valor de la variable o propiedad (en el lado izquierdo del operador) con la potencia del valor de la expresión (en el lado derecho del operador). A continuación, el operador asigna el resultado de la operación a la variable o propiedad.  
  
 Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../data-types/double-data-type.md). Los operandos de cualquier tipo diferente se convierten en `Double` y el resultado siempre es `Double` .  
  
 El valor de `expression` puede ser fraccionario, negativo o ambos.  
  
## <a name="overloading"></a>Sobrecarga  
 El [operador ^](exponentiation-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del `^` operador afecta al comportamiento del `^=` operador. Si el código utiliza `^=` en una clase o estructura que sobrecarga `^` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `^=` operador para elevar el valor de una `Integer` variable a la potencia de una segunda variable y asignar el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Consulte también

- [^ (Operador)](exponentiation-operator.md)
- [Operadores de asignación](assignment-operators.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
