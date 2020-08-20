---
ms.openlocfilehash: e128bdb5735b3e4844356ad4807cc092f6f2b105
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062435"
---
### <a name="no-aw-suffix-probing-on-non-windows-platforms"></a>No se incluye el sondeo del sufijo A/W en plataformas que no son de Windows

Los runtimes de .NET ya no agregan un sufijo `A` o `W` a los nombres de exportación de funciones durante el sondeo de P/Invoke en plataformas que no son de Windows.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 4)

#### <a name="change-description"></a>Descripción del cambio

[Windows tiene la convención](/windows/win32/intl/conventions-for-function-prototypes) de agregar un sufijo `A` o `W` a los nombres de función de Windows SDK. Estos prefijos corresponden a la página de códigos de Windows y a las versiones de Unicode respectivamente.

En versiones anteriores de .NET, los runtimes de CoreCLR y Mono agregan un sufijo `A` o `W` al nombre de la exportación durante la detección de exportación para P/Invokes *en todas las plataformas*.

En .NET 5,0 y versiones posteriores, se agrega un sufijo `A` o `W` al nombre de la exportación durante la detección de exportación *solo en Windows*. En las plataformas UNIX, no se agrega el sufijo. La semántica de los runtimes en la plataforma de Windows no se modifica.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio se ha realizado para simplificar el sondeo entre plataformas. Es algo de lo que no habría que preocuparse, ya que las plataformas que no son de Windows no contienen esta semántica.

#### <a name="recommended-action"></a>Acción recomendada

Para mitigar el cambio, puede agregar manualmente el sufijo deseado en plataformas que no son de Windows. Por ejemplo:

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

#### <a name="category"></a>Categoría

Interop

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

-->
