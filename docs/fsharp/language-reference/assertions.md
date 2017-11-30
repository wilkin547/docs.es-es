---
title: Aserciones (F#)
description: "Obtenga información acerca de cómo usar la expresión 'assert' como una característica de depuración para probar expresiones en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2badaad7-f086-47e7-99c1-91f35117da83
ms.openlocfilehash: 56891769602afaa765ebfe7e7822a179c7a22968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="assertions"></a><span data-ttu-id="66506-104">Aserciones</span><span class="sxs-lookup"><span data-stu-id="66506-104">Assertions</span></span>

<span data-ttu-id="66506-105">El `assert` expresión es una característica de depuración que puede usar para probar una expresión.</span><span class="sxs-lookup"><span data-stu-id="66506-105">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="66506-106">En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.</span><span class="sxs-lookup"><span data-stu-id="66506-106">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="66506-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66506-107">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="66506-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66506-108">Remarks</span></span>

<span data-ttu-id="66506-109">El `assert` expresión tiene el tipo `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="66506-109">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="66506-110">En la sintaxis anterior, *condición* representa una expresión booleana que se va a probar.</span><span class="sxs-lookup"><span data-stu-id="66506-110">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="66506-111">Si la expresión se evalúa como `true`, la ejecución continúa sin ninguna variación.</span><span class="sxs-lookup"><span data-stu-id="66506-111">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="66506-112">Si se evalúa como `false`, se genera un cuadro de diálogo de error de sistema.</span><span class="sxs-lookup"><span data-stu-id="66506-112">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="66506-113">El cuadro de diálogo de error tiene un título que contiene la cadena **error de aserción**.</span><span class="sxs-lookup"><span data-stu-id="66506-113">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="66506-114">El cuadro de diálogo contiene un seguimiento de pila que indica dónde se produjo el error de aserción.</span><span class="sxs-lookup"><span data-stu-id="66506-114">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="66506-115">Comprobación de aserción está habilitada sólo cuando se compila en modo de depuración; es decir, si la constante `DEBUG` se define.</span><span class="sxs-lookup"><span data-stu-id="66506-115">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="66506-116">En el sistema del proyecto, de forma predeterminada, la `DEBUG` constante se define en la configuración de depuración pero no en la configuración de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="66506-116">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="66506-117">No se puede detectar el error de aserción, use el control de excepción de F #.</span><span class="sxs-lookup"><span data-stu-id="66506-117">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="66506-118">El `assert` función se resuelve como <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="66506-118">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="66506-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66506-119">Example</span></span>

<span data-ttu-id="66506-120">En el ejemplo de código siguiente se muestra el uso de la `assert` expresión.</span><span class="sxs-lookup"><span data-stu-id="66506-120">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="66506-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="66506-121">See Also</span></span>

[<span data-ttu-id="66506-122">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="66506-122">F# Language Reference</span></span>](index.md)
