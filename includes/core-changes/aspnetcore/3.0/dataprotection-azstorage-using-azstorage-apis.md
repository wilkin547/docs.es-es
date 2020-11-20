---
ms.openlocfilehash: f6e4c3d5c5fd020562e48515554136e0f8b6785c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440429"
---
### <a name="data-protection-dataprotectionblobs-uses-new-azure-storage-apis"></a>Protección de datos: uso de nuevas API de Azure Storage por parte de DataProtection.Blobs

`Azure.Extensions.AspNetCore.DataProtection.Blobs` depende de las [bibliotecas de Azure Storage](https://github.com/Azure/azure-storage-net). Estas bibliotecas han cambiado el nombre de los ensamblados, paquetes y espacios de nombres. A partir de ASP.NET Core 3.0, `Azure.Extensions.AspNetCore.DataProtection.Blobs` utiliza las nuevas API y paquetes con prefijo `Azure.Storage.`.

Si tiene preguntas sobre las API de Azure Storage, utilice <https://github.com/Azure/azure-storage-net>. Para obtener información sobre esta incidencia, consulte [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

El paquete hacía referencia al paquete NuGet `WindowsAzure.Storage`.
El paquete hace referencia al paquete NuGet `Microsoft.Azure.Storage.Blob`.

#### <a name="new-behavior"></a>Comportamiento nuevo

El paquete hace referencia al paquete NuGet `Azure.Storage.Blob`.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio permite a `Azure.Extensions.AspNetCore.DataProtection.Blobs` migrar a los paquetes de Azure Storage recomendados.

#### <a name="recommended-action"></a>Acción recomendada

Si todavía necesita usar las API de Azure Storage anteriores con ASP.NET Core 3.0, agregue una dependencia directa al paquete [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) o [Microsoft.Azure.Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/). Este paquete se puede instalar junto con las nuevas API de `Azure.Storage`.

En muchos casos, la actualización solo implica cambiar las instrucciones `using` para usar los espacios de nombres nuevos:

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
- using Microsoft.Azure.Storage;
- using Microsoft.Azure.Storage.Blob;
+ using Azure.Storage;
+ using Azure.Storage.Blobs;
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
