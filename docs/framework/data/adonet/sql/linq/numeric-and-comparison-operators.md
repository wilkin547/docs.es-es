---
description: 'Más información sobre: Operadores numéricos y de comparación'
title: Operadores numéricos y de comparación
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 5b17f19769436ac4e575ac974668eadc3b17b8f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695533"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="2913d-103">Operadores numéricos y de comparación</span><span class="sxs-lookup"><span data-stu-id="2913d-103">Numeric and Comparison Operators</span></span>

<span data-ttu-id="2913d-104">Los operadores aritméticos y de comparación funcionan como cabía esperar en Common Language Runtime (CLR), con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="2913d-104">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>

- <span data-ttu-id="2913d-105">SQL no admite al operador de módulo en números de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="2913d-105">SQL does not support the modulus operator on floating-point numbers.</span></span>

- <span data-ttu-id="2913d-106">SQL no admite la aritmética no comprobada.</span><span class="sxs-lookup"><span data-stu-id="2913d-106">SQL does not support unchecked arithmetic.</span></span>

- <span data-ttu-id="2913d-107">Los operadores de incremento y decremento producen efectos no deseados cuando se utilizan en expresiones que no se pueden replicar en SQL y son, por tanto, incompatibles.</span><span class="sxs-lookup"><span data-stu-id="2913d-107">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>

## <a name="supported-operators"></a><span data-ttu-id="2913d-108">Operadores admitidos</span><span class="sxs-lookup"><span data-stu-id="2913d-108">Supported Operators</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="2913d-109">admite los operadores siguientes.</span><span class="sxs-lookup"><span data-stu-id="2913d-109">supports the following operators.</span></span>

- <span data-ttu-id="2913d-110">Operadores aritméticos básicos:</span><span class="sxs-lookup"><span data-stu-id="2913d-110">Basic arithmetic operators:</span></span>

  - `+`

  - <span data-ttu-id="2913d-111">`-` (resta)</span><span class="sxs-lookup"><span data-stu-id="2913d-111">`-` (subtraction)</span></span>

  - `*`

  - `/`

  - <span data-ttu-id="2913d-112">División de enteros en Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="2913d-112">Visual Basic integer division (`\`)</span></span>

  - <span data-ttu-id="2913d-113">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="2913d-113">`%` (Visual Basic `Mod`)</span></span>

  - `<<`

  - `>>`

  - <span data-ttu-id="2913d-114">`-` (negación unaria)</span><span class="sxs-lookup"><span data-stu-id="2913d-114">`-` (unary negation)</span></span>

- <span data-ttu-id="2913d-115">Operadores de comparación básicos:</span><span class="sxs-lookup"><span data-stu-id="2913d-115">Basic comparison operators:</span></span>

  - <span data-ttu-id="2913d-116">`=` en Visual Basic y `==` en C#</span><span class="sxs-lookup"><span data-stu-id="2913d-116">Visual Basic `=` and C# `==`</span></span>

  - <span data-ttu-id="2913d-117">`<>` en Visual Basic y `!=` en C#</span><span class="sxs-lookup"><span data-stu-id="2913d-117">Visual Basic `<>` and C# `!=`</span></span>

  - <span data-ttu-id="2913d-118">`Is/IsNot` en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2913d-118">Visual Basic `Is/IsNot`</span></span>

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a><span data-ttu-id="2913d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2913d-119">See also</span></span>

- [<span data-ttu-id="2913d-120">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="2913d-120">Data Types and Functions</span></span>](data-types-and-functions.md)
- [<span data-ttu-id="2913d-121">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="2913d-121">C# Operators</span></span>](../../../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="2913d-122">Operadores</span><span class="sxs-lookup"><span data-stu-id="2913d-122">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
