---
ms.openlocfilehash: 8d7942ef6c36c01a9ae7ae2a9739f26dfcda5813
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394360"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a>Identity: la interfaz de usuario usa la característica de recursos web estáticos

ASP.NET Core 3.0 ha presentado una característica de recursos web estáticos y la interfaz de usuario de Identity la ha adoptado.

#### <a name="change-description"></a>Descripción del cambio

Como resultado de la interfaz de usuario de Identity que adopta la característica de recursos web estáticos:

- La selección del marco se realiza mediante el uso de la propiedad `IdentityUIFrameworkVersion` en el archivo del proyecto.
- Bootstrap 4 es el marco de la interfaz de usuario predeterminado para la interfaz de usuario de Identity. Bootstrap 3 ha alcanzado el final del ciclo de vida y debe considerar la posibilidad de migrar a una versión compatible.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

El marco de la interfaz de usuario predeterminado para la interfaz de usuario de Identity era **Bootstrap 3**. El marco de la interfaz de usuario se puede configurar mediante un parámetro para la llamada al método `AddIdentityUI` en `Startup.ConfigureServices`.

#### <a name="new-behavior"></a>Comportamiento nuevo

El marco de la interfaz de usuario predeterminado para la interfaz de usuario de Identity es **Bootstrap 4**. El marco de la interfaz de usuario debe configurarse en el archivo del proyecto, en lugar de en la llamada al método `AddIdentityUI`.

#### <a name="reason-for-change"></a>Motivo del cambio

La adopción de la característica de recursos web estáticos requiere que la configuración del marco de la interfaz de usuario se mueva a MSBuild. La decisión sobre qué marco se debe insertar es una decisión en tiempo de compilación, no una decisión en runtime.

#### <a name="recommended-action"></a>Acción recomendada

Revise la interfaz de usuario del sitio para garantizar que los nuevos componentes de Bootstrap 4 son compatibles. En caso necesario, use la propiedad `IdentityUIFrameworkVersion` de MSBuild para revertir a Bootstrap 3. Agregue la propiedad a un elemento `<PropertyGroup>` en el archivo del proyecto:

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)`

-->
