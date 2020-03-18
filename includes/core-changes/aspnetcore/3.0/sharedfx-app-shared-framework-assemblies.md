---
ms.openlocfilehash: a8146db1fb54d63d4716b879ce793f7d817cef59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937291"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a>Marco compartido: se han quitado los ensamblados de Microsoft.AspNetCore.App

A partir de ASP.NET Core 3.0, el marco compartido de ASP.NET Core (`Microsoft.AspNetCore.App`) solo contiene ensamblados propios totalmente desarrollados, admitidos y mantenidos por Microsoft.

#### <a name="change-description"></a>Descripción del cambio

Considere el cambio como la redefinición de los límites de la "plataforma" ASP.NET Core. [A través de GitHub, cualquier usuario puede compilar el código fuente](https://github.com/dotnet/source-build) del marco compartido y seguirá ofreciendo a las aplicaciones las ventajas existentes de los marcos compartidos de .NET Core. Algunas ventajas son el tamaño de implementación más pequeño, la revisión centralizada y el tiempo de inicio más rápido.

Como parte del cambio, en `Microsoft.AspNetCore.App` se han introducido algunos cambios importantes.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Los proyectos hacían referencia a `Microsoft.AspNetCore.App` mediante un elemento `<PackageReference>` en el archivo de proyecto.

Además, `Microsoft.AspNetCore.App` incluía los subcomponentes siguientes:

- Json.NET (`Newtonsoft.Json`)
- Entity Framework Core (ensamblados con el prefijo `Microsoft.EntityFrameworkCore.`)
- Roslyn (`Microsoft.CodeAnalysis`)

#### <a name="new-behavior"></a>Comportamiento nuevo

Una referencia a `Microsoft.AspNetCore.App` ya no requiere un elemento `<PackageReference>` en el archivo de proyecto. El SDK de .NET Core admite un nuevo elemento denominado `<FrameworkReference>`, que reemplaza el uso de `<PackageReference>`.

Para obtener más información, vea [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612).

Entity Framework Core se distribuye como paquetes NuGet. Este cambio alinea el modelo de envío con el resto de las bibliotecas de acceso a datos de .NET. Proporciona a Entity Framework Core la ruta más sencilla para continuar con la innovación al tiempo que admite las distintas plataformas .NET. La exclusión de Entity Framework Core del marco compartido no tiene ningún impacto en su estado como biblioteca desarrollada, admitida y mantenida por Microsoft. Continúa bajo la cobertura de la [directiva de compatibilidad de .NET Core](https://www.microsoft.com/net/platform/support-policy).

Json.NET y Entity Framework Core siguen funcionando con ASP.NET Core. Pero no se incluirán en el marco compartido.

Para obtener más información, vea [El futuro de JSON en .NET Core 3.0](https://github.com/dotnet/announcements/issues/90). Vea también [la lista completa de archivos binarios](https://github.com/dotnet/aspnetcore/issues/3755) que se han quitado del marco compartido.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio simplifica el consumo de `Microsoft.AspNetCore.App` y reduce la duplicación entre paquetes NuGet y marcos compartidos.

Para obtener más información sobre la motivación de este cambio, vea [esta entrada de blog](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).

#### <a name="recommended-action"></a>Acción recomendada

No será necesario que los proyectos consuman ensamblados en `Microsoft.AspNetCore.App` como paquetes NuGet. Para simplificar la selección como destino y el uso del marco compartido de ASP.NET Core, ya no se generan muchos paquetes NuGet enviados desde ASP.NET Core 1.0. Las API que proporcionan esos paquetes siguen estando disponibles para las aplicaciones mediante el uso de un elemento `<FrameworkReference>` para `Microsoft.AspNetCore.App`. Entre los ejemplos de API comunes se incluyen Kestrel, MVC y Razor.

Este cambio no se aplica a todos los archivos binarios a los que se hace referencia a través de `Microsoft.AspNetCore.App` en ASP.NET Core 2.x. Entre las excepciones destacables se incluyen las siguientes:

- Las bibliotecas de `Microsoft.Extensions` que todavía tienen .NET Standard como destino estarán disponibles como paquetes NuGet (vea https://github.com/dotnet/extensions) ).
- API generadas por el equipo de ASP.NET Core que no forman parte de `Microsoft.AspNetCore.App`. Por ejemplo, los componentes siguientes están disponibles como paquetes NuGet:
  - Entity Framework Core
  - API que proporcionan integración de terceros
  - Características experimentales
  - API con dependencias que no han podido [cumplir los requisitos para ser incluidas en el marco compartido](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)
- Extensiones para MVC que mantienen la compatibilidad con Json.NET. Se proporcionará una API como paquete NuGet para admitir el uso de Json.NET y MVC.
- El cliente de SignalR para .NET seguirá admitiendo .NET Standard y se enviará como un paquete NuGet. Está diseñado para usarse en muchos entornos de ejecución de .NET, como Xamarin y UWP.

Para obtener más información, vea [Detección de la generación de paquetes para ensamblados de marco compartido en 3.0](https://github.com/dotnet/aspnetcore/issues/3756). Para obtener información, vea [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757).

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.CodeAnalysis?displayProperty=nameWithType>
- <xref:Microsoft.EntityFrameworkCore?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.CodeAnalysis`
- `N:Microsoft.EntityFrameworkCore`

-->
