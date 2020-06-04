---
title: '- Operador'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 6539beb5cf8078281357445e2391fac189208087
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406359"
---
# <a name="--operator-visual-basic"></a>- (Operador, Visual Basic)
Devuelve la diferencia entre dos expresiones numéricas o el valor negativo de una expresión numérica.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
expression1 – expression2
```
  
o

```vb  
–expression1  
```  
  
## <a name="parts"></a>Partes  
 `expression1`  
 Necesario. Cualquier expresión numérica.  
  
 `expression2`  
 Obligatorio a menos que el `–` operador calcule un valor negativo. Cualquier expresión numérica.  
  
## <a name="result"></a>Resultado  
 El resultado es la diferencia entre `expression1` y `expression2` , o el valor negado de `expression1` .  
  
 El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2` . Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Tipos admitidos  
 todos los tipos numéricos. Esto incluye los tipos de punto flotante y sin signo y `Decimal` .  
  
## <a name="remarks"></a>Observaciones  
 En el primer uso que se muestra en la sintaxis mostrada anteriormente, el operador `–` es el operador de resta aritmética *binaria* para la diferencia entre dos expresiones numéricas.  
  
 En el segundo uso que se muestra en la sintaxis mostrada anteriormente, el `–` operador es el operador *unario* de negación para el valor negativo de una expresión. En este sentido, la negación consiste en invertir el signo de `expression1` para que el resultado sea positivo si `expression1` es negativo.  
  
 Si alguna de las expresiones se evalúa como [Nothing](../nothing.md), el `–` operador la trata como cero.  
  
> [!NOTE]
> El `–` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `–` operador para calcular y devolver la diferencia entre dos números y, a continuación, para negar un número.  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 Después de la ejecución de estas instrucciones, `binaryResult` contiene 124,45 y `unaryResult` contiene – 334,90.  
  
## <a name="see-also"></a>Consulte también

- [-= (Operador) (Visual Basic)](subtraction-assignment-operator.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
