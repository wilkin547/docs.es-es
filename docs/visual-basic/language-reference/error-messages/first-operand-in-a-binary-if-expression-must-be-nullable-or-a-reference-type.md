---
description: "Más información sobre: BC33107: el primer operando de una expresión ' if ' binaria debe admitir valores NULL o un tipo de referencia"
title: El primer operando de una expresión 'If' binaria debe ser un tipo que acepte valores NULL o un tipo de referencia
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 4a0037680e31a8220cb796e6d8f3215139e01b20
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796254"
---
# <a name="bc33107-first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="58aac-103">BC33107: el primer operando de una expresión ' if ' binaria debe admitir valores NULL o un tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="58aac-103">BC33107: First operand in a binary 'If' expression must be nullable or a reference type</span></span>

<span data-ttu-id="58aac-104">Una `If` expresión puede tomar dos o tres argumentos.</span><span class="sxs-lookup"><span data-stu-id="58aac-104">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="58aac-105">Cuando se envían solo dos argumentos, el primer argumento debe ser un tipo de referencia o un tipo de valor que acepte valores NULL.</span><span class="sxs-lookup"><span data-stu-id="58aac-105">When you send only two arguments, the first argument must be a reference type or a nullable value type.</span></span> <span data-ttu-id="58aac-106">Si el primer argumento se evalúa como distinto de `Nothing` , se devuelve su valor.</span><span class="sxs-lookup"><span data-stu-id="58aac-106">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="58aac-107">Si el primer argumento se evalúa como `Nothing` , el segundo argumento se evalúa y se devuelve.</span><span class="sxs-lookup"><span data-stu-id="58aac-107">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>

 <span data-ttu-id="58aac-108">Por ejemplo, el código siguiente contiene dos `If` expresiones: una con tres argumentos y otra con dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="58aac-108">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="58aac-109">Las expresiones calculan y devuelven el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="58aac-109">The expressions calculate and return the same value.</span></span>

```vb
' firstChoice is a nullable value type.
Dim firstChoice? As Integer = Nothing
Dim secondChoice As Integer = 1128
' If expression with three arguments.
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))
' If expression with two arguments.
Console.WriteLine(If(firstChoice, secondChoice))
```

 <span data-ttu-id="58aac-110">Las expresiones siguientes provocan este error:</span><span class="sxs-lookup"><span data-stu-id="58aac-110">The following expressions cause this error:</span></span>

```vb
Dim choice1 = 4
Dim choice2 = 5
Dim booleanVar = True

' Not valid.
'Console.WriteLine(If(choice1 < choice2, 1))
' Not valid.
'Console.WriteLine(If(booleanVar, "Test returns True."))
```

 <span data-ttu-id="58aac-111">**Identificador de error:** BC33107</span><span class="sxs-lookup"><span data-stu-id="58aac-111">**Error ID:** BC33107</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="58aac-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="58aac-112">To correct this error</span></span>

- <span data-ttu-id="58aac-113">Si no puede cambiar el código para que el primer argumento sea un tipo de valor o un tipo de referencia que acepte valores NULL, considere la posibilidad de convertir en una expresión de tres argumentos `If` o en una `If...Then...Else` instrucción.</span><span class="sxs-lookup"><span data-stu-id="58aac-113">If you cannot change the code so that the first argument is a nullable value type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>

```vb
Console.WriteLine(If(choice1 < choice2, 1, 2))
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))
```

## <a name="see-also"></a><span data-ttu-id="58aac-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="58aac-114">See also</span></span>

- [<span data-ttu-id="58aac-115">Operador If</span><span class="sxs-lookup"><span data-stu-id="58aac-115">If Operator</span></span>](../operators/if-operator.md)
- [<span data-ttu-id="58aac-116">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="58aac-116">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="58aac-117">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="58aac-117">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
