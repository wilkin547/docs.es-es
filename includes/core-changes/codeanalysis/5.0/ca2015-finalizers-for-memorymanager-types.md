---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065175"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a>CA2015: No definir finalizadores para los tipos derivados de MemoryManager\<T>

La regla [CA2015](/visualstudio/code-quality/ca2015) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para todos los tipos que derivan de <xref:System.Buffers.MemoryManager%601> que definen un finalizador.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2015](/visualstudio/code-quality/ca2015). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.

La regla CA2015 marca los tipos que derivan de <xref:System.Buffers.MemoryManager%601> que definen un finalizador. Agregar un finalizador a un tipo que deriva de <xref:System.Buffers.MemoryManager%601> es probablemente una indicación de un error. Sugiere que un recurso nativo que se podría haber obtenido en un elemento <xref:System.Span%601> se va a limpiar, posiblemente mientras <xref:System.Span%601> lo sigue usando.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

- Quite la definición del finalizador. Para obtener más información, vea [CA2015](/visualstudio/code-quality/ca2015).

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Categoría

Análisis de código

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
