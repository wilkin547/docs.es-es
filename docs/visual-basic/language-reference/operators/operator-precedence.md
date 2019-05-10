---
title: Prioridad de operador en Visual Basic
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
ms.openlocfilehash: 95505fd593881ff27418c69550952d072b4e3949
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628870"
---
# <a name="operator-precedence-in-visual-basic"></a>Prioridad de operador en Visual Basic
Cuando se producen varias operaciones en una expresión, cada parte se evalúa y se resuelve en un orden predeterminado llamado *prioridad de operador*.  
  
## <a name="precedence-rules"></a>Reglas de prioridad  
 Cuando las expresiones contienen operadores de más de una categoría, se evalúan según las reglas siguientes:  
  
- Los operadores aritméticos y de concatenación tienen el orden de prioridad que se describe en la sección siguiente, y todos tienen mayor prioridad que la comparación, lógicos y operadores bit a bit.  
  
- Todos los operadores de comparación tienen la misma prioridad y todos tienen mayor prioridad que los operadores lógicos y bit a bit, pero con menor prioridad que los operadores aritméticos y de concatenación.  
  
- Los operadores lógicos y bit a bit tienen el orden de prioridad que se describe en la sección siguiente, y todas tienen menor prioridad que los operadores de comparación, concatenación y aritmética.  
  
- Los operadores con la misma prioridad se evalúan de izquierda a derecha en el orden en que aparecen en la expresión.  
  
## <a name="precedence-order"></a>Orden de prioridad  
 Los operadores se evalúan en el orden de precedencia siguiente:  
  
### <a name="await-operator"></a>Await (Operador)  
 Await  
  
### <a name="arithmetic-and-concatenation-operators"></a>Operaciones aritméticas y operadores de concatenación  
 Exponenciación (`^`)  
  
 Unario identidad y la negación (`+`, `–`)  
  
 Multiplicación y división de punto flotante (`*`, `/`)  
  
 División de enteros (`\`)  
  
 MODULUS aritmético (`Mod`)  
  
 Suma y resta (`+`, `–`)  
  
 Concatenación de cadenas (`&`)  
  
 Desplazamiento de bits aritmético (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>Operadores de comparación  
 Todos los operadores de comparación (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>Operadores lógicos y bit a bit  
 Negación (`Not`)  
  
 Conjunción (`And`, `AndAlso`)  
  
 Disyunción inclusiva (`Or`, `OrElse`)  
  
 Disyunción exclusiva (`Xor`)  
  
### <a name="comments"></a>Comentarios  
 El `=` operador es solo el operador de comparación de igualdad, no el operador de asignación.  
  
 El operador de concatenación de cadenas (`&`) no es un operador aritmético, pero en la prioridad se agrupa con los operadores aritméticos.  
  
 El `Is` y `IsNot` operadores son operadores de comparación de referencia de objeto. No se comparan los valores de dos objetos; que se registren solo para determinar si dos variables de objeto hacen referencia a la misma instancia de objeto.  
  
## <a name="associativity"></a>asociatividad  
 Cuando los operadores tienen la misma precedencia aparecen juntas en una expresión, por ejemplo, multiplicación y división, el compilador evalúa cada operación tal y como encuentra de izquierda a derecha. Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 La primera expresión se evalúa como la división de 96 / 8 (lo que da como resultado 12) y, a continuación, la división de 12 / 4, lo que resulta en tres. Dado que el compilador evalúa las operaciones de `n1` de izquierda a derecha, la evaluación es el mismo cuando ese criterio se indica explícitamente para `n2`. Ambos `n1` y `n2` tiene un resultado de tres. Por el contrario, `n3` tiene un resultado de 48, porque los paréntesis fuerzan al compilador que evaluar 8 / 4 primero.  
  
 Debido a este comportamiento, los operadores se consideran *asociativos a la izquierda* en Visual Basic.  
  
## <a name="overriding-precedence-and-associativity"></a>Invalidación de precedencia y asociatividad  
 Puede usar paréntesis para forzar que algunas partes de una expresión se evalúe antes que otras. Esto puede invalidar el orden de prioridad y asociatividad por la izquierda. Visual Basic siempre realiza las operaciones que se incluyen entre paréntesis antes de aquellos que no pertenecen. Sin embargo, entre paréntesis, mantiene normal prioridad y asociatividad, a menos que utilice paréntesis dentro del paréntesis. Esto se ilustra en el siguiente ejemplo:  
  
```  
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

- [Operador =](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Like (operador)](../../../visual-basic/language-reference/operators/like-operator.md)
- [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Await (operador)](../../../visual-basic/language-reference/operators/await-operator.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
