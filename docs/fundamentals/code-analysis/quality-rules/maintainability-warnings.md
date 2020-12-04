---
title: Reglas de mantenimiento (análisis de código)
description: Más información sobre las reglas de mantenimiento del análisis de código.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- rules, maintainability
- managed code analysis rules, maintainability rules
- maintainability rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: fc2ef2b42eeba241b7af66b579a60365ad2b88c7
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592408"
---
# <a name="maintainability-rules"></a><span data-ttu-id="7ae3a-103">Reglas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="7ae3a-103">Maintainability rules</span></span>

<span data-ttu-id="7ae3a-104">Las reglas de mantenimiento admiten el mantenimiento de bibliotecas y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-104">Maintainability rules support library and application maintenance.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7ae3a-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7ae3a-105">In this section</span></span>

| <span data-ttu-id="7ae3a-106">Regla</span><span class="sxs-lookup"><span data-stu-id="7ae3a-106">Rule</span></span> | <span data-ttu-id="7ae3a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ae3a-107">Description</span></span> |
|-----------|-----------------------------------|
| [<span data-ttu-id="7ae3a-108">CA1501: Evitar una herencia excesiva</span><span class="sxs-lookup"><span data-stu-id="7ae3a-108">CA1501: Avoid excessive inheritance</span></span>](ca1501.md) | <span data-ttu-id="7ae3a-109">Un tipo tiene más de cuatro niveles de profundidad en su jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-109">A type is more than four levels deep in its inheritance hierarchy.</span></span> <span data-ttu-id="7ae3a-110">Las jerarquías de tipos con demasiados niveles de anidación pueden resultar difíciles de seguir, comprender y mantener.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-110">Deeply nested type hierarchies can be difficult to follow, understand, and maintain.</span></span> |
| [<span data-ttu-id="7ae3a-111">CA1502: Evitar una complejidad excesiva</span><span class="sxs-lookup"><span data-stu-id="7ae3a-111">CA1502: Avoid excessive complexity</span></span>](ca1502.md) | <span data-ttu-id="7ae3a-112">Esta regla mide el número de rutas de acceso independientes de forma lineal a través del método, que es determinado por el número y la complejidad de bifurcaciones condicionales.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-112">This rule measures the number of linearly independent paths through the method, which is determined by the number and complexity of conditional branches.</span></span> |
| [<span data-ttu-id="7ae3a-113">CA1505: Evitar código que no se puede mantener</span><span class="sxs-lookup"><span data-stu-id="7ae3a-113">CA1505: Avoid unmaintainable code</span></span>](ca1505.md) | <span data-ttu-id="7ae3a-114">Un tipo o método tiene un valor del índice de mantenimiento bajo.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-114">A type or method has a low maintainability index value.</span></span> <span data-ttu-id="7ae3a-115">Un índice de mantenimiento bajo indica que un tipo o método resulta probablemente difícil de mantener y se debería volver a diseñar.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-115">A low maintainability index indicates that a type or method is probably difficult to maintain and would be a good candidate for redesign.</span></span> |
| [<span data-ttu-id="7ae3a-116">CA1506: Evitar el acoplamiento excesivo de clases</span><span class="sxs-lookup"><span data-stu-id="7ae3a-116">CA1506: Avoid excessive class coupling</span></span>](ca1506.md) | <span data-ttu-id="7ae3a-117">Esta regla mide el acoplamiento de clase contando el número de referencias de tipo únicas que contiene un tipo o método.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-117">This rule measures class coupling by counting the number of unique type references that a type or method contains.</span></span> |
| [<span data-ttu-id="7ae3a-118">CA1507: Usar nameof en lugar de la cadena</span><span class="sxs-lookup"><span data-stu-id="7ae3a-118">CA1507: Use nameof in place of string</span></span>](ca1507.md) | <span data-ttu-id="7ae3a-119">Un literal de cadena se usa como argumento en el que se `nameof` podría utilizar una expresión.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-119">A string literal is used as an argument where a `nameof` expression could be used.</span></span> |
| [<span data-ttu-id="7ae3a-120">CA1508: Evitar código de condición no alcanzado</span><span class="sxs-lookup"><span data-stu-id="7ae3a-120">CA1508: Avoid dead conditional code</span></span>](ca1508.md) | <span data-ttu-id="7ae3a-121">Un método tiene código condicional que siempre se evalúa como `true` o `false` en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-121">A method has conditional code that always evaluates to `true` or `false` at runtime.</span></span> <span data-ttu-id="7ae3a-122">Esto conduce a código muerto en la `false` rama de la condición.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-122">This leads to dead code in the `false` branch of the condition.</span></span> |
| [<span data-ttu-id="7ae3a-123">CA1509: Entrada no válida en el archivo de configuración de métricas de código</span><span class="sxs-lookup"><span data-stu-id="7ae3a-123">CA1509: Invalid entry in code metrics configuration file</span></span>](ca1509.md) | <span data-ttu-id="7ae3a-124">Las reglas de métricas de código, como [CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) y [CA1506](ca1506.md), proporcionan un archivo de configuración denominado `CodeMetricsConfig.txt` que tiene una entrada no válida.</span><span class="sxs-lookup"><span data-stu-id="7ae3a-124">Code metrics rules, such as [CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) and [CA1506](ca1506.md), supplied a configuration file named `CodeMetricsConfig.txt` that has an invalid entry.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7ae3a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ae3a-125">See also</span></span>

- [<span data-ttu-id="7ae3a-126">Medir la complejidad y el mantenimiento del código administrado</span><span class="sxs-lookup"><span data-stu-id="7ae3a-126">Measure Complexity and Maintainability of Managed Code</span></span>](/visualstudio/code-quality/code-metrics-values)
