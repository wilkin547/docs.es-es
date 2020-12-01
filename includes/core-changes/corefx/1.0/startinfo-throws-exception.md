---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032062"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a>Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron

Al leer la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> de los procesos que el código no ha iniciado, se produce una excepción <xref:System.InvalidOperationException>.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework, el acceso a la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> para los procesos que el código no inició devuelve un objeto <xref:System.Diagnostics.ProcessStartInfo> ficticio. El objeto ficticio contiene los valores predeterminados de todas sus propiedades excepto <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.

A partir de .NET Core 1,0, si lee la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> de un proceso que no se inició (es decir, mediante la llamada a <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>), se produce una excepción <xref:System.InvalidOperationException>.

#### <a name="version-introduced"></a>Versión introducida

1.0

#### <a name="recommended-action"></a>Acción recomendada

No acceda a la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> de los procesos que el código no ha iniciado. Por ejemplo, no lea esta propiedad de los procesos devueltos por <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
