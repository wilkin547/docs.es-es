---
title: "^ (Operador, Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.^"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "^ (operador) [Visual Basic]"
  - "^ (operador) [Visual Basic], exponenciación"
  - "operadores aritméticos, exponenciación"
  - "exponente"
  - "exponenciación (operador) [Visual Basic]"
  - "números, elevar"
  - "potencias"
  - "elevar números a potencias"
  - "operador de cuadrado"
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ^ (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Eleva un número a la potencia indicada por otro.  
  
## Sintaxis  
  
```  
  
number ^ exponent  
```  
  
## Elementos  
 `number`  
 Obligatorio.  Cualquier expresión numérica.  
  
 `exponent`  
 Obligatorio.  Cualquier expresión numérica.  
  
## Resultado  
 El resultado es `number` elevado a la potencia de `exponent`, siempre como un valor `Double`.  
  
## Tipos admitidos  
 `Double`.  Operandos de cualquier tipo diferente se convierten a `Double`.  
  
## Comentarios  
 Visual Basic siempre realiza la exponenciación en [Double \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/double-data-type.md).  
  
 El valor de `exponent` puede ser fraccionario, negativo o ambos.  
  
 Cuando se realizan varias exponenciaciones en una única expresión, el operador `^` se evalúa a medida que se va encontrando de izquierda a derecha.  
  
> [!NOTE]
>  El operador `^` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el operador `^` para elevar un número a la potencia del exponente.  El resultado será el primer operando a la potencia del segundo.  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 En el ejemplo anterior los resultados son:  
  
 `exp1` se establece en 4 \(2 al cuadrado\).  
  
 `exp2` se establece en 19683 \(3 al cubo; a continuación, ese valor se eleva al cubo\).  
  
 `exp3` se establece en \-125 \(\-5 al cubo\).  
  
 `exp4` se establece en 625 \(\-5 elevado a la cuarta\).  
  
 `exp5` se establece en 2 \(raíz cúbica de 8\).  
  
 `exp6` se establece en 0,5 \(1,0 dividido por la raíz cúbica de 8\).  
  
 Observe la importancia de los paréntesis en las expresiones del ejemplo anterior.  Debido a la *prioridad de operadores*, Visual Basic normalmente calcula el operador `^` antes de cualquier otro, antes incluso que el operador unario `–`.  Si `exp4` y `exp6` se hubieran calculado sin paréntesis, habrían generado los resultados siguientes:  
  
 `exp4 = -5 ^ 4` se calcula como – \(5 al cuarto potencia\), que darían lugar a \-625.  
  
 `exp6 = 8 ^ -1.0 / 3.0` se calcularía como \(8 elevado a –1  o 0,125\) dividido entre 3,0, cuyo resultado sería 0,041666666666666666666666666666667.  
  
## Vea también  
 [^\= \(Operador\)](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)