---
ms.openlocfilehash: d7a93cb539baee6a70f75d3afe52fd7546ac2399
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507105"
---
### <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a>Extensiones: cambios en las referencias de paquetes que afectan a algunos paquetes NuGet

Con la migración de algunos paquetes NuGet de `Microsoft.Extensions.*` del repositorio [dotnet/extensions](https://github.com/dotnet/extensions) a [dotnet/runtime](https://github.com/dotnet/runtime), como se describe en [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), se están aplicando cambios en el empaquetado a algunos de los paquetes migrados. Para obtener información sobre esta incidencia, vea [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 4)

#### <a name="old-behavior"></a>Comportamiento anterior

Algunos paquetes de `Microsoft.Extensions.*` incluían referencias de paquete para las API en las que se basaba la aplicación.

#### <a name="new-behavior"></a>Comportamiento nuevo

Es posible que la aplicación tenga que agregar dependencias de paquete de `Microsoft.Extensions.*`.

#### <a name="reason-for-change"></a>Motivo del cambio

Las directivas de empaquetado se actualizaron para alinearse mejor con el repositorio *dotnet/runtime*. Según la nueva directiva, las referencias de paquete sin usar se quitan de los archivos *.nupkg* durante el empaquetado.

#### <a name="recommended-action"></a>Acción recomendada

Los consumidores de los paquetes afectados deben agregar en su proyecto una dependencia directa en la dependencia de paquete quitado si se usan las API de la dependencia de paquete quitada. En la tabla siguiente se enumeran los paquetes afectados y los cambios correspondientes.

|Nombre del paquete|Descripción del cambio|
|------------|------------------|
|[Microsoft.Extensions.Configuration.Binder](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|Se ha quitado la referencia a `Microsoft.Extensions.Configuration`.|
|[Microsoft.Extensions.Configuration.Json](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |Se ha quitado la referencia a `System.Threading.Tasks.Extensions`.|
|[Microsoft.Extensions.Hosting.Abstractions](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|Se ha quitado la referencia a `Microsoft.Extensions.Logging.Abstractions`.|
|[Microsoft.Extensions.Logging](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |Se ha quitado la referencia a `Microsoft.Extensions.Configuration.Binder`.|
|[Microsoft.Extensions.Logging.Console](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |Se ha quitado la referencia a `Microsoft.Extensions.Configuration.Abstractions`.|
|[Microsoft.Extensions.Logging.EventLog](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |Se ha quitado la referencia a `System.Diagnostics.EventLog` para el moniker de la plataforma de destino de .NET Framework 4.6.1.|
|[Microsoft.Extensions.Logging.EventSource](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |Se ha quitado la referencia a `System.Threading.Tasks.Extensions`.|
|[Microsoft.Extensions.Options](https://nuget.org/packages/Microsoft.Extensions.Options)                          |Se ha quitado la referencia a `System.ComponentModel.Annotations`.|

Por ejemplo, la referencia de paquete a `Microsoft.Extensions.Configuration` se ha quitado de `Microsoft.Extensions.Configuration.Binder`. No se ha usado en el paquete ninguna API de la dependencia. Los usuarios de `Microsoft.Extensions.Configuration.Binder` que dependen de las API de `Microsoft.Extensions.Configuration` deben agregar una referencia directa a ella en su proyecto.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!--

#### Affected APIs

Not detectable via API analysis

-->
