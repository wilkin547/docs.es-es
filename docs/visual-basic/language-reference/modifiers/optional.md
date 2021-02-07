---
description: 'Más información acerca de: opcional (Visual Basic)'
title: Opcional
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: d9a61371364d87745203363dbc0a641cec9660a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666087"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="1cc19-103">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cc19-103">Optional (Visual Basic)</span></span>

<span data-ttu-id="1cc19-104">Especifica que un argumento de procedimiento se puede omitir cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1cc19-104">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>

## <a name="remarks"></a><span data-ttu-id="1cc19-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1cc19-105">Remarks</span></span>

<span data-ttu-id="1cc19-106">Para cada parámetro opcional, debe especificar una expresión constante como valor predeterminado de ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="1cc19-106">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="1cc19-107">Si la expresión se evalúa como [Nothing](../nothing.md), se usa el valor predeterminado del tipo de datos Value como valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="1cc19-107">If the expression evaluates to [Nothing](../nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>

<span data-ttu-id="1cc19-108">Si la lista de parámetros contiene un parámetro opcional, cada parámetro que siga también debe ser opcional.</span><span class="sxs-lookup"><span data-stu-id="1cc19-108">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>

<span data-ttu-id="1cc19-109">El modificador `Optional` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1cc19-109">The `Optional` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="1cc19-110">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="1cc19-110">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="1cc19-111">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="1cc19-111">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="1cc19-112">Property Statement</span><span class="sxs-lookup"><span data-stu-id="1cc19-112">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="1cc19-113">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="1cc19-113">Sub Statement</span></span>](../statements/sub-statement.md)

> [!NOTE]
> <span data-ttu-id="1cc19-114">Cuando se llama a un procedimiento con o sin parámetros opcionales, se pueden pasar argumentos por posición o por nombre.</span><span class="sxs-lookup"><span data-stu-id="1cc19-114">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="1cc19-115">Para obtener más información, vea [pasar argumentos por posición y por nombre](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="1cc19-115">For more information, see [Passing Arguments by Position and by Name](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1cc19-116">También puede definir un procedimiento con parámetros opcionales mediante sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="1cc19-116">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="1cc19-117">Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepte el parámetro y otra que no lo sea.</span><span class="sxs-lookup"><span data-stu-id="1cc19-117">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="1cc19-118">Para obtener más información, consulta [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="1cc19-118">For more information, see [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).</span></span>

## <a name="example"></a><span data-ttu-id="1cc19-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cc19-119">Example</span></span>

<span data-ttu-id="1cc19-120">En el ejemplo siguiente se define un procedimiento que tiene un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="1cc19-120">The following example defines a procedure that has an optional parameter.</span></span>

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

## <a name="example"></a><span data-ttu-id="1cc19-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cc19-121">Example</span></span>

<span data-ttu-id="1cc19-122">En el ejemplo siguiente se muestra cómo llamar a un procedimiento con argumentos pasados por posición y con argumentos pasados por nombre.</span><span class="sxs-lookup"><span data-stu-id="1cc19-122">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="1cc19-123">El procedimiento tiene dos parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="1cc19-123">The procedure has two optional parameters.</span></span>

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a><span data-ttu-id="1cc19-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cc19-124">See also</span></span>

- [<span data-ttu-id="1cc19-125">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="1cc19-125">Parameter List</span></span>](../statements/parameter-list.md)
- [<span data-ttu-id="1cc19-126">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="1cc19-126">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="1cc19-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1cc19-127">Keywords</span></span>](../keywords/index.md)
