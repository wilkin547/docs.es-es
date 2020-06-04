---
title: ^ (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: e139becf74ae367266a23513e18d0bdbdd24cdea
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371393"
---
# <a name="-operator-visual-basic"></a>^ (Operador, Visual Basic)

Eleva un número a la potencia de otro número.

## <a name="syntax"></a>Sintaxis

```vb
number ^ exponent
```

## <a name="parts"></a>Partes

`number`\
Necesario. Cualquier expresión numérica.

`exponent`\
Necesario. Cualquier expresión numérica.

## <a name="result"></a>Resultado

El resultado se `number` eleva a la potencia de `exponent` , siempre como un `Double` valor.

## <a name="supported-types"></a>Tipos admitidos

`Double`. Los operandos de cualquier tipo diferente se convierten en `Double` .

## <a name="remarks"></a>Observaciones

Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../data-types/double-data-type.md).

El valor de `exponent` puede ser fraccionario, negativo o ambos.

Cuando se realiza más de una exponenciación en una sola expresión, el `^` operador se evalúa como se encuentra de izquierda a derecha.

> [!NOTE]
> El `^` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa el `^` operador para elevar un número a la potencia de un exponente. El resultado es el primer operando elevado a la potencia del segundo.

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

En el ejemplo anterior se generan los siguientes resultados:

`exp1`está establecido en 4 (2 cuadrados).

`exp2`está establecido en 19683 (3 cubos y, a continuación, ese valor en cubo).

`exp3`está establecido en-125 (-5 cubed).

`exp4`está establecido en 625 (-5 en la cuarta potencia).

`exp5`está establecido en 2 (raíz del cubo de 8).

`exp6`está establecido en 0,5 (1,0 dividido por la raíz del cubo de 8).

Tenga en cuenta la importancia de los paréntesis en las expresiones del ejemplo anterior. Debido a la prioridad de los *operadores*, Visual Basic normalmente realiza el `^` operador antes que cualquier otro, incluso el operador unario `–` . Si `exp4` y `exp6` se hubieran calculado sin paréntesis, habrían generado los siguientes resultados:

`exp4 = -5 ^ 4`se calcularía como – (5 a la cuarta potencia), lo que daría como resultado-625.

`exp6 = 8 ^ -1.0 / 3.0`se calculará como (8 para la potencia – 1 o 0,125) dividido entre 3,0, lo que daría lugar a 0.041666666666666666666666666666667.

## <a name="see-also"></a>Consulte también

- [Operador ^ =](exponentiation-assignment-operator.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
