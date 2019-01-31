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
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="3cc69-102">El primer operando de una expresión 'If' binaria debe ser un tipo que acepte valores NULL o un tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="3cc69-102">First operand in a binary 'If' expression must be nullable or a reference type</span></span>
<span data-ttu-id="3cc69-103">Un `If` expresión puede tardar dos o tres argumentos.</span><span class="sxs-lookup"><span data-stu-id="3cc69-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="3cc69-104">Cuando se envía solo dos argumentos, el primer argumento debe ser un tipo de referencia o un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="3cc69-104">When you send only two arguments, the first argument must be a reference type or a nullable type.</span></span> <span data-ttu-id="3cc69-105">Si el primer argumento se evalúa como algo distinto `Nothing`, se devuelve su valor.</span><span class="sxs-lookup"><span data-stu-id="3cc69-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="3cc69-106">Si el primer argumento se evalúa como `Nothing`, se evalúa y devuelve el segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="3cc69-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="3cc69-107">Por ejemplo, el código siguiente contiene dos `If` expresiones, uno con tres argumentos y uno con dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="3cc69-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="3cc69-108">Las expresiones de calcular y devolverán el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="3cc69-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="3cc69-109">Las expresiones siguientes provocan este error:</span><span class="sxs-lookup"><span data-stu-id="3cc69-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="3cc69-110">**Identificador de error:** BC33107</span><span class="sxs-lookup"><span data-stu-id="3cc69-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3cc69-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3cc69-111">To correct this error</span></span>  
  
-   <span data-ttu-id="3cc69-112">Si no se puede cambiar el código para que el primer argumento es un tipo que acepta valores NULL o un tipo de referencia, considere la posibilidad de convertir a un argumento de tres `If` expresión, o a un `If...Then...Else` instrucción.</span><span class="sxs-lookup"><span data-stu-id="3cc69-112">If you cannot change the code so that the first argument is a nullable type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cc69-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cc69-113">See also</span></span>
- [<span data-ttu-id="3cc69-114">If (operador)</span><span class="sxs-lookup"><span data-stu-id="3cc69-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="3cc69-115">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3cc69-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="3cc69-116">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="3cc69-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
