---
title: Opcional
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: c46d06dba61158d7362d736731161be306af3f10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392150"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="cc4e7-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc4e7-102">Optional (Visual Basic)</span></span>

<span data-ttu-id="cc4e7-103">Especifica que un argumento de procedimiento se puede omitir cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc4e7-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cc4e7-104">Remarks</span></span>

<span data-ttu-id="cc4e7-105">Para cada parámetro opcional, debe especificar una expresión constante como valor predeterminado de ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="cc4e7-106">Si la expresión se evalúa como [Nothing](../nothing.md), se usa el valor predeterminado del tipo de datos Value como valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-106">If the expression evaluates to [Nothing](../nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>

<span data-ttu-id="cc4e7-107">Si la lista de parámetros contiene un parámetro opcional, cada parámetro que siga también debe ser opcional.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>

<span data-ttu-id="cc4e7-108">El modificador `Optional` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cc4e7-108">The `Optional` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="cc4e7-109">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="cc4e7-109">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="cc4e7-110">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="cc4e7-110">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="cc4e7-111">Property Statement</span><span class="sxs-lookup"><span data-stu-id="cc4e7-111">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="cc4e7-112">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="cc4e7-112">Sub Statement</span></span>](../statements/sub-statement.md)

> [!NOTE]
> <span data-ttu-id="cc4e7-113">Cuando se llama a un procedimiento con o sin parámetros opcionales, se pueden pasar argumentos por posición o por nombre.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="cc4e7-114">Para obtener más información, vea [pasar argumentos por posición y por nombre](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="cc4e7-114">For more information, see [Passing Arguments by Position and by Name](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cc4e7-115">También puede definir un procedimiento con parámetros opcionales mediante sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="cc4e7-116">Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepte el parámetro y otra que no lo sea.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="cc4e7-117">Para obtener más información, consulta [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="cc4e7-117">For more information, see [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).</span></span>

## <a name="example"></a><span data-ttu-id="cc4e7-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc4e7-118">Example</span></span>

<span data-ttu-id="cc4e7-119">En el ejemplo siguiente se define un procedimiento que tiene un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-119">The following example defines a procedure that has an optional parameter.</span></span>

```vb
Public Function FindMatches(ByRef values As List(Of String),
                            ByVal searchString As String,
                            Optional ByVal matchCase As Boolean = False) As List(Of String)

    Dim results As IEnumerable(Of String)

    If matchCase Then
        results = From v In values
                  Where v.Contains(searchString)
    Else
        results = From v In values
                  Where UCase(v).Contains(UCase(searchString))
    End If

    Return results.ToList()
End Function
```

## <a name="example"></a><span data-ttu-id="cc4e7-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc4e7-120">Example</span></span>

<span data-ttu-id="cc4e7-121">En el ejemplo siguiente se muestra cómo llamar a un procedimiento con argumentos pasados por posición y con argumentos pasados por nombre.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="cc4e7-122">El procedimiento tiene dos parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="cc4e7-122">The procedure has two optional parameters.</span></span>

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a><span data-ttu-id="cc4e7-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc4e7-123">See also</span></span>

- [<span data-ttu-id="cc4e7-124">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="cc4e7-124">Parameter List</span></span>](../statements/parameter-list.md)
- [<span data-ttu-id="cc4e7-125">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="cc4e7-125">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="cc4e7-126">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="cc4e7-126">Keywords</span></span>](../keywords/index.md)
