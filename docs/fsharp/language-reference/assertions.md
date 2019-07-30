---
title: Aserciones
description: Aprenda a usar la expresión ' Assert ' como una característica de depuración para probar expresiones F# en el lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630026"
---
# <a name="assertions"></a><span data-ttu-id="24421-103">Aserciones</span><span class="sxs-lookup"><span data-stu-id="24421-103">Assertions</span></span>

<span data-ttu-id="24421-104">La `assert` expresión es una característica de depuración que puede usar para probar una expresión.</span><span class="sxs-lookup"><span data-stu-id="24421-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="24421-105">En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.</span><span class="sxs-lookup"><span data-stu-id="24421-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="24421-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24421-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="24421-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24421-107">Remarks</span></span>

<span data-ttu-id="24421-108">La `assert` expresión tiene el `bool -> unit`tipo.</span><span class="sxs-lookup"><span data-stu-id="24421-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="24421-109">En la sintaxis anterior, *Condition* representa una expresión booleana que se va a probar.</span><span class="sxs-lookup"><span data-stu-id="24421-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="24421-110">Si la expresión se evalúa como `true`, la ejecución continúa inalterada.</span><span class="sxs-lookup"><span data-stu-id="24421-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="24421-111">Si se evalúa como `false`, se genera un cuadro de diálogo de error del sistema.</span><span class="sxs-lookup"><span data-stu-id="24421-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="24421-112">El cuadro de diálogo de error tiene un título que contiene un **error de aserción**de cadena.</span><span class="sxs-lookup"><span data-stu-id="24421-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="24421-113">El cuadro de diálogo contiene un seguimiento de la pila que indica dónde se produjo el error de aserción.</span><span class="sxs-lookup"><span data-stu-id="24421-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="24421-114">La comprobación de aserciones solo está habilitada cuando se compila en modo de depuración; es decir, si se define `DEBUG` la constante.</span><span class="sxs-lookup"><span data-stu-id="24421-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="24421-115">En el sistema del proyecto, de forma predeterminada `DEBUG` , la constante se define en la configuración de depuración, pero no en la configuración de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="24421-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="24421-116">El error de aserción no se puede detectar mediante el F# control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="24421-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="24421-117">La `assert` función se resuelve como <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="24421-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="24421-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24421-118">Example</span></span>

<span data-ttu-id="24421-119">En el ejemplo de código siguiente se muestra el uso `assert` de la expresión.</span><span class="sxs-lookup"><span data-stu-id="24421-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="24421-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="24421-120">See also</span></span>

- [<span data-ttu-id="24421-121">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="24421-121">F# Language Reference</span></span>](index.md)
