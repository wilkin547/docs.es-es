---
title: "Cómo: calcular valores numéricos (Visual Basic) | Documentos de Microsoft"
ms.custom: 
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
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations, numeric expressions
- precedence, of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: d844e2af3892d897125e21d3fd7047a8b295d10a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Cómo: Calcular valores numéricos (Visual Basic)
Puede calcular valores numéricos mediante el uso de expresiones numéricas. Un *expresión numérica* es una expresión que contiene literales, constantes y variables que representan valores numéricos y operadores que actúan sobre esos valores.  
  
## <a name="calculating-numeric-values"></a>Calcular valores numéricos  
  
#### <a name="to-calculate-a-numeric-value"></a>Para calcular un valor numérico  
  
-   Combinar uno o más literales numéricos, constantes y variables en una expresión numérica. El ejemplo siguiente muestra algunas expresiones numéricas válidas.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Las tres primeras líneas muestran un literal, una constante y una variable. Cada uno forma una expresión numérica válida por sí mismo. La línea final muestra una combinación de una variable con dos literales.  
  
     Tenga en cuenta que una expresión numérica no forma una completa [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] instrucción por sí mismo. Debe usar la expresión como parte de una instrucción completa.  
  
#### <a name="to-store-a-numeric-value"></a>Para almacenar un valor numérico  
  
-   Puede utilizar una instrucción de asignación para asignar el valor representado por una expresión numérica a una variable, como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbVbalrOperators&#82;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     En el ejemplo anterior, el valor de la expresión en el lado derecho del operador igual (`=`) se asigna a la variable `j` en el lado izquierdo del operador, por lo que `j` se evalúa como 276.  
  
     Para obtener más información, consulte [instrucciones](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Operadores varios  
 Si la expresión numérica contiene más de un operador, se determina el orden en que se evalúan las reglas de precedencia de operadores. Para reemplazar las reglas de prioridad de operador, las expresiones se escriben entre paréntesis, como en el ejemplo anterior; Estas expresiones se evalúan primero.  
  
#### <a name="to-override-normal-operator-precedence"></a>Para invalidar la prioridad de operador  
  
-   Utilice paréntesis para indicar las operaciones que desee que se ejecute primero. El ejemplo siguiente muestra dos resultados diferentes con los mismos operandos y operadores.  
  
     [!code-vb[VbVbalrOperators número&83;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     En el ejemplo anterior, el cálculo de `j` realiza el operador de suma (`+`) primera porque los paréntesis alrededor de `(67 + i)` invalidar la prioridad normal y el valor asignado a `j` es 276 (4 por 69). El cálculo de `k` ejecuta los operadores con su prioridad normal (`*` antes de `+`) y el valor asignado a `k` es 270 (268 más 2).  
  
     Para obtener más información, consulte [prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Vea también  
 [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)   
 [Precedencia de operadores en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores aritméticos](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
