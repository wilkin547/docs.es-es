---
ms.openlocfilehash: 4e937f56f6315ce2abf76dd56989f4d2c4059f22
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065198"
---
### <a name="ca1831-use-asspan-instead-of-range-based-indexers-for-string"></a>CA1831: Uso de AsSpan en lugar de indizadores basados en intervalos para una cadena

La regla [CA1831](/visualstudio/code-quality/ca1831) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para cualquier código donde se usa un indizador basado en <xref:System.Range> en una cadena, pero no está prevista ninguna copia.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA1831](/visualstudio/code-quality/ca1831). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.

La regla CA1831 busca instancias en las que se usa un indizador basado en <xref:System.Range> en una cadena, pero donde no está prevista ninguna copia. Si el indizador basado en <xref:System.Range> se usa directamente en una cadena para generar una conversión implícita, se crea una copia innecesaria de la parte solicitada de la cadena. Por ejemplo:

```csharp
ReadOnlySpan<char> slice = str[1..3];
```

CA1831 sugiere, en su lugar, el uso del indizador basado en <xref:System.Range> en un *intervalo* de la cadena. Por ejemplo:

```csharp
ReadOnlySpan<char> slice = str.AsSpan()[1..3];
```

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

- Para corregir el código y evitar asignaciones innecesarias, llame a <xref:System.MemoryExtensions.AsSpan(System.String)> o <xref:System.MemoryExtensions.AsMemory(System.String)> antes de usar el indizador basado en <xref:System.Range>. Por ejemplo:

  ```csharp
  ReadOnlySpan<char> slice = str.AsSpan()[1..3];
  ```

- Si no quiere cambiar el código, puede deshabilitar la regla estableciendo su gravedad en `suggestion` o en `none`. Para obtener más información, vea el artículo [Configuración de reglas de análisis de código](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md).

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Categoría

Análisis de código

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Range?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Range`

-->
