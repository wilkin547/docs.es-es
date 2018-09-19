---
title: Aserciones (F#)
description: "Obtenga información sobre cómo usar la expresión 'assert' como una característica de depuración para probar las expresiones en el lenguaje de programación F #."
ms.date: 05/16/2016
ms.openlocfilehash: 85b1e839bfd19bada48b7f1821d15ddd8fa77754
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46000182"
---
# <a name="assertions"></a><span data-ttu-id="eb630-103">Aserciones</span><span class="sxs-lookup"><span data-stu-id="eb630-103">Assertions</span></span>

<span data-ttu-id="eb630-104">El `assert` expresión es una característica de depuración que puede usar para probar una expresión.</span><span class="sxs-lookup"><span data-stu-id="eb630-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="eb630-105">En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.</span><span class="sxs-lookup"><span data-stu-id="eb630-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="eb630-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb630-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="eb630-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb630-107">Remarks</span></span>

<span data-ttu-id="eb630-108">El `assert` expresión tiene el tipo `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="eb630-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="eb630-109">En la sintaxis anterior, *condición* representa una expresión booleana que se va a probar.</span><span class="sxs-lookup"><span data-stu-id="eb630-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="eb630-110">Si la expresión se evalúa como `true`, la ejecución continúa sin ninguna variación.</span><span class="sxs-lookup"><span data-stu-id="eb630-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="eb630-111">Si se evalúa como `false`, se genera un cuadro de diálogo de error del sistema.</span><span class="sxs-lookup"><span data-stu-id="eb630-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="eb630-112">El cuadro de diálogo de error tiene un título que contiene la cadena **error de aserción**.</span><span class="sxs-lookup"><span data-stu-id="eb630-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="eb630-113">El cuadro de diálogo contiene un seguimiento de pila que indica dónde se produjo el error de aserción.</span><span class="sxs-lookup"><span data-stu-id="eb630-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="eb630-114">Comprobación de aserción está habilitada sólo cuando se compila en modo de depuración; es decir, si la constante `DEBUG` está definido.</span><span class="sxs-lookup"><span data-stu-id="eb630-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="eb630-115">En el sistema del proyecto, de forma predeterminada, el `DEBUG` constante se define en la configuración de depuración pero no en la configuración de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="eb630-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="eb630-116">No se puede detectar el error de aserción mediante el uso de control de excepciones de F #.</span><span class="sxs-lookup"><span data-stu-id="eb630-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="eb630-117">El `assert` función se resuelve en <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eb630-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="eb630-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb630-118">Example</span></span>

<span data-ttu-id="eb630-119">El ejemplo de código siguiente muestra el uso de la `assert` expresión.</span><span class="sxs-lookup"><span data-stu-id="eb630-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="eb630-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb630-120">See also</span></span>

- [<span data-ttu-id="eb630-121">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="eb630-121">F# Language Reference</span></span>](index.md)
