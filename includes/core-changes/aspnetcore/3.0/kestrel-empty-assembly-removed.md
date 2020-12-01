---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032810"
---
### <a name="kestrel-empty-https-assembly-removed"></a>Kestrel: se ha quitado un ensamblado HTTPS vacío

Se ha quitado el ensamblado <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName>.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="reason-for-change"></a>Motivo del cambio

En ASP.NET Core 2.1, el contenido de `Microsoft.AspNetCore.Server.Kestrel.Https` se ha movido a <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>. Este cambio se realizado de forma no interrumpida mediante el uso de atributos de `[TypeForwardedTo]`.

#### <a name="recommended-action"></a>Acción recomendada

- Las bibliotecas que hacen referencia a `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 deben actualizar todas las dependencias de ASP.NET Core a 2.1 o una versión posterior. De lo contrario, se pueden interrumpir cuando se cargan en una aplicación ASP.NET Core 3.0.
- Las aplicaciones y bibliotecas que tienen como destino ASP.NET Core 2.1 y versiones posteriores deben quitar las referencias directas al paquete NuGet `Microsoft.AspNetCore.Server.Kestrel.Https`.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
