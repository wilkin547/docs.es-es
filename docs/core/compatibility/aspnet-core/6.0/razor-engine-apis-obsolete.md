---
title: 'Cambio importante: Razor: API de RazorEngine marcadas como obsoletas'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 6.0 titulado Razor: API de RazorEngine marcadas como obsoletas.'
author: scottaddie
ms.author: scaddie
ms.date: 02/09/2021
ms.openlocfilehash: 173ff0ee5c062f050c967c6edc7bed333d1a2031
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488255"
---
# <a name="razor-razorengine-apis-marked-obsolete"></a>Razor: API de RazorEngine marcadas como obsoletas

Los tipos relacionados con el tipo <xref:Microsoft.AspNetCore.Razor.Language.RazorEngine> en Blazor se han marcado como obsoletos.

## <a name="version-introduced"></a>Versión introducida

6.0 (versión preliminar 1)

## <a name="old-behavior"></a>Comportamiento anterior

Las API `RazorEngine` no están obsoletas.

## <a name="new-behavior"></a>Comportamiento nuevo

Las API de `RazorEngine` están obsoletas.

## <a name="reason-for-change"></a>Motivo del cambio

El tipo `RazorEngine` ha quedado en desuso en favor del tipo <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.

## <a name="recommended-action"></a>Acción recomendada

Cambie el código fuente del tipo `RazorEngine` al tipo `RazorProjectEngine`.

## <a name="affected-apis"></a>API afectadas

- [Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.injectdirective.register?view=aspnetcore-3.1&preserve-view=true)
- [Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.functionsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.inheritsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.sectiondirective.register?view=aspnetcore-3.0&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder](/dotnet/api/microsoft.aspnetcore.razor.language.irazorenginebuilder?view=aspnetcore-3.0&preserve-view=true)

<!--

## Category

ASP.NET Core

## Affected APIs

- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register`
- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register`
- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register`
- `T:Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder`

-->
