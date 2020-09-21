---
ms.openlocfilehash: 62a5f56bb7fffc453623a2c3202f288a19110158
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539514"
---
### <a name="localization-pubternal-apis-removed"></a>Localización: API "Pubternal" quitadas

Para mantener mejor la superficie de la API pública de ASP.NET Core, se han quitado algunas API de localización de :::no-loc text="\"pubternal\"":::. Una API de :::no-loc text="\"pubternal\""::: tiene un modificador de acceso `public` y se define en un espacio de nombres que implica una intención [interna](../../../../docs/csharp/language-reference/keywords/internal.md).

Para obtener información, vea [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 6)

#### <a name="old-behavior"></a>Comportamiento anterior

Las siguientes API eran `public`:

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- El constructor `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` se sobrecarga al aceptar cualquiera de los tipos de parámetro siguientes:
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a>Comportamiento nuevo

En la lista siguiente se describen los cambios:

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper` se ha convertido en `Microsoft.Extensions.Localization.AssemblyWrapper` y ahora es `internal`.
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` se ha convertido en `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` y ahora es `internal`.
- Las sobrecargas del constructor `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` al aceptar cualquiera de los tipos de parámetro siguientes ahora son `internal`:
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a>Motivo del cambio

Se explica de forma más detallada en [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882). Los tipos :::no-loc text="\"pubternal\""::: se han quitado de la superficie de la API de `public`. Estos cambios adaptan más clases a la decisión de diseño mencionada. Las clases en cuestión estaban pensadas como puntos de extensión para las pruebas internas del equipo.

#### <a name="recommended-action"></a>Acción recomendada

Aunque es improbable, algunas aplicaciones pueden depender intencional o accidentalmente de los tipos de :::no-loc text="\"pubternal\"":::. Consulte las secciones de [Nuevo comportamiento](#new-behavior) para determinar cómo realizar la migración para dejar de usar estos tipos.

Si ha identificado un escenario en el que la API pública permitía esto antes del cambio mencionado, pero no lo hace ahora, registre una incidencia en [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
