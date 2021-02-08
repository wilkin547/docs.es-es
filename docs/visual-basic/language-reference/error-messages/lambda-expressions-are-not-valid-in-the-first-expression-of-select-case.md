---
description: "Más información sobre: BC36635: las expresiones lambda no son válidas en la primera expresión de una instrucción ' Select Case '"
title: Las expresiones lambda no son válidas en la primera expresión de una instrucción 'Select Case'
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: e0c388db7164f6c9f99ba917109593a796f7b23b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795942"
---
# <a name="bc36635-lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="01f74-103">BC36635: las expresiones lambda no son válidas en la primera expresión de una instrucción ' Select Case '</span><span class="sxs-lookup"><span data-stu-id="01f74-103">BC36635: Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>

<span data-ttu-id="01f74-104">No se puede usar una expresión lambda para la expresión de prueba en una `Select Case` instrucción.</span><span class="sxs-lookup"><span data-stu-id="01f74-104">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="01f74-105">Las definiciones de expresión lambda devuelven funciones y la expresión de prueba de una `Select Case` instrucción debe ser un tipo de datos elemental.</span><span class="sxs-lookup"><span data-stu-id="01f74-105">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>

 <span data-ttu-id="01f74-106">El código siguiente provoca este error:</span><span class="sxs-lookup"><span data-stu-id="01f74-106">The following code causes this error:</span></span>

```vb
' Select Case (Function(arg) arg Is Nothing)
    ' List of the cases.
' End Select
```

 <span data-ttu-id="01f74-107">**Identificador de error:** BC36635</span><span class="sxs-lookup"><span data-stu-id="01f74-107">**Error ID:** BC36635</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="01f74-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="01f74-108">To correct this error</span></span>

- <span data-ttu-id="01f74-109">Examine el código para determinar si podría funcionar una construcción condicional diferente como, por ejemplo, una instrucción `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="01f74-109">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>

- <span data-ttu-id="01f74-110">Es posible que haya previsto llamar a la función, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="01f74-110">You may have intended to call the function, as shown in the following code:</span></span>

```vb
Dim num? As Integer
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))
    ' List of the cases
End Select
```

## <a name="see-also"></a><span data-ttu-id="01f74-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01f74-111">See also</span></span>

- [<span data-ttu-id="01f74-112">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="01f74-112">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="01f74-113">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="01f74-113">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="01f74-114">Instrucción Select...Case</span><span class="sxs-lookup"><span data-stu-id="01f74-114">Select...Case Statement</span></span>](../statements/select-case-statement.md)
