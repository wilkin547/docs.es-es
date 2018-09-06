---
title: Operadores booleanos (F#)
description: 'Obtenga información sobre los operadores booleanos que están disponibles en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784519"
---
# <a name="boolean-operators"></a><span data-ttu-id="acaad-103">Operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="acaad-103">Boolean Operators</span></span>

<span data-ttu-id="acaad-104">En este tema se describe la compatibilidad con los operadores booleanos en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="acaad-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="acaad-105">Resumen de operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="acaad-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="acaad-106">En la tabla siguiente se resume los operadores booleanos que están disponibles en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="acaad-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="acaad-107">Es el único tipo admitido por estos operadores el `bool` tipo.</span><span class="sxs-lookup"><span data-stu-id="acaad-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="acaad-108">Operador</span><span class="sxs-lookup"><span data-stu-id="acaad-108">Operator</span></span>|<span data-ttu-id="acaad-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="acaad-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="acaad-110">Negación booleana</span><span class="sxs-lookup"><span data-stu-id="acaad-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="acaad-111">OR booleano</span><span class="sxs-lookup"><span data-stu-id="acaad-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="acaad-112">AND Boolean</span><span class="sxs-lookup"><span data-stu-id="acaad-112">Boolean AND</span></span>|

<span data-ttu-id="acaad-113">Realizan el booleano operadores AND y OR *la evaluación de cortocircuito*, es decir, evalúa la expresión a la derecha del operador solo cuando sea necesario determinar el resultado global de la expresión.</span><span class="sxs-lookup"><span data-stu-id="acaad-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="acaad-114">La segunda expresión de la `&&` operador se evalúa solo si la primera expresión se evalúa como `true`; la segunda expresión de la `||` operador se evalúa solo si la primera expresión se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="acaad-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="acaad-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="acaad-115">See also</span></span>

- [<span data-ttu-id="acaad-116">Operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="acaad-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="acaad-117">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="acaad-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="acaad-118">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="acaad-118">Symbol and Operator Reference</span></span>](index.md)
