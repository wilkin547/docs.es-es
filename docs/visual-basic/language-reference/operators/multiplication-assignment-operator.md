---
title: '*= (Operador)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 4e2f18fb2b8110d97390390b3934d3c1761baa35
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866737"
---
# <a name="-operator-visual-basic"></a>*= (Operador, Visual Basic)

Multiplica el valor de una variable o propiedad por el valor de una expresión y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Partes  

 `variableorproperty`  
 Obligatorio. Cualquier variable o propiedad numérica.  
  
 `expression`  
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Comentarios  

 El elemento del lado izquierdo del `*=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).  
  
 El `*=` operador multiplica primero el valor de la expresión (en el lado derecho del operador) por el valor de la variable o propiedad (en el lado izquierdo del operador). A continuación, el operador asigna el resultado de la operación a la variable o propiedad.  
  
## <a name="overloading"></a>Sobrecarga  

 El [operador *](multiplication-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del `*` operador afecta al comportamiento del `*=` operador. Si el código utiliza `*=` en una clase o estructura que sobrecarga `*` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `*=` operador para multiplicar una `Integer` variable por un segundo y asignar el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Consulte también

- [* (Operador)](multiplication-operator.md)
- [Operadores de asignación](assignment-operators.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
