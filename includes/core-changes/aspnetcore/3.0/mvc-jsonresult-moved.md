---
ms.openlocfilehash: 96c2a32dd7cca91e965601d715bbd4625bba439a
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811287"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a>MVC: JsonResult se ha trasladado a Microsoft.AspNetCore.Mvc.Core

`JsonResult` se ha trasladado al ensamblado `Microsoft.AspNetCore.Mvc.Core`. Este tipo se ha usado para definirse en [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json). Se ha agregado un atributo [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) de nivel de ensamblado a `Microsoft.AspNetCore.Mvc.Formatters.Json` para solucionar este problema en la mayoría de los usuarios. Las aplicaciones que usan bibliotecas de terceros pueden encontrar problemas.

#### <a name="version-introduced"></a>Versión introducida

3.0 Preview 6

#### <a name="old-behavior"></a>Comportamiento anterior

Una aplicación que usa una biblioteca basada en la versión 2.2 se compila correctamente.

#### <a name="new-behavior"></a>Comportamiento nuevo

Una aplicación que usa una biblioteca basada en la versión 2.2 produce un error en la compilación. Se proporciona un error que contiene una variación del texto siguiente:

```output
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

Para obtener un ejemplo de este tipo de problema, consulte [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).

#### <a name="reason-for-change"></a>Motivo del cambio

Los cambios en el nivel de plataforma de la composición de ASP.NET Core como se describe en [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).

#### <a name="recommended-action"></a>Acción recomendada

Es posible que sea necesario volver a compilar las bibliotecas compiladas con la versión 2.2 de `Microsoft.AspNetCore.Mvc.Formatters.Json` para solucionar el problema de todos los consumidores. Si se ve afectado, póngase en contacto con el autor de la biblioteca. Solicite volver a compilar la biblioteca para tener como destino ASP.NET Core 3.0.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
