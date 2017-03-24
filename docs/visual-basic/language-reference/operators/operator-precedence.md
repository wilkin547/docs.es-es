---
title: Precedencia de operadores en Visual Basic | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- arithmetic operators, precedence
- operator precedence
- logical operators, precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators
- operators [Visual Basic], precedence
- precedence, of operators
- comparison operators, precedence
- math operators
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6532fc0c26db3b736c863be075571570a3d25eef
ms.lasthandoff: 03/13/2017

---
# <a name="operator-precedence-in-visual-basic"></a>Prioridad de operador en Visual Basic
Cuando se producen varias operaciones en una expresión, cada parte se evalúa y se resuelve en un orden predeterminado denominado *prioridad de operador*.  
  
## <a name="precedence-rules"></a>Reglas de prioridad  
 Cuando las expresiones contienen operadores de más de una categoría, se evalúan según las reglas siguientes:  
  
-   Los operadores aritméticos y de concatenación tienen el orden de prioridad que se describe en la sección siguiente, y todos tienen mayor prioridad que la comparación, lógicos y operadores bit a bit.  
  
-   Todos los operadores de comparación tienen la misma precedencia y todos tienen mayor prioridad que los operadores lógicos y bit a bit, pero menor prioridad que los operadores aritméticos y de concatenación.  
  
-   Los operadores lógicos y bit a bit tienen el orden de prioridad que se describe en la siguiente sección y tienen menor prioridad que los operadores de comparación, concatenación y aritmética.  
  
-   Operadores con la misma prioridad se evalúan de izquierda a derecha en el orden en que aparecen en la expresión.  
  
## <a name="precedence-order"></a>Orden de prioridad  
 Los operadores se evalúan en el siguiente orden de prioridad:  
  
### <a name="await-operator"></a>Await (Operador)  
 Await  
  
### <a name="arithmetic-and-concatenation-operators"></a>Operadores de concatenación y aritméticos  
 Exponenciación (`^`)  
  
 Unario identidad y negación (`+`, `–`)  
  
 Multiplicación y división de coma flotante (`*`, `/`)  
  
 División de enteros (`\`)  
  
 Módulo aritmético (`Mod`)  
  
 Suma y resta (`+`, `–`)  
  
 Concatenación de cadenas (`&`)  
  
 Desplazamiento de bits aritmético (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>Operadores de comparación  
 All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>Operadores lógicos y bit a bit  
 Negación (`Not`)  
  
 Conjunción (`And`, `AndAlso`)  
  
 Disyunción inclusiva (`Or`, `OrElse`)  
  
 Disyunción exclusiva (`Xor`)  
  
### <a name="comments"></a>Comentarios  
 El `=` operador es sólo el operador de comparación de igualdad, no el operador de asignación.  
  
 El operador de concatenación de cadenas (`&`) no es un operador aritmético, pero en prioridad, se agrupa con los operadores aritméticos.  
  
 El `Is` y `IsNot` operadores son operadores de comparación de referencia de objeto. No se comparan los valores de dos objetos; sólo comprueban y para determinar si dos variables de objeto hacen referencia a la misma instancia de objeto.  
  
## <a name="associativity"></a>Asociatividad  
 Cuando aparecen operadores de la misma prioridad juntos en una expresión, por ejemplo, multiplicación y división, el compilador evalúa cada operación encuentra de izquierda a derecha. Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 La primera expresión se evalúa como la división de 96 / 8 (que da como resultado 12) y, a continuación, la división de 12 / 4, lo que resulta en tres. Dado que el compilador evalúa las operaciones de `n1` de izquierda a derecha, la evaluación es la misma cuando ese orden está indicado de forma explícita `n2`. Ambos `n1` y `n2` tiene un resultado de tres. Por el contrario, `n3` da como resultado 48, porque los paréntesis fuerzan al compilador a evaluar 8 / 4 primero.  
  
 Debido a este comportamiento, los operadores se dice que *asociativos por la izquierda* en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="overriding-precedence-and-associativity"></a>Reemplazar la prioridad y asociatividad  
 Puede utilizar paréntesis para forzar que algunas partes de una expresión se evalúe antes que otras. Esto puede invalidar el orden de prioridad y asociatividad por la izquierda. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]siempre realiza operaciones que están entre paréntesis antes que los fuera. Sin embargo, entre paréntesis, mantiene ordinario prioridad y asociatividad, a menos que utilice paréntesis dentro del paréntesis. Esto se ilustra en el siguiente ejemplo:  
  
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
 [= (Operador)](../../../visual-basic/language-reference/operators/assignment-operator.md)   
 [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Like (operador)](../../../visual-basic/language-reference/operators/like-operator.md)   
 [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Await (operador)](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
