---
title: Reglas de código innecesario
description: Más información sobre las reglas de código innecesarias del análisis de código
ms.date: 09/30/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 16c4ba0e4bee2388736bf9813a3e8290d8d4da32
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "96594641"
---
# <a name="unnecessary-code-rules"></a><span data-ttu-id="e3227-103">Reglas de código innecesario</span><span class="sxs-lookup"><span data-stu-id="e3227-103">Unnecessary code rules</span></span>

<span data-ttu-id="e3227-104">Las reglas de código innecesarias identifican distintas partes de la base de código que no son necesarias y se pueden refactorizar o quitar.</span><span class="sxs-lookup"><span data-stu-id="e3227-104">Unnecessary code rules identify different parts of the code base that are unnecessary and can be refactored or removed.</span></span> <span data-ttu-id="e3227-105">La presencia de código innecesario indica uno de los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="e3227-105">The presence of unnecessary code indicates one of more of the following problems:</span></span>

- <span data-ttu-id="e3227-106">Legibilidad: código que está desduciendo innecesariamente la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="e3227-106">Readability: Code that is unnecessarily degrading readability.</span></span> <span data-ttu-id="e3227-107">Por ejemplo, [IDE0001](ide0001.md) marca las calificaciones innecesarias de nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="e3227-107">For example, [IDE0001](ide0001.md) flags unnecessary type-name qualifications.</span></span>
- <span data-ttu-id="e3227-108">Mantenimiento: código que ya no se utiliza después de la refactorización y que se mantiene innecesariamente.</span><span class="sxs-lookup"><span data-stu-id="e3227-108">Maintainability: Code that is no longer used after refactoring and is unnecessarily being maintained.</span></span> <span data-ttu-id="e3227-109">Por ejemplo, [IDE0051](ide0051.md) marca los campos, propiedades, eventos y métodos privados sin usar.</span><span class="sxs-lookup"><span data-stu-id="e3227-109">For example, [IDE0051](ide0051.md) flags unused private fields, properties, events, and methods.</span></span>
- <span data-ttu-id="e3227-110">Rendimiento: cálculo innecesario que no tiene efectos secundarios y genera una sobrecarga de rendimiento innecesaria.</span><span class="sxs-lookup"><span data-stu-id="e3227-110">Performance: Unnecessary computation that has no side effects and leads to unnecessary performance overhead.</span></span> <span data-ttu-id="e3227-111">Por ejemplo, [IDE0059](ide0059.md) marca las asignaciones de valores no utilizadas en las que la expresión para calcular un valor no tiene efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="e3227-111">For example, [IDE0059](ide0059.md) flags unused value assignments where the expression to compute a value has no side effects.</span></span>
- <span data-ttu-id="e3227-112">Funcionalidad: problema funcional en el código que hace que el código necesario se represente como redundante.</span><span class="sxs-lookup"><span data-stu-id="e3227-112">Functionality: Functional issue in code leading to required code being rendered redundant.</span></span> <span data-ttu-id="e3227-113">Por ejemplo, [IDE0060](ide0060.md) marca los parámetros no usados en los que el método omite accidentalmente un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="e3227-113">For example, [IDE0060](ide0060.md) flags unused parameters where the method accidentally ignores an input parameter.</span></span>

<span data-ttu-id="e3227-114">Las reglas de esta sección se refieren a las siguientes reglas de código innecesario:</span><span class="sxs-lookup"><span data-stu-id="e3227-114">The rules in this section concern the following unnecessary code rules:</span></span>

