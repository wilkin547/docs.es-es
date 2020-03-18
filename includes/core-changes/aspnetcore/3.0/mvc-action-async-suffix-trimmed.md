---
ms.openlocfilehash: 58b1190e3e6a3168d35700eed655f6756e076a29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901779"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a>MVC: se ha recortado el sufijo Async de los nombres de acción de controlador

Como parte de la solución de [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849), en ASP.NET Core MVC se recorta el sufijo `Async` de los nombres de acción de forma predeterminada. A partir de ASP.NET Core 3.0, este cambio afecta tanto al enrutamiento como a la generación de vínculos.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Tenga en cuenta el siguiente controlador de ASP.NET Core MVC:

```csharp
public class ProductController : Controller
{
    public async IActionResult ListAsync()
    {
        var model = await DbContext.Products.ToListAsync();
        return View(model);
    }
}
```

La acción es enrutable mediante `Product/ListAsync`. La generación de vínculos requiere que se especifique el sufijo `Async`. Por ejemplo:

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a>Comportamiento nuevo

En ASP.NET Core 3.0, la acción es enrutable mediante `Product/List`. El código de generación de vínculos debe omitir el sufijo `Async`. Por ejemplo:

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

Este cambio no afecta a los nombres especificados mediante el atributo `[ActionName]`. El nuevo comportamiento se puede deshabilitar si se establece `MvcOptions.SuppressAsyncSuffixInActionNames` en `false` en `Startup.ConfigureServices`:

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a>Motivo del cambio

Por convención, los métodos asincrónicos de .NET tienen el sufijo `Async`. Pero cuando un método define una acción de MVC, no es recomendable usar el sufijo `Async`.

#### <a name="recommended-action"></a>Acción recomendada

Si la aplicación depende de que las acciones de MVC conserven el sufijo `Async` del nombre, elija una de las mitigaciones siguientes:

- Use el atributo `[ActionName]` para conservar el nombre original.
- Establezca `MvcOptions.SuppressAsyncSuffixInActionNames` en `false` en `Startup.ConfigureServices` para deshabilitar totalmente el cambio de nombre:

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
