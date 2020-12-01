---
ms.openlocfilehash: ed5a90063b8963d79f412ec1c5c0b9030f980f83
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032789"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Identity: el constructor SignInManager acepta un nuevo parámetro

A partir de ASP.NET Core 3.0, se ha agregado un nuevo parámetro `IUserConfirmation<TUser>` al constructor `SignInManager`. Para obtener más información, consulte [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="reason-for-change"></a>Motivo del cambio

La motivación del cambio consistió en agregar compatibilidad con nuevos flujos de correo electrónico o de confirmación en Identity.

#### <a name="recommended-action"></a>Acción recomendada

Si crea manualmente un elemento `SignInManager`, proporcione una implementación de `IUserConfirmation` o capte una de la inserción de dependencias que se va a proporcionar.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
