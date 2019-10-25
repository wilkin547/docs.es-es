---
ms.openlocfilehash: 65bac44c84589fb55d2b04c39088c2825c451a6b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393939"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Autorización: la sobrecarga de AddAuthorization se ha cambiado a otro ensamblado

Se ha cambiado a `AddAuthorizationCore` el nombre de los métodos `AddAuthorization` principales que antes se encontraban en `Microsoft.AspNetCore.Authorization`. Los métodos `AddAuthorization` antiguos todavía existen, pero ahora se encuentran en el paquete `Microsoft.AspNetCore.Authorization.Policy`. Las aplicaciones en las que se usen ambos métodos no se verán afectadas. Las aplicaciones en las que no se usaba el paquete de directivas deben cambiar a `AddAuthorizationCore`.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Los métodos `AddAuthorization` existían en `Microsoft.AspNetCore.Authorization`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Los métodos `AddAuthorization` existen en `Microsoft.AspNetCore.Authorization.Policy`. `AddAuthorizationCore` es el nuevo nombre de los métodos antiguos.

#### <a name="reason-for-change"></a>Motivo del cambio

`AddAuthorization` es un nombre de método más indicado para agregar todos los servicios comunes necesarios para la autorización.

#### <a name="recommended-action"></a>Acción recomendada

Agregue una referencia a `Microsoft.AspNetCore.Authorization.Policy` o, en su lugar, use `AddAuthorizationCore`.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
