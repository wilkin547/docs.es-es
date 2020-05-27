---
ms.openlocfilehash: 09027863ff2f0009a14578db35db870c27369726
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721263"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a>Los tipos del espacio de nombres Microsoft.VisualBasic.ApplicationServices no están disponibles

Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> no están disponibles.

#### <a name="version-introduced"></a>Versión introducida

.NET Core 3.0 (versión preliminar 8)

#### <a name="change-description"></a>Descripción del cambio

Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> estaban disponibles en algunas versiones preliminares de .NET Core 3.0. A partir del SDK de .NET Core 3.0 (versión preliminar 9), ya no están disponibles.

Los tipos se han quitado para evitar dependencias de ensamblado innecesarias o cambios importantes en las versiones posteriores.

#### <a name="recommended-action"></a>Acción recomendada

Si su código depende del uso de los tipos <xref:Microsoft.VisualBasic.ApplicationServices> y de sus miembros, es posible que pueda usar un tipo o miembro equivalente de la biblioteca de clases .NET. Por ejemplo, algunos miembros <xref:System.Environment?displayProperty=nameWithType> y <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> proporcionan una funcionalidad equivalente a las propiedades de la clase <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

Visual Basic

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

#### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-->
