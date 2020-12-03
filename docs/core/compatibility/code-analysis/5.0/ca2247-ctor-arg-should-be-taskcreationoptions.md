---
title: 'Cambio importante: CA2247: El argumento para el constructor TaskCompletionSource debe ser el valor TaskCreationOptions'
description: Obtenga información sobre el cambio importante en .NET 5.0 causado por la habilitación de la regla de análisis de código CA2247.
ms.date: 09/03/2020
ms.openlocfilehash: 323fd5a05da4dfeb68ef75d88d5d293ba01c8ade
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760191"
---
# <a name="warning-ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a>Advertencia CA2247: El argumento para el constructor TaskCompletionSource debe ser el valor TaskCreationOptions

La regla [CA2247](/visualstudio/code-quality/ca2247) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para las llamadas al constructor <xref:System.Threading.Tasks.TaskCompletionSource%601> que pasan un argumento de tipo <xref:System.Threading.Tasks.TaskContinuationOptions>.

## <a name="change-description"></a>Descripción del cambio

A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2247](/visualstudio/code-quality/ca2247). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.

La regla CA2247 busca llamadas al constructor <xref:System.Threading.Tasks.TaskCompletionSource%601> que pasan un argumento de tipo <xref:System.Threading.Tasks.TaskContinuationOptions>. El tipo <xref:System.Threading.Tasks.TaskCompletionSource%601> tiene un constructor que acepta un valor <xref:System.Threading.Tasks.TaskCreationOptions> y otro constructor que acepta <xref:System.Object>. Si por accidente se pasa un valor <xref:System.Threading.Tasks.TaskContinuationOptions> en lugar de un valor <xref:System.Threading.Tasks.TaskCreationOptions>, se llama al constructor con el parámetro <xref:System.Object> en tiempo de ejecución. El código se compilará y ejecutará, pero no tendrá el comportamiento previsto.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

- Reemplace el argumento <xref:System.Threading.Tasks.TaskContinuationOptions> por el valor <xref:System.Threading.Tasks.TaskCreationOptions> correspondiente. No suprima esta advertencia, ya que casi siempre resalta un error en el código. Para obtener más información, vea [CA2247](/visualstudio/code-quality/ca2247).

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>API afectadas

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

### Category

Code analysis

-->
