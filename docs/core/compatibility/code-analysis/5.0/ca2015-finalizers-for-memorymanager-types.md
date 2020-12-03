---
title: 'Cambio importante: CA2015: No definir finalizadores para los tipos derivados de MemoryManager<T>'
description: Obtenga información sobre el cambio importante en .NET 5.0 causado por la habilitación de la regla de análisis de código CA2015.
ms.date: 09/03/2020
ms.openlocfilehash: 5d0ba0546b5a72363559f23713c8af4bb4e26e48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760086"
---
# <a name="warning-ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a>Advertencia CA2015: No definir finalizadores para los tipos derivados de MemoryManager\<T>

La regla [CA2015](/visualstudio/code-quality/ca2015) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para todos los tipos que derivan de <xref:System.Buffers.MemoryManager%601> que definen un finalizador.

## <a name="change-description"></a>Descripción del cambio

A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2015](/visualstudio/code-quality/ca2015). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.

La regla CA2015 marca los tipos que derivan de <xref:System.Buffers.MemoryManager%601> que definen un finalizador. Agregar un finalizador a un tipo que deriva de <xref:System.Buffers.MemoryManager%601> es probablemente una indicación de un error. Sugiere que un recurso nativo que se podría haber obtenido en un elemento <xref:System.Span%601> se va a limpiar, posiblemente mientras <xref:System.Span%601> lo sigue usando.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

- Quite la definición del finalizador. Para obtener más información, vea [CA2015](/visualstudio/code-quality/ca2015).

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
