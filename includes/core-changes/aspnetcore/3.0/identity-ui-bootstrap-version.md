---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032794"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a>Identity: se ha cambiado la versión de Bootstrap predeterminada de la interfaz de usuario

A partir de ASP.NET Core 3.0, la interfaz de usuario de Identity tiene como valor predeterminado el uso de la versión 4 de Bootstrap.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

La llamada al método `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` era la misma que en `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`.

#### <a name="new-behavior"></a>Comportamiento nuevo

La llamada al método `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` es la misma que en `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`.

#### <a name="reason-for-change"></a>Motivo del cambio

Bootstrap 4 se lanzó durante el periodo de tiempo de ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Acción recomendada

En el caso de que use la interfaz de usuario predeterminada de Identity y la haya agregado en `Startup.ConfigureServices`, este cambio le afectará, como se muestra en el ejemplo siguiente:

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

Realice una de las siguientes acciones:

- Migre su aplicación para usar Bootstrap 4 usando la [guía de migración](https://getbootstrap.com/docs/4.0/migration).
- Actualice `Startup.ConfigureServices` para forzar el uso de Bootstrap 3. Por ejemplo:

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
