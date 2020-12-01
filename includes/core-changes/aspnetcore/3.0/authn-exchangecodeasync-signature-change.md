---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032706"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a>Autenticación: se ha cambiado la firma ExchangeCodeAsync de OAuthHandler

En ASP.NET Core 3.0, la firma de `OAuthHandler.ExchangeCodeAsync` cambió de:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

A:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Las cadenas `code` y `redirectUri` se pasaron como argumentos independientes.

#### <a name="new-behavior"></a>Comportamiento nuevo

`Code` y `RedirectUri` son propiedades de `OAuthCodeExchangeContext` que se pueden establecer mediante el constructor de `OAuthCodeExchangeContext`. El nuevo tipo de `OAuthCodeExchangeContext` es el único argumento que se pasa a `OAuthHandler.ExchangeCodeAsync`.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio permite proporcionar parámetros adicionales de forma no interrumpida. No es necesario crear sobrecargas nuevas de `ExchangeCodeAsync`.

#### <a name="recommended-action"></a>Acción recomendada

Construya un elemento `OAuthCodeExchangeContext` con los valores adecuados de `code` y `redirectUri`. Se debe proporcionar una instancia de <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties>. Esta instancia de `OAuthCodeExchangeContext` única se puede pasar a `OAuthHandler.ExchangeCodeAsync` en lugar de varios argumentos.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
