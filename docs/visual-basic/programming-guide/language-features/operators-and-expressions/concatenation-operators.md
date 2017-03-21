---
title: "Operadores de concatenación en Visual Basic | Documentos de Microsoft"
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
- '& operator [Visual Basic], concatenation'
- concatenation operators
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators, Visual Basic strings
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
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
ms.openlocfilehash: fa11f1dcff2c333861596cbac03391403cf962c1
ms.lasthandoff: 03/13/2017

---
# <a name="concatenation-operators-in-visual-basic"></a>Operadores de concatenación en Visual Basic
Los operadores de concatenación unen varias cadenas en una sola. Existen dos operadores de concatenación: `+` y `&`. Ambos efectúan la operación de concatenación básica, como se aprecia en el siguiente ejemplo.  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 Estos operadores también concatenan variables de `String`, como indica el siguiente ejemplo.  
  
 [!code-vb[VbVbalrOperators&#76;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a>Diferencias entre los dos operadores de concatenación  
 El [+ (operador)](../../../../visual-basic/language-reference/operators/addition-operator.md) tiene la finalidad principal de sumar dos números. aunque también puede concatenar operandos numéricos con operandos de cadena. El `+` operador tiene un conjunto complejo de reglas que determinan si se va a agregar, concatenar, señalar un error del compilador o producir un tiempo de ejecución <xref:System.InvalidCastException>excepción.</xref:System.InvalidCastException>  
  
 El [aspecto operador](../../../../visual-basic/language-reference/operators/concatenation-operator.md) sólo se define para `String` operandos y siempre amplía sus operandos a `String`, independientemente de la configuración de `Option Strict`. El uso del operador `&` es recomendable para concatenar cadenas, ya que se está expresamente definido para cadenas y reduce las probabilidades de generar una conversión inintencionada.  
  
## <a name="performance-string-and-stringbuilder"></a>Rendimiento: String y StringBuilder  
 Si lo hace un número significativo de manipulaciones en una cadena, como concatenaciones, eliminaciones y reemplazos, el rendimiento puede beneficiarse de la <xref:System.Text.StringBuilder>de clase en el <xref:System.Text>espacio de nombres.</xref:System.Text> </xref:System.Text.StringBuilder> Toma una instrucción extra para crear e inicializar un <xref:System.Text.StringBuilder>objeto y otra instrucción para convertir su valor final a un `String`, pero este tiempo se puede recuperar porque <xref:System.Text.StringBuilder>puede ejecutarse más rápidamente.</xref:System.Text.StringBuilder> </xref:System.Text.StringBuilder>  
  
## <a name="see-also"></a>Vea también  
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Tipos de métodos de manipulación de cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)   
 [Operadores aritméticos en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
