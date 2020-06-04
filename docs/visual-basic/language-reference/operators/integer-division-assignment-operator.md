---
title: Operador \=
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: a546d8b0c9b3852386970f80d3da96794da2351c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370952"
---
# <a name="-operator"></a>\\= (Operador)
Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado entero a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Partes  
 `variableorproperty`  
 Necesario. Cualquier variable o propiedad numérica.  
  
 `expression`  
 Necesario. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Observaciones  
 El elemento del lado izquierdo del `\=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).  
  
 El `\=` operador divide el valor de una variable o propiedad a su izquierda por el valor de su derecha, y asigna el resultado entero a la variable o propiedad de su izquierda.  
  
 Para obtener más información sobre la división de enteros, vea [\ (operador Visual Basic)](integer-division-operator.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `\` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del `\` operador afecta al comportamiento del `\=` operador. Si el código utiliza `\=` en una clase o estructura que sobrecarga `\` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `\=` operador para dividir una `Integer` variable por un segundo y asignar el resultado entero a la primera variable.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Consulte también

- [Operador (Visual Basic)](integer-division-operator.md)
- [/= (Operador) (Visual Basic)](floating-point-division-assignment-operator.md)
- [Operadores de asignación](assignment-operators.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
