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
# <a name="maintainability-rules"></a>Reglas de mantenimiento

Las reglas de mantenimiento admiten el mantenimiento de bibliotecas y aplicaciones.

## <a name="in-this-section"></a>En esta sección

| Regla | Descripción |
|-----------|-----------------------------------|
| [CA1501: Evitar una herencia excesiva](ca1501.md) | Un tipo tiene más de cuatro niveles de profundidad en su jerarquía de herencia. Las jerarquías de tipos con demasiados niveles de anidación pueden resultar difíciles de seguir, comprender y mantener. |
| [CA1502: Evitar una complejidad excesiva](ca1502.md) | Esta regla mide el número de rutas de acceso independientes de forma lineal a través del método, que es determinado por el número y la complejidad de bifurcaciones condicionales. |
| [CA1505: Evitar código que no se puede mantener](ca1505.md) | Un tipo o método tiene un valor del índice de mantenimiento bajo. Un índice de mantenimiento bajo indica que un tipo o método resulta probablemente difícil de mantener y se debería volver a diseñar. |
| [CA1506: Evitar el acoplamiento excesivo de clases](ca1506.md) | Esta regla mide el acoplamiento de clase contando el número de referencias de tipo únicas que contiene un tipo o método. |
| [CA1507: Usar nameof en lugar de la cadena](ca1507.md) | Un literal de cadena se usa como argumento en el que se `nameof` podría utilizar una expresión. |
| [CA1508: Evitar código de condición no alcanzado](ca1508.md) | Un método tiene código condicional que siempre se evalúa como `true` o `false` en tiempo de ejecución. Esto conduce a código muerto en la `false` rama de la condición. |
| [CA1509: Entrada no válida en el archivo de configuración de métricas de código](ca1509.md) | Las reglas de métricas de código, como [CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) y [CA1506](ca1506.md), proporcionan un archivo de configuración denominado `CodeMetricsConfig.txt` que tiene una entrada no válida. |

## <a name="see-also"></a>Vea también

- [Medir la complejidad y el mantenimiento del código administrado](/visualstudio/code-quality/code-metrics-values)
