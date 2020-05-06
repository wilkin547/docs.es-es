---
ms.openlocfilehash: 6deeb7debce9b731f3871b7de0ad8df8a8cdafea
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728295"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a>Localización: se han eliminado la clase ResourceManagerWithCultureStringLocalizer y el miembro de interfaz WithCulture

Se han eliminado la clase [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) y el método [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) en .NET 5.0 (versión preliminar 1).

Para obtener el contexto, consulte [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) y [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324). Para obtener información sobre este cambio, vea [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 1)

#### <a name="old-behavior"></a>Comportamiento anterior

La clase `ResourceManagerWithCultureStringLocalizer` y el método `ResourceManagerStringLocalizer.WithCulture` están [obsoletos en .NET Core 3.0 (versión preliminar 3 y posteriores)](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).

#### <a name="new-behavior"></a>Comportamiento nuevo

La clase `ResourceManagerWithCultureStringLocalizer` y el método `ResourceManagerStringLocalizer.WithCulture` se han quitado de .NET 5.0 (versión preliminar 1). Para ver un inventario de los cambios realizados, consulte la solicitud de incorporación de cambios en [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).

#### <a name="reason-for-change"></a>Motivo del cambio

La clase [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) y el método [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) solían causar confusión a los usuarios de localización. La confusión era más marcada cuando se creaba una implementación de <xref:Microsoft.Extensions.Localization.IStringLocalizer> personalizada. Esta clase y método dan a los consumidores la impresión de que se espera que una instancia de `IStringLocalizer` sea "por idioma y por recurso". En realidad, la instancia solo debe ser "por recurso". En tiempo de ejecución, la propiedad <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> determina el idioma que se va a usar.

#### <a name="recommended-action"></a>Acción recomendada

Deje de usar la clase `ResourceManagerWithCultureStringLocalizer` y el método `ResourceManagerStringLocalizer.WithCulture`.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
