---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901701"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a>Hospedaje: el host genérico restringe la inserción del constructor de Startup

Los únicos tipos que admite el host genérico para la inserción del constructor de la clase `Startup` son `IHostEnvironment`, `IWebHostEnvironment` e `IConfiguration`. Las aplicaciones que usan `WebHost` no se ven afectadas.

#### <a name="change-description"></a>Descripción del cambio

Antes de ASP.NET Core 3.0, se podía usar la inserción de constructores para tipos arbitrarios en el constructor de la clase `Startup`. En ASP.NET Core 3.0, se ha cambiado la plataforma de la pila web a la biblioteca de host genéricos. Puede ver el cambio en el archivo *Program.cs* de las plantillas:

**ASP.NET Core 2.x:**

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

**ASP.NET Core 3.0:**

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

`Host` usa un contenedor de inserción de dependencias (DI) para compilar la aplicación. `WebHost` usa dos contenedores: uno para el host y otro para la aplicación. Como resultado, el constructor de `Startup` ya no admite la inserción de servicios personalizados. Solo se pueden insertar `IHostEnvironment`, `IWebHostEnvironment` e `IConfiguration`. Este cambio evita problemas de DI, como la creación duplicada de un servicio singleton.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio es consecuencia del cambio de plataforma de la pila web a la biblioteca de host genéricos.

#### <a name="recommended-action"></a>Acción recomendada

Inserte los servicios en la firma del método `Startup.Configure`. Por ejemplo:

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
