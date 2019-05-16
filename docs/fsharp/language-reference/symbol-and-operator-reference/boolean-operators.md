---
title: Operadores booleanos
description: Obtenga información sobre los operadores booleanos que están disponibles en el F# lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: ad4bdd1121389f7e280647dbe0c4d0098ffb17df
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641894"
---
# <a name="boolean-operators"></a><span data-ttu-id="017de-103">Operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="017de-103">Boolean Operators</span></span>

<span data-ttu-id="017de-104">Este tema describe la compatibilidad con los operadores booleanos en la F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="017de-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="017de-105">Resumen de operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="017de-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="017de-106">En la tabla siguiente se resume los operadores booleanos que están disponibles en el F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="017de-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="017de-107">Es el único tipo admitido por estos operadores el `bool` tipo.</span><span class="sxs-lookup"><span data-stu-id="017de-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="017de-108">Operador</span><span class="sxs-lookup"><span data-stu-id="017de-108">Operator</span></span>|<span data-ttu-id="017de-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="017de-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="017de-110">Negación booleana</span><span class="sxs-lookup"><span data-stu-id="017de-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="017de-111">OR booleano</span><span class="sxs-lookup"><span data-stu-id="017de-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="017de-112">AND Boolean</span><span class="sxs-lookup"><span data-stu-id="017de-112">Boolean AND</span></span>|

<span data-ttu-id="017de-113">Realizan el booleano operadores AND y OR *la evaluación de cortocircuito*, es decir, evalúa la expresión a la derecha del operador solo cuando sea necesario determinar el resultado global de la expresión.</span><span class="sxs-lookup"><span data-stu-id="017de-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="017de-114">La segunda expresión de la `&&` operador se evalúa solo si la primera expresión se evalúa como `true`; la segunda expresión de la `||` operador se evalúa solo si la primera expresión se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="017de-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="017de-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="017de-115">See also</span></span>

- [<span data-ttu-id="017de-116">Operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="017de-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="017de-117">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="017de-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="017de-118">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="017de-118">Symbol and Operator Reference</span></span>](index.md)
