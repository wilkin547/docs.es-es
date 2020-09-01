---
description: 'Instrucción break: Referencia de C#'
title: 'Instrucción break: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 7fd05889f684f7a2282de8222e1195898dead5b9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134749"
---
# <a name="break-c-reference"></a><span data-ttu-id="a5061-103">break (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a5061-103">break (C# Reference)</span></span>

<span data-ttu-id="a5061-104">La instrucción `break` finaliza la ejecución del bucle contenedor más próximo o de la instrucción [switch](./switch.md) en la que aparezca.</span><span class="sxs-lookup"><span data-stu-id="a5061-104">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="a5061-105">El control se pasa a la instrucción que hay a continuación de la instrucción finalizada, si existe.</span><span class="sxs-lookup"><span data-stu-id="a5061-105">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="a5061-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5061-106">Example</span></span>

<span data-ttu-id="a5061-107">En este ejemplo, la instrucción condicional contiene un contador que se supone que cuenta de 1 a 100. Pero la instrucción `break` finaliza el bucle después de cuatro recuentos.</span><span class="sxs-lookup"><span data-stu-id="a5061-107">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="a5061-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5061-108">Example</span></span>

<span data-ttu-id="a5061-109">En este ejemplo se muestra el uso de `break` en una instrucción [switch](./switch.md).</span><span class="sxs-lookup"><span data-stu-id="a5061-109">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="a5061-110">Si se escribió `4`, la salida será:</span><span class="sxs-lookup"><span data-stu-id="a5061-110">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a><span data-ttu-id="a5061-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5061-111">Example</span></span>

<span data-ttu-id="a5061-112">En este ejemplo, se usa la instrucción `break` para salir de un bucle anidado interno y devolver el control al bucle externo.</span><span class="sxs-lookup"><span data-stu-id="a5061-112">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span> <span data-ttu-id="a5061-113">El control _solo_ se devuelve un nivel hacia arriba en los bucles anidados.</span><span class="sxs-lookup"><span data-stu-id="a5061-113">Control is _only_ returned one level up in the nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="a5061-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5061-114">Example</span></span>

<span data-ttu-id="a5061-115">En este ejemplo, la instrucción `break` solo se usa para salir de la rama actual durante cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="a5061-115">In this example, the `break` statement is only used to break out of the current branch during each iteration of the loop.</span></span> <span data-ttu-id="a5061-116">El propio bucle no se ve afectado por las instancias de `break` que pertenecen a la instrucción anidada [switch](./switch.md).</span><span class="sxs-lookup"><span data-stu-id="a5061-116">The loop itself is unaffected by the instances of `break` that belong to the nested [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="a5061-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a5061-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a5061-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5061-118">See also</span></span>

- [<span data-ttu-id="a5061-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a5061-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a5061-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a5061-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a5061-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a5061-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="a5061-122">switch</span><span class="sxs-lookup"><span data-stu-id="a5061-122">switch</span></span>](./switch.md)
