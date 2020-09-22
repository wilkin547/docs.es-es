---
title: '>>= (Operador)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: a1c2331791644155504183d3cf5767470a3bf17b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873350"
---
# <a name="-operator-visual-basic"></a>>>= (operador) (Visual Basic)

Realiza un desplazamiento aritmético a la derecha en el valor de una variable o propiedad y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Partes  

 `variableorproperty`  
 Obligatorio. Variable o propiedad de un tipo entero ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` o `ULong` ).  
  
 `amount`  
 Obligatorio. Expresión numérica de un tipo de datos que se amplía a `Integer` .  
  
## <a name="remarks"></a>Comentarios  

 El elemento del lado izquierdo del `>>=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).  
  
 El `>>=` operador realiza primero un desplazamiento aritmético a la derecha en el valor de la variable o propiedad. A continuación, el operador asigna el resultado de la operación a la variable o propiedad.  
  
 Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo. En un desplazamiento aritmético a la derecha, se descartan los bits desplazados más allá de la posición de bit situada más a la derecha y el bit del extremo izquierdo se propaga a las posiciones de bits que quedan a la izquierda. Esto significa que si `variableorproperty` tiene un valor negativo, las posiciones vacías se establecen en una. Si `variableorproperty` es positivo, o si su tipo de datos es un tipo sin signo, las posiciones vacantes se establecen en cero.  
  
## <a name="overloading"></a>Sobrecarga  

 El [ operador de>> ](right-shift-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del `>>` operador afecta al comportamiento del `>>=` operador. Si el código utiliza `>>=` en una clase o estructura que sobrecarga `>>` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `>>=` operador para desplazar el patrón de bits de una `Integer` variable a la derecha la cantidad especificada y asignar el resultado a la variable.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Consulte también

- [>> (operador)](right-shift-operator.md)
- [Operadores de asignación](assignment-operators.md)
- [Operadores de desplazamiento de bits](bit-shift-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