- [<span data-ttu-id="e3227-115">Nombre simplificado (IDE0001)</span><span class="sxs-lookup"><span data-stu-id="e3227-115">Simplify name (IDE0001)</span></span>](ide0001.md)
- [<span data-ttu-id="e3227-116">Simplificar el acceso a miembros (IDE0002)</span><span class="sxs-lookup"><span data-stu-id="e3227-116">Simplify member access (IDE0002)</span></span>](ide0002.md)
- [<span data-ttu-id="e3227-117">Quitar conversión innecesaria (IDE0004)</span><span class="sxs-lookup"><span data-stu-id="e3227-117">Remove unnecessary cast (IDE0004)</span></span>](ide0004.md)
- [<span data-ttu-id="e3227-118">Quitar importación innecesaria (IDE0005)</span><span class="sxs-lookup"><span data-stu-id="e3227-118">Remove unnecessary import (IDE0005)</span></span>](ide0005.md)
- [<span data-ttu-id="e3227-119">Quitar código inaccesible (IDE0035)</span><span class="sxs-lookup"><span data-stu-id="e3227-119">Remove unreachable code (IDE0035)</span></span>](ide0035.md)
- [<span data-ttu-id="e3227-120">Quitar miembro privado no utilizado (IDE0051)</span><span class="sxs-lookup"><span data-stu-id="e3227-120">Remove unused private member (IDE0051)</span></span>](ide0051.md)
- [<span data-ttu-id="e3227-121">Quitar miembro privado no leído (IDE0052)</span><span class="sxs-lookup"><span data-stu-id="e3227-121">Remove unread private member (IDE0052)</span></span>](ide0052.md)
- [<span data-ttu-id="e3227-122">Quitar el valor de expresión sin usar (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="e3227-122">Remove unused expression value (IDE0058)</span></span>](ide0058.md)
- [<span data-ttu-id="e3227-123">Quitar la asignación de valores innecesarios (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="e3227-123">Remove unnecessary value assignment (IDE0059)</span></span>](ide0059.md)
- [<span data-ttu-id="e3227-124">Quitar el parámetro sin usar (IDE0060)</span><span class="sxs-lookup"><span data-stu-id="e3227-124">Remove unused parameter (IDE0060)</span></span>](ide0060.md)
- [<span data-ttu-id="e3227-125">Quitar supresión innecesaria (IDE0079)</span><span class="sxs-lookup"><span data-stu-id="e3227-125">Remove unnecessary suppression (IDE0079)</span></span>](ide0079.md)
- <span data-ttu-id="e3227-126">[Quitar el operador de supresión innecesario (IDE0080) (](ide0080.md) solo C#).</span><span class="sxs-lookup"><span data-stu-id="e3227-126">[Remove unnecessary suppression operator (IDE0080)](ide0080.md) - C# only.</span></span>
- <span data-ttu-id="e3227-127">[Quitar ' ByVal ' (IDE0081)](ide0081.md) : solo Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e3227-127">[Remove 'ByVal' (IDE0081)](ide0081.md) - Visual Basic only.</span></span>
- [<span data-ttu-id="e3227-128">Quitar el operador de igualdad innecesario (IDE0100)</span><span class="sxs-lookup"><span data-stu-id="e3227-128">Remove unnecessary equality operator (IDE0100)</span></span>](ide0100.md)
- <span data-ttu-id="e3227-129">[Quitar descartar innecesariamente (IDE0110)](ide0110.md) : solo C#.</span><span class="sxs-lookup"><span data-stu-id="e3227-129">[Remove unnecessary discard (IDE0110)](ide0110.md) - C# only.</span></span>

<span data-ttu-id="e3227-130">Algunas de estas reglas tienen opciones para configurar el comportamiento de la regla:</span><span class="sxs-lookup"><span data-stu-id="e3227-130">Some of these rules have options to configure the rule behavior:</span></span>

- [<span data-ttu-id="e3227-131">csharp_style_unused_value_expression_statement_preference (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="e3227-131">csharp_style_unused_value_expression_statement_preference (IDE0058)</span></span>](ide0058.md#csharp_style_unused_value_expression_statement_preference)
- [<span data-ttu-id="e3227-132">visual_basic_style_unused_value_expression_statement_preference (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="e3227-132">visual_basic_style_unused_value_expression_statement_preference (IDE0058)</span></span>](ide0058.md#visual_basic_style_unused_value_expression_statement_preference)
- [<span data-ttu-id="e3227-133">csharp_style_unused_value_assignment_preference (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="e3227-133">csharp_style_unused_value_assignment_preference (IDE0059)</span></span>](ide0059.md#csharp_style_unused_value_assignment_preference)
- [<span data-ttu-id="e3227-134">visual_basic_style_unused_value_assignment_preference (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="e3227-134">visual_basic_style_unused_value_assignment_preference (IDE0059)</span></span>](ide0059.md#visual_basic_style_unused_value_assignment_preference)
- [<span data-ttu-id="e3227-135">dotnet_code_quality_unused_parameters (IDE0060)</span><span class="sxs-lookup"><span data-stu-id="e3227-135">dotnet_code_quality_unused_parameters (IDE0060)</span></span>](ide0060.md#dotnet_code_quality_unused_parameters)
- [<span data-ttu-id="e3227-136">dotnet_remove_unnecessary_suppression_exclusions (IDE0079)</span><span class="sxs-lookup"><span data-stu-id="e3227-136">dotnet_remove_unnecessary_suppression_exclusions (IDE0079)</span></span>](ide0079.md#dotnet_remove_unnecessary_suppression_exclusions)

## <a name="see-also"></a><span data-ttu-id="e3227-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3227-137">See also</span></span>

- [<span data-ttu-id="e3227-138">Reglas del lenguaje de estilo de código</span><span class="sxs-lookup"><span data-stu-id="e3227-138">Code style language rules</span></span>](language-rules.md)
- [<span data-ttu-id="e3227-139">Referencia de reglas de estilo de código</span><span class="sxs-lookup"><span data-stu-id="e3227-139">Code style rules reference</span></span>](index.md)
