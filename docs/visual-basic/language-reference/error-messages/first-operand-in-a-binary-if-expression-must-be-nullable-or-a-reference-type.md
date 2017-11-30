---
title: "El primer operando de un archivo binario &#39; si &#39; expresión deben aceptar valores NULL o un tipo de referencia"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords: BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f66b110c02076120c55a3bff28c3d7614bf8be26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="first-operand-in-a-binary-39if39-expression-must-be-nullable-or-a-reference-type"></a>El primer operando de un archivo binario &#39; si &#39; expresión deben aceptar valores NULL o un tipo de referencia
Un `If` expresión puede tomar dos o tres argumentos. Cuando se envían solo dos argumentos, el primer argumento debe ser un tipo de referencia o un tipo que acepta valores NULL. Si el primer argumento se evalúa como algo distinto de `Nothing`, se devuelve su valor. Si el primer argumento se evalúa como `Nothing`, se evalúa y devuelve el segundo argumento.  
  
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
  
 Las expresiones siguientes producen este error:  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **Id. de error:** BC33107  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si no se puede cambiar el código para que el primer argumento es un tipo de referencia o tipo que acepta valores NULL, considere la posibilidad de convertir a un argumento de tres `If` expresión, o a un `If...Then...Else` instrucción.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>Vea también  
 [If (operador)](../../../visual-basic/language-reference/operators/if-operator.md)  
 [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
