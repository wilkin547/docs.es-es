---
ms.openlocfilehash: d61e4da187b3ede5e49fa80903d6e4c3b40578b9
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216280"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a>Los tipos del espacio de nombres Microsoft.VisualBasic.MyServices no están disponibles

Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> no están disponibles.

#### <a name="version-introduced"></a>Versión introducida

.NET Core 3.0 (versión preliminar 8)

#### <a name="details"></a>Detalles

Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> estaban disponibles en algunas versiones preliminares de .NET Core 3.0. A partir del SDK de .NET Core 3.0 (versión preliminar 9), ya no están disponibles.

Los tipos se han quitado para evitar dependencias de ensamblado innecesarias o cambios importantes en las versiones posteriores.
 
#### <a name="recommended-action"></a>Acción recomendada

Si su código depende del uso de los tipos **Microsoft.VisualBasic.MyServices** de y sus miembros, hay tipos y miembros correspondientes en la biblioteca de clases .NET. Lo siguiente es una relación de tipos **Microsoft.VisualBasic.MyServices** y de sus tipos equivalentes en la biblioteca de clases .NET:

|Tipo Microsoft.VisualBasic.MyServices|Tipo de la biblioteca de clases .NET|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<xref:System.Windows.Clipboard?displayProperty=nameWithType> para las aplicaciones de WPF y <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> para aplicaciones de Windows Forms| 
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|Tipos del espacio de nombres <xref:System.IO>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|Tipos relacionados con el registro en el espacio de nombres <xref:Microsoft.Win32>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a>Categoría

Visual Basic

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

