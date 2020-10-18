---
title: El primer operando de una expresión 'If' binaria debe ser un tipo que acepte valores NULL o un tipo de referencia
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: bca9b74a68815b4e5a3bb2dc114b9031cdf24099
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162744"
---
# <a name="bc33107-first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>BC33107: el primer operando de una expresión ' if ' binaria debe admitir valores NULL o un tipo de referencia

Una `If` expresión puede tomar dos o tres argumentos. Cuando se envían solo dos argumentos, el primer argumento debe ser un tipo de referencia o un tipo de valor que acepte valores NULL. Si el primer argumento se evalúa como distinto de `Nothing` , se devuelve su valor. Si el primer argumento se evalúa como `Nothing` , el segundo argumento se evalúa y se devuelve.

 Por ejemplo, el código siguiente contiene dos `If` expresiones: una con tres argumentos y otra con dos argumentos. Las expresiones calculan y devuelven el mismo valor.

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

- Si no puede cambiar el código para que el primer argumento sea un tipo de valor o un tipo de referencia que acepte valores NULL, considere la posibilidad de convertir en una expresión de tres argumentos `If` o en una `If...Then...Else` instrucción.

```vb
Console.WriteLine(If(choice1 < choice2, 1, 2))
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))
```

## <a name="see-also"></a>Vea también

- [Operador If](../operators/if-operator.md)
- [Instrucción If...Then...Else](../statements/if-then-else-statement.md)
- [Tipos de valor que aceptan valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md)
