---
ms.openlocfilehash: dcc64fe651b219ff1416c0afcdb4c6d275160f4b
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "97911637"
---
### <a name="change-in-default-value-of-useshellexecute"></a>Cambio del valor predeterminado de UseShellExecute

<xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> tiene un valor predeterminado de `false` en .NET Core. En .NET Framework, su valor predeterminado es `true`.

#### <a name="change-description"></a>Descripción del cambio

<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> permite iniciar una aplicación directamente, por ejemplo, con código como `Process.Start("mspaint.exe")` que inicia Paint. También permite iniciar indirectamente una aplicación asociada si <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> se establece en `true`. En .NET Framework, el valor predeterminado de <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> es `true`, lo que significa que código como `Process.Start("mytextfile.txt")` iniciaría el Bloc de notas, si ha asociado archivos *.txt* con ese editor. Para evitar el inicio indirecto de una aplicación en .NET Framework, debe establecer explícitamente <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> en `false`. En .NET Core, el valor predeterminado de <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> es `false`. Esto significa que, de forma predeterminada, las aplicaciones asociadas no se inician cuando se llama a `Process.Start`.

Las siguientes propiedades de <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType> solo funcionan cuando <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> es `true`:

- <xref:System.Diagnostics.ProcessStartInfo.CreateNoWindow?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo.ErrorDialog?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo.Verb?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo.WindowStyle?displayProperty=nameWithType>.

Este cambio se introdujo en .NET Core por motivos de rendimiento. Normalmente, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> se usa para iniciar una aplicación directamente. Iniciar una aplicación directamente no implica el uso del shell de Windows e incurrir en el costo de rendimiento asociado. Para que este caso predeterminado sea más rápido, .NET Core cambia el valor predeterminado de <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> por `false`. Puede optar por la ruta de acceso más lenta si lo necesita.

#### <a name="version-introduced"></a>Versión introducida

2.1

> [!NOTE]
> En versiones anteriores de .NET Core, no se implementaba `UseShellExecute` para Windows.

#### <a name="recommended-action"></a>Acción recomendada

Si la aplicación se basa en el comportamiento anterior, llame a <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> con <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> establecido en `true` en el objeto <xref:System.Diagnostics.ProcessStartInfo>.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
