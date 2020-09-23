---
ms.openlocfilehash: 8bcd9987cb061233c8476b9c083a224fc0e25440
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539511"
---
### <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a>Autenticación: Paquetes y API de AzureAD.UI y AzureADB2C.UI marcados como obsoletos

En ASP.NET Core 2.1, la integración con la autenticación de Azure Active Directory (Azure AD) y Azure Active Directory B2C (Azure AD B2C) la proporcionan los paquetes [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) y [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI). La funcionalidad proporcionada por estos paquetes se basa en el punto de conexión de Azure AD v1.0.

En ASP.NET Core 5.0 y versiones posteriores, la integración con la autenticación de Azure AD y Azure AD B2C la proporciona el paquete [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web). Este paquete se basa en la plataforma Microsoft Identity, anteriormente conocida como el punto de conexión de Azure AD v2.0. Por tanto, las API antiguas de los paquetes `Microsoft.AspNetCore.Authentication.AzureAD.UI` y `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` han quedado en desuso.

Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

#### <a name="old-behavior"></a>Comportamiento anterior

Las API no están marcadas como obsoletas.

#### <a name="new-behavior"></a>Comportamiento nuevo

Las API están marcadas como obsoletas.

#### <a name="reason-for-change"></a>Motivo del cambio

La funcionalidad de autenticación de Azure AD y Azure AD B2C se ha migrado a las API de la Biblioteca de autenticación de Microsoft (MSAL) proporcionadas por `Microsoft.Identity.Web`.

#### <a name="recommended-action"></a>Acción recomendada

Siga las instrucciones de la API `Microsoft.Identity.Web` para [aplicaciones web](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) y [API web](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

* [Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
