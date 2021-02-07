---
description: 'Más información sobre: precedencia de operadores en Visual Basic'
title: Prioridad de los operadores
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
ms.openlocfilehash: 7aa4677549328d450834f3a1ecb047d405893f69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665294"
---
# <a name="operator-precedence-in-visual-basic"></a>Prioridad de operador en Visual Basic

Cuando se producen varias operaciones en una expresión, cada parte se evalúa y se resuelve en un orden predeterminado denominado *precedencia de operadores*.

## <a name="precedence-rules"></a>Reglas de precedencia

 Cuando las expresiones contienen operadores de más de una categoría, se evalúan según las reglas siguientes:

- Los operadores aritméticos y de concatenación tienen el orden de prioridad que se describe en la sección siguiente y todos tienen mayor prioridad que los operadores de comparación, lógicos y bit a bit.

- Todos los operadores de comparación tienen la misma prioridad y todos tienen mayor prioridad que los operadores lógicos y bit a bit, pero tienen menor prioridad que los operadores aritméticos y de concatenación.

- Los operadores lógicos y bit a bit tienen el orden de prioridad que se describe en la sección siguiente y todos tienen menor prioridad que los operadores aritméticos, de concatenación y de comparación.

- Los operadores con la misma prioridad se evalúan de izquierda a derecha en el orden en que aparecen en la expresión.

## <a name="precedence-order"></a>Orden de prioridad

 Los operadores se evalúan en el orden de prioridad siguiente:

### <a name="await-operator"></a>Await (Operador)

 Operador

### <a name="arithmetic-and-concatenation-operators"></a>Operadores aritméticos y de concatenación

 Exponenciación ( `^` )

 Identidad unaria y negación ( `+` , `–` )

 Multiplicación y división de punto flotante ( `*` , `/` )

 División de enteros ( `\` )

 Aritmética modular ( `Mod` )

 Suma y resta ( `+` , `–` )

 Concatenación de cadenas ( `&` )

 Desplazamiento de bits aritmético ( `<<` , `>>` )

### <a name="comparison-operators"></a>Operadores de comparación

 Todos los operadores de comparación ( `=` , `<>` , `<` , `<=` , `>` , `>=` , `Is` , `IsNot` , `Like` , `TypeOf` ... `Is` )

### <a name="logical-and-bitwise-operators"></a>Operadores lógicos y bit a bit

 Negación ( `Not` )

 Conjunción ( `And` , `AndAlso` )

 Disyunción inclusiva ( `Or` , `OrElse` )

 Disyunción exclusiva ( `Xor` )

### <a name="comments"></a>Comentarios

 El `=` operador es solo el operador de comparación de igualdad, no el operador de asignación.

 El operador de concatenación de cadenas ( `&` ) no es un operador aritmético, pero en su precedencia está agrupado con los operadores aritméticos.

 Los `Is` `IsNot` operadores y son operadores de comparación de referencia de objeto. No comparan los valores de dos objetos; solo comprueban si dos variables de objeto hacen referencia a la misma instancia de objeto.

## <a name="associativity"></a>asociatividad

 Cuando los operadores de igual precedencia aparecen juntos en una expresión, por ejemplo multiplicación y división, el compilador evalúa cada operación a medida que la encuentra de izquierda a derecha. Esto se ilustra en el siguiente ejemplo:

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 La primera expresión evalúa la división 96/8 (que da como resultado 12) y, a continuación, la división 12/4, que da como resultado tres. Dado que el compilador evalúa las operaciones de `n1` izquierda a derecha, la evaluación es la misma cuando ese orden se indica explícitamente para `n2` . `n1`Y `n2` tienen el resultado de tres. Por el contrario, `n3` tiene un resultado de 48, porque los paréntesis obligan al compilador a evaluar 8/4 primero.

 Debido a este comportamiento, se dice que los operadores son *asociativos* a la izquierda en Visual Basic.

## <a name="overriding-precedence-and-associativity"></a>Reemplazar precedencia y asociatividad

 Puede usar paréntesis para forzar que se evalúen algunas partes de una expresión antes que otras. Esto puede invalidar el orden de prioridad y la asociatividad izquierda. Visual Basic siempre realiza las operaciones que se incluyen entre paréntesis antes de las externas. Sin embargo, entre paréntesis, mantiene la prioridad y la asociatividad ordinarias, a menos que use paréntesis dentro de los paréntesis. Esto se ilustra en el siguiente ejemplo:

```vb
Dim a, b, c, d, e, f, g As Double
a = 8.0
b = 3.0
c = 4.0
d = 2.0
e = 1.0
f = a - b + c / d * e
' The preceding line sets f to 7.0. Because of natural operator
' precedence and associativity, it is exactly equivalent to the
' following line.
f = (a - b) + ((c / d) * e)
' The following line overrides the natural operator precedence
' and left associativity.
g = (a - (b + c)) / (d * e)
' The preceding line sets g to 0.5.
```

## <a name="see-also"></a>Vea también

- [= (Operador)](assignment-operator.md)
- [Operador Is](is-operator.md)
- [Operador IsNot](isnot-operator.md)
- [Like (Operador)](like-operator.md)
- [Operador TypeOf](typeof-operator.md)
- [Await (Operador)](await-operator.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores y expresiones](../../programming-guide/language-features/operators-and-expressions/index.md)
