---
description: 'Más información acerca de: = (operador)'
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
ms.openlocfilehash: a05e136cbf17eaf7102fb2213993adf9cf0e06be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665814"
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
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Observaciones  

 El elemento del lado izquierdo del `\=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).  
  
 El `\=` operador divide el valor de una variable o propiedad a su izquierda por el valor de su derecha, y asigna el resultado entero a la variable o propiedad de su izquierda.  
  
 Para obtener más información sobre la división de enteros, vea [\ (operador Visual Basic)](integer-division-operator.md).  
  
## <a name="overloading"></a>Sobrecarga  

 El `\` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del `\` operador afecta al comportamiento del `\=` operador. Si el código utiliza `\=` en una clase o estructura que sobrecarga `\` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `\=` operador para dividir una `Integer` variable por un segundo y asignar el resultado entero a la primera variable.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vea también

- [Operador (Visual Basic)](integer-division-operator.md)
- [/= (Operador) (Visual Basic)](floating-point-division-assignment-operator.md)
- [Operadores de asignación](assignment-operators.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
