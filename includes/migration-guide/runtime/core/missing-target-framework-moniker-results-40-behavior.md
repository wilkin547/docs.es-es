---
ms.openlocfilehash: 49740d3b1890d72935e6e329a4f4be836ed70b25
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496767"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>La ausencia de moniker de la plataforma de destino da lugar a un comportamiento de la versión 4.0

#### <a name="details"></a>Detalles

Las aplicaciones sin un elemento <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> aplicado en el nivel de ensamblado se ejecutarán automáticamente con la semántica (las peculiaridades) de .NET Framework 4.0. Para garantizar una buena calidad, se recomienda que todos los archivos binarios incluyan un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> explícito en el que se indique la versión de .NET Framework con la que se compilaron. Tenga en cuenta que usar un moniker de la plataforma de destino en un archivo de proyecto hará que MSBuild aplique automáticamente un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.

#### <a name="suggestion"></a>Sugerencia

Se debe proporcionar un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>, agregándolo directamente al ensamblado o especificando una plataforma de destino en el [archivo de proyecto, o bien a través de la GUI de propiedades del proyecto de Visual Studio](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Major|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
