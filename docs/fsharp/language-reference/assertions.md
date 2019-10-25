---
title: Aserciones
description: Aprenda a usar la expresión ' Assert ' como una característica de depuración para probar expresiones F# en el lenguaje de programación.
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799062"
---
# <a name="assertions"></a><span data-ttu-id="e4ca0-103">Aserciones</span><span class="sxs-lookup"><span data-stu-id="e4ca0-103">Assertions</span></span>

<span data-ttu-id="e4ca0-104">La expresión de `assert` es una característica de depuración que puede usar para probar una expresión.</span><span class="sxs-lookup"><span data-stu-id="e4ca0-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="e4ca0-105">En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.</span><span class="sxs-lookup"><span data-stu-id="e4ca0-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4ca0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4ca0-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="e4ca0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4ca0-107">Remarks</span></span>

<span data-ttu-id="e4ca0-108">La expresión `assert` tiene el tipo `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="e4ca0-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="e4ca0-109">La función `assert` se resuelve como <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4ca0-109">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e4ca0-110">Esto significa que su comportamiento es idéntico a haber llamado a <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> directamente.</span><span class="sxs-lookup"><span data-stu-id="e4ca0-110">This means its behavior is identical to having called <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="e4ca0-111">La comprobación de aserciones solo está habilitada cuando se compila en modo de depuración; es decir, si se define la constante `DEBUG`.</span><span class="sxs-lookup"><span data-stu-id="e4ca0-111">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="e4ca0-112">En el sistema del proyecto, de forma predeterminada, la constante `DEBUG` se define en la configuración de depuración, pero no en la configuración de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="e4ca0-112">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="e4ca0-113">El error de aserción no se puede detectar mediante el F# control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="e4ca0-113">The assertion failure error cannot be caught by using F# exception handling.</span></span>

## <a name="example"></a><span data-ttu-id="e4ca0-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4ca0-114">Example</span></span>

<span data-ttu-id="e4ca0-115">En el ejemplo de código siguiente se muestra el uso de la expresión `assert`.</span><span class="sxs-lookup"><span data-stu-id="e4ca0-115">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="e4ca0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4ca0-116">See also</span></span>

- [<span data-ttu-id="e4ca0-117">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="e4ca0-117">F# Language Reference</span></span>](index.md)
