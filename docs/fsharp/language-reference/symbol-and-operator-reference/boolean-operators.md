---
title: Operadores booleanos (F#)
description: "Obtenga información acerca de los operadores booleanos que están disponibles en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="boolean-operators"></a><span data-ttu-id="90f2a-104">Operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="90f2a-104">Boolean Operators</span></span>

<span data-ttu-id="90f2a-105">En este tema se describe la compatibilidad con los operadores booleanos en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="90f2a-105">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="90f2a-106">Resumen de operadores booleanos</span><span class="sxs-lookup"><span data-stu-id="90f2a-106">Summary of Boolean Operators</span></span>
<span data-ttu-id="90f2a-107">En la tabla siguiente se resume los operadores booleanos que están disponibles en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="90f2a-107">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="90f2a-108">Es el único tipo admitido por estos operadores el `bool` tipo.</span><span class="sxs-lookup"><span data-stu-id="90f2a-108">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="90f2a-109">Operador</span><span class="sxs-lookup"><span data-stu-id="90f2a-109">Operator</span></span>|<span data-ttu-id="90f2a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="90f2a-110">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="90f2a-111">Negación booleana</span><span class="sxs-lookup"><span data-stu-id="90f2a-111">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="90f2a-112">OR booleano</span><span class="sxs-lookup"><span data-stu-id="90f2a-112">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="90f2a-113">AND booleano</span><span class="sxs-lookup"><span data-stu-id="90f2a-113">Boolean AND</span></span>|

<span data-ttu-id="90f2a-114">Realizan el booleano operadores AND y OR *evaluación cortocircuitada*, es decir, evalúan la expresión situada a la derecha del operador sólo cuando sea necesario determinar el resultado general de la expresión.</span><span class="sxs-lookup"><span data-stu-id="90f2a-114">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="90f2a-115">La segunda expresión de la `&&` operador se evalúa solo si la primera expresión se evalúa como `true`; la segunda expresión de la `||` operador se evalúa solo si la primera expresión se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="90f2a-115">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="90f2a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="90f2a-116">See Also</span></span>
[<span data-ttu-id="90f2a-117">Operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="90f2a-117">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="90f2a-118">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="90f2a-118">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="90f2a-119">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="90f2a-119">Symbol and Operator Reference</span></span>](index.md)
