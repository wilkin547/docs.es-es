---
title: Operadores booleanos
description: Obtenga información sobre los operadores booleanos que están disponibles en el F# lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: 5353b6ec6a0bd610f3446761a1d28f01f0403302
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612743"
---
# <a name="boolean-operators"></a><span data-ttu-id="e179c-103">Operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="e179c-103">Boolean Operators</span></span>

<span data-ttu-id="e179c-104">Este tema describe la compatibilidad con los operadores booleanos en la F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="e179c-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="e179c-105">Resumen de operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="e179c-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="e179c-106">En la tabla siguiente se resume los operadores booleanos que están disponibles en el F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="e179c-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="e179c-107">Es el único tipo admitido por estos operadores el `bool` tipo.</span><span class="sxs-lookup"><span data-stu-id="e179c-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="e179c-108">Operador</span><span class="sxs-lookup"><span data-stu-id="e179c-108">Operator</span></span>|<span data-ttu-id="e179c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e179c-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="e179c-110">Negación booleana</span><span class="sxs-lookup"><span data-stu-id="e179c-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="e179c-111">OR booleano</span><span class="sxs-lookup"><span data-stu-id="e179c-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="e179c-112">AND Boolean</span><span class="sxs-lookup"><span data-stu-id="e179c-112">Boolean AND</span></span>|

<span data-ttu-id="e179c-113">Realizan el booleano operadores AND y OR *la evaluación de cortocircuito*, es decir, evalúa la expresión a la derecha del operador solo cuando sea necesario determinar el resultado global de la expresión.</span><span class="sxs-lookup"><span data-stu-id="e179c-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="e179c-114">La segunda expresión de la `&&` operador se evalúa solo si la primera expresión se evalúa como `true`; la segunda expresión de la `||` operador se evalúa solo si la primera expresión se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="e179c-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e179c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e179c-115">See also</span></span>

- [<span data-ttu-id="e179c-116">Operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="e179c-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="e179c-117">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="e179c-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="e179c-118">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="e179c-118">Symbol and Operator Reference</span></span>](index.md)