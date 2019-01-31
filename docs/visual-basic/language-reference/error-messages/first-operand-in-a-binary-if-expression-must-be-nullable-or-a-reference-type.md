---
title: El primer operando de una expresión 'If' binaria debe ser un tipo que acepte valores NULL o un tipo de referencia
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: cb47670e8417e903b2886887394b972d1ac138b0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284640"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>El primer operando de una expresión 'If' binaria debe ser un tipo que acepte valores NULL o un tipo de referencia
Un `If` expresión puede tardar dos o tres argumentos. Cuando se envía solo dos argumentos, el primer argumento debe ser un tipo de referencia o un tipo que acepta valores NULL. Si el primer argumento se evalúa como algo distinto `Nothing`, se devuelve su valor. Si el primer argumento se evalúa como `Nothing`, se evalúa y devuelve el segundo argumento.  
  
 Por ejemplo, el código siguiente contiene dos `If` expresiones, uno con tres argumentos y uno con dos argumentos. Las expresiones de calcular y devolverán el mismo valor.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Las expresiones siguientes provocan este error:  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **Identificador de error:** BC33107  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si no se puede cambiar el código para que el primer argumento es un tipo que acepta valores NULL o un tipo de referencia, considere la posibilidad de convertir a un argumento de tres `If` expresión, o a un `If...Then...Else` instrucción.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>Vea también
- [If (operador)](../../../visual-basic/language-reference/operators/if-operator.md)
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
