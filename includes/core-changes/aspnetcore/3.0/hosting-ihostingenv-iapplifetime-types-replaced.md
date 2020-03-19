---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394333"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a>Hospedaje: los tipos IHostingEnvironment e IApplicationLifetime se han marcado como obsoletos y se han reemplazado

Se han introducido tipos nuevos para reemplazar los tipos de `IHostingEnvironment` y `IApplicationLifetime` existentes.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Había dos tipos de `IHostingEnvironment` y `IApplicationLifetime` distintos de `Microsoft.Extensions.Hosting` y `Microsoft.AspNetCore.Hosting`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Los tipos antiguos se han marcado como obsoletos y se han reemplazado por tipos nuevos.

#### <a name="reason-for-change"></a>Motivo del cambio

Cuando `Microsoft.Extensions.Hosting` se presentó en ASP.NET Core 2.1, algunos tipos como `IHostingEnvironment` y `IApplicationLifetime` se copiaron de `Microsoft.AspNetCore.Hosting`. Algunos cambios de ASP.NET Core 3.0 provocan que las aplicaciones incluyan los espacios de nombres `Microsoft.Extensions.Hosting` y `Microsoft.AspNetCore.Hosting`. Cualquier uso de estos tipos duplicados produce un error del compilador de "referencia ambigua" cuando se hace referencia a ambos espacios de nombres.

#### <a name="recommended-action"></a>Acción recomendada

Reemplazados los usos de los tipos anteriores por los tipos recién introducidos, como se indica a continuación:

**Tipos obsoletos (advertencia):**

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

**Tipos nuevos:**

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

Los nuevos métodos de extensión `IsDevelopment` y `IsProduction` de `IHostEnvironment` se encuentran en el espacio de nombres `Microsoft.Extensions.Hosting`. Es posible que sea necesario agregar ese espacio de nombres al proyecto.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
