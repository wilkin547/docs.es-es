---
title: Operadores booleanos (F#)
description: 'Obtenga información acerca de los operadores booleanos que están disponibles en el lenguaje de programación de F #.'
ms.date: 05/16/2016
ms.openlocfilehash: f8516ceb531907400f98dc4226d2985d3119e9e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563433"
---
# <a name="boolean-operators"></a><span data-ttu-id="1546b-103">Operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="1546b-103">Boolean Operators</span></span>

<span data-ttu-id="1546b-104">En este tema se describe la compatibilidad con los operadores booleanos en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="1546b-104">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="1546b-105">Resumen de operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="1546b-105">Summary of Boolean Operators</span></span>
<span data-ttu-id="1546b-106">En la tabla siguiente se resume los operadores booleanos que están disponibles en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="1546b-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="1546b-107">Es el único tipo admitido por estos operadores el `bool` tipo.</span><span class="sxs-lookup"><span data-stu-id="1546b-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="1546b-108">Operador</span><span class="sxs-lookup"><span data-stu-id="1546b-108">Operator</span></span>|<span data-ttu-id="1546b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1546b-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="1546b-110">Negación booleana</span><span class="sxs-lookup"><span data-stu-id="1546b-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="1546b-111">OR booleano</span><span class="sxs-lookup"><span data-stu-id="1546b-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="1546b-112">AND booleano</span><span class="sxs-lookup"><span data-stu-id="1546b-112">Boolean AND</span></span>|

<span data-ttu-id="1546b-113">Realizan el booleano operadores AND y OR *evaluación cortocircuitada*, es decir, evalúan la expresión situada a la derecha del operador sólo cuando sea necesario determinar el resultado general de la expresión.</span><span class="sxs-lookup"><span data-stu-id="1546b-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="1546b-114">La segunda expresión de la `&&` operador se evalúa solo si la primera expresión se evalúa como `true`; la segunda expresión de la `||` operador se evalúa solo si la primera expresión se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="1546b-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1546b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1546b-115">See Also</span></span>
[<span data-ttu-id="1546b-116">Operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="1546b-116">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="1546b-117">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="1546b-117">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="1546b-118">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="1546b-118">Symbol and Operator Reference</span></span>](index.md)
