---
title: 'Cambio importante: CA2013: No usar ReferenceEquals con tipos de valor'
description: Obtenga información sobre el cambio importante en .NET 5.0 causado por la habilitación de la regla de análisis de código CA2013.
ms.date: 09/03/2020
ms.openlocfilehash: ca2b845427eff547b996b577394c6859e30f50bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760088"
---
# <a name="warning-ca2013-do-not-use-referenceequals-with-value-types"></a>Advertencia CA2013: No usar ReferenceEquals con tipos de valor

La regla [CA2013](/visualstudio/code-quality/ca2013) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para cualquier código donde se usa <xref:System.Object.ReferenceEquals(System.Object,System.Object)> para comparar uno o varios tipos de valor con el fin de determinar si son iguales.

## <a name="change-description"></a>Descripción del cambio

A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2013](/visualstudio/code-quality/ca2013). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.

La regla CA2013 busca instancias en las que se usa <xref:System.Object.ReferenceEquals(System.Object,System.Object)> para comparar uno o varios tipos de valor con el fin de determinar si son iguales. La comparación de los tipos de valor de esta forma para saber si son iguales puede producir resultados incorrectos, ya que se aplica la conversión boxing a los valores antes de compararlos. <xref:System.Object.ReferenceEquals(System.Object,System.Object)> devolverá `false` incluso si los valores comparados representan la misma instancia de un tipo de valor.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

- Cambie el código para usar un operador de igualdad adecuado, por ejemplo, `==`. No debe suprimir esta advertencia.

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>API afectadas

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

### Category

Code analysis

-->
