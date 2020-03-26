---
title: El primer operando de una expresión 'If' binaria debe ser un tipo que acepte valores NULL o un tipo de referencia
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 4b520949cb59b63ea39441632dc5e2c6d000d711
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249531"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>El primer operando de una expresión 'If' binaria debe ser un tipo que acepte valores NULL o un tipo de referencia
Una `If` expresión puede tomar dos o tres argumentos. Cuando se envían solo dos argumentos, el primer argumento debe ser un tipo de referencia o un tipo de valor que acepta valores NULL. Si el primer argumento se `Nothing`evalúa como algo distinto de , se devuelve su valor. Si el primer argumento `Nothing`se evalúa como , se evalúa y devuelve el segundo argumento.  
  
 Por ejemplo, el código `If` siguiente contiene dos expresiones, una con tres argumentos y otra con dos argumentos. Las expresiones calculan y devuelven el mismo valor.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Las siguientes expresiones provocan este error:  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **ID de error:** BC33107  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si no puede cambiar el código para que el primer argumento sea un tipo de `If` valor que `If...Then...Else` acepta valores NULL o un tipo de referencia, considere la posibilidad de convertir en una expresión de tres argumentos o en una instrucción.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>Vea también

- [Operador If](../../../visual-basic/language-reference/operators/if-operator.md)
- [Instrucción If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Tipos de valores que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
