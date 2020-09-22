---
ms.openlocfilehash: e77312605ee367c159171e305d8f69429f9ac58b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539615"
---
### <a name="identity-adddefaultui-method-overload-removed"></a>Identidad: se ha quitado la sobrecarga del método AddDefaultUI

A partir de ASP.NET Core 3.0, ya no existe la sobrecarga del método [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio fue el resultado de la adopción de la característica de recursos web estáticos.

#### <a name="recommended-action"></a>Acción recomendada

Llame a <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> en lugar de a la sobrecarga que toma dos argumentos. Si usa Bootstrap 3, agregue también la línea siguiente a un elemento `<PropertyGroup>` del archivo de proyecto:

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

[IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
