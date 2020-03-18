---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394356"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a>Identity: SignInAsync produce una excepción para la identidad no autenticada

De forma predeterminada, `SignInAsync` produce una excepción para las entidades de seguridad o identidades en las que `IsAuthenticated` es `false`.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

`SignInAsync` acepta entidades de seguridad e identidades, incluidas las identidades en las que `IsAuthenticated` es `false`.

#### <a name="new-behavior"></a>Comportamiento nuevo

De forma predeterminada, `SignInAsync` produce una excepción para las entidades de seguridad o identidades en las que `IsAuthenticated` es `false`. Hay una nueva marca para suprimir este comportamiento, pero el comportamiento predeterminado ha cambiado.

#### <a name="reason-for-change"></a>Motivo del cambio

El comportamiento anterior era problemático porque, de forma predeterminada, `[Authorize]` / `RequireAuthenticatedUser()` rechazó estas entidades de seguridad.

#### <a name="recommended-action"></a>Acción recomendada

En ASP.NET Core 3.0, versión preliminar 6, hay una marca de `RequireAuthenticatedSignIn` en `AuthenticationOptions` que es `true` de forma predeterminada. Establezca esta marca en `false` para restaurar el comportamiento anterior.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
