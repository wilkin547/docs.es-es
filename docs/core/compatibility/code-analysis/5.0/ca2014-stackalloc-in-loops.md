---
title: 'Cambio importante: CA2014: No usar stackalloc en los bucles'
description: Obtenga información sobre el cambio importante en .NET 5.0 causado por la habilitación de la regla de análisis de código CA2014.
ms.date: 09/03/2020
ms.openlocfilehash: 7ad6203c0edd930bbbe43cdb8df0413cba833d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760087"
---
# <a name="warning-ca2014-do-not-use-stackalloc-in-loops"></a>Advertencia CA2014: No usar stackalloc en los bucles

La regla [CA2014](/visualstudio/code-quality/ca2014) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para cualquier código de C# donde se usa una expresión [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) dentro de un bucle.

## <a name="change-description"></a>Descripción del cambio

A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2014](/visualstudio/code-quality/ca2014). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.

La regla CA2014 busca código de C# en el que se usa una [expresión stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) dentro de un bucle. [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) asigna memoria del marco de pila actual. La memoria no se libera hasta que se devuelve la llamada al método actual, lo que puede provocar desbordamientos de pila. Como las excepciones de desbordamiento de pila no se pueden detectar, la aplicación finalizará en caso de desbordamiento de pila.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

- Evite usar [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) dentro de bucles. Asigne el bloque de memoria fuera de un bucle y vuelva a usarlo dentro del bucle. Para obtener más información, vea [CA2014](/visualstudio/code-quality/ca2014).

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
