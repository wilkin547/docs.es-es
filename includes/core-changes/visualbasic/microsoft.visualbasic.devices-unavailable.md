---
ms.openlocfilehash: dae4afa92b8833f326b4eacd00b36bb3e1199cc1
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237459"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Los tipos del espacio de nombres Microsoft.VisualBasic.Devices no están disponibles

Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> no están disponibles.

#### <a name="version-introduced"></a>Versión introducida

.NET Core 3.0 (versión preliminar 8)

#### <a name="change-description"></a>Descripción del cambio

Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> estaban disponibles en algunas versiones preliminares de .NET Core 3.0. A partir del SDK de .NET Core 3.0 (versión preliminar 9), ya no están disponibles.

Los tipos se han quitado para evitar dependencias de ensamblado innecesarias o cambios importantes en las versiones posteriores.
 
#### <a name="recommended-action"></a>Acción recomendada

Si su código depende del uso de los tipos <xref:Microsoft.VisualBasic.Devices> y de sus miembros, es posible que pueda usar un tipo o miembro equivalente de la biblioteca de clases .NET. Por ejemplo, los tipos <xref:System.DateTime?displayProperty=nameWithType> y <xref:System.Environment?displayProperty=nameWithType> proporcionan una funcionalidad equivalente a la clase <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType>, y la funcionalidad equivalente a la clase <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> la proporcionan los tipos del espacio de nombres <xref:System.IO.Ports?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

Visual Basic

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

