---
title: Las expresiones lambda no son válidas en la primera expresión de una instrucción 'Select Case'
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 448a685a7c174ce212389842c31066f1c4557cdf
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162536"
---
# <a name="bc36635-lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="c82fa-102">BC36635: las expresiones lambda no son válidas en la primera expresión de una instrucción ' Select Case '</span><span class="sxs-lookup"><span data-stu-id="c82fa-102">BC36635: Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>

<span data-ttu-id="c82fa-103">No se puede usar una expresión lambda para la expresión de prueba en una `Select Case` instrucción.</span><span class="sxs-lookup"><span data-stu-id="c82fa-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="c82fa-104">Las definiciones de expresión lambda devuelven funciones y la expresión de prueba de una `Select Case` instrucción debe ser un tipo de datos elemental.</span><span class="sxs-lookup"><span data-stu-id="c82fa-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>

 <span data-ttu-id="c82fa-105">El código siguiente provoca este error:</span><span class="sxs-lookup"><span data-stu-id="c82fa-105">The following code causes this error:</span></span>

```vb
' Select Case (Function(arg) arg Is Nothing)
    ' List of the cases.
' End Select
```

 <span data-ttu-id="c82fa-106">**Identificador de error:** BC36635</span><span class="sxs-lookup"><span data-stu-id="c82fa-106">**Error ID:** BC36635</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c82fa-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c82fa-107">To correct this error</span></span>

- <span data-ttu-id="c82fa-108">Examine el código para determinar si podría funcionar una construcción condicional diferente como, por ejemplo, una instrucción `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="c82fa-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>

- <span data-ttu-id="c82fa-109">Es posible que haya previsto llamar a la función, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c82fa-109">You may have intended to call the function, as shown in the following code:</span></span>

```vb
Dim num? As Integer
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))
    ' List of the cases
End Select
```

## <a name="see-also"></a><span data-ttu-id="c82fa-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c82fa-110">See also</span></span>

- [<span data-ttu-id="c82fa-111">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="c82fa-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="c82fa-112">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="c82fa-112">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="c82fa-113">Instrucción Select...Case</span><span class="sxs-lookup"><span data-stu-id="c82fa-113">Select...Case Statement</span></span>](../statements/select-case-statement.md)
