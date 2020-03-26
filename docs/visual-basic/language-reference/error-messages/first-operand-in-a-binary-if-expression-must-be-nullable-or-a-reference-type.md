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
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="bdba5-102">El primer operando de una expresión 'If' binaria debe ser un tipo que acepte valores NULL o un tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="bdba5-102">First operand in a binary 'If' expression must be nullable or a reference type</span></span>
<span data-ttu-id="bdba5-103">Una `If` expresión puede tomar dos o tres argumentos.</span><span class="sxs-lookup"><span data-stu-id="bdba5-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="bdba5-104">Cuando se envían solo dos argumentos, el primer argumento debe ser un tipo de referencia o un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="bdba5-104">When you send only two arguments, the first argument must be a reference type or a nullable value type.</span></span> <span data-ttu-id="bdba5-105">Si el primer argumento se `Nothing`evalúa como algo distinto de , se devuelve su valor.</span><span class="sxs-lookup"><span data-stu-id="bdba5-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="bdba5-106">Si el primer argumento `Nothing`se evalúa como , se evalúa y devuelve el segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="bdba5-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="bdba5-107">Por ejemplo, el código `If` siguiente contiene dos expresiones, una con tres argumentos y otra con dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="bdba5-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="bdba5-108">Las expresiones calculan y devuelven el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="bdba5-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="bdba5-109">Las siguientes expresiones provocan este error:</span><span class="sxs-lookup"><span data-stu-id="bdba5-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="bdba5-110">**ID de error:** BC33107</span><span class="sxs-lookup"><span data-stu-id="bdba5-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bdba5-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="bdba5-111">To correct this error</span></span>  
  
- <span data-ttu-id="bdba5-112">Si no puede cambiar el código para que el primer argumento sea un tipo de `If` valor que `If...Then...Else` acepta valores NULL o un tipo de referencia, considere la posibilidad de convertir en una expresión de tres argumentos o en una instrucción.</span><span class="sxs-lookup"><span data-stu-id="bdba5-112">If you cannot change the code so that the first argument is a nullable value type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdba5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdba5-113">See also</span></span>

- [<span data-ttu-id="bdba5-114">Operador If</span><span class="sxs-lookup"><span data-stu-id="bdba5-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="bdba5-115">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="bdba5-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="bdba5-116">Tipos de valores que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="bdba5-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
