---
ms.openlocfilehash: 8bcd9987cb061233c8476b9c083a224fc0e25440
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539511"
---
### <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a><span data-ttu-id="99c47-101">Autenticación: Paquetes y API de AzureAD.UI y AzureADB2C.UI marcados como obsoletos</span><span class="sxs-lookup"><span data-stu-id="99c47-101">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>

<span data-ttu-id="99c47-102">En ASP.NET Core 2.1, la integración con la autenticación de Azure Active Directory (Azure AD) y Azure Active Directory B2C (Azure AD B2C) la proporcionan los paquetes [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) y [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI).</span><span class="sxs-lookup"><span data-stu-id="99c47-102">In ASP.NET Core 2.1, integration with Azure Active Directory (Azure AD) and Azure Active Directory B2C (Azure AD B2C) authentication is provided by the [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) and [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) packages.</span></span> <span data-ttu-id="99c47-103">La funcionalidad proporcionada por estos paquetes se basa en el punto de conexión de Azure AD v1.0.</span><span class="sxs-lookup"><span data-stu-id="99c47-103">The functionality provided by these packages is based on the Azure AD v1.0 endpoint.</span></span>

<span data-ttu-id="99c47-104">En ASP.NET Core 5.0 y versiones posteriores, la integración con la autenticación de Azure AD y Azure AD B2C la proporciona el paquete [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web).</span><span class="sxs-lookup"><span data-stu-id="99c47-104">In ASP.NET Core 5.0 and later, integration with Azure AD and Azure AD B2C authentication is provided by the [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) package.</span></span> <span data-ttu-id="99c47-105">Este paquete se basa en la plataforma Microsoft Identity, anteriormente conocida como el punto de conexión de Azure AD v2.0.</span><span class="sxs-lookup"><span data-stu-id="99c47-105">This package is based on the Microsoft Identity Platform, which is formerly known as the Azure AD v2.0 endpoint.</span></span> <span data-ttu-id="99c47-106">Por tanto, las API antiguas de los paquetes `Microsoft.AspNetCore.Authentication.AzureAD.UI` y `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` han quedado en desuso.</span><span class="sxs-lookup"><span data-stu-id="99c47-106">Consequently, the old APIs in the `Microsoft.AspNetCore.Authentication.AzureAD.UI` and `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` packages were deprecated.</span></span>

<span data-ttu-id="99c47-107">Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).</span><span class="sxs-lookup"><span data-stu-id="99c47-107">For discussion, see GitHub issue [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="99c47-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="99c47-108">Version introduced</span></span>

<span data-ttu-id="99c47-109">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="99c47-109">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="99c47-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="99c47-110">Old behavior</span></span>

<span data-ttu-id="99c47-111">Las API no están marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="99c47-111">The APIs weren't marked as obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="99c47-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="99c47-112">New behavior</span></span>

<span data-ttu-id="99c47-113">Las API están marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="99c47-113">The APIs are marked as obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="99c47-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="99c47-114">Reason for change</span></span>

<span data-ttu-id="99c47-115">La funcionalidad de autenticación de Azure AD y Azure AD B2C se ha migrado a las API de la Biblioteca de autenticación de Microsoft (MSAL) proporcionadas por `Microsoft.Identity.Web`.</span><span class="sxs-lookup"><span data-stu-id="99c47-115">The Azure AD and Azure AD B2C authentication functionality was migrated to Microsoft Authentication Library (MSAL) APIs that are provided by `Microsoft.Identity.Web`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="99c47-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="99c47-116">Recommended action</span></span>

<span data-ttu-id="99c47-117">Siga las instrucciones de la API `Microsoft.Identity.Web` para [aplicaciones web](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) y [API web](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span><span class="sxs-lookup"><span data-stu-id="99c47-117">Follow the `Microsoft.Identity.Web` API guidance for [web apps](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) and [web APIs](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span></span>

#### <a name="category"></a><span data-ttu-id="99c47-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="99c47-118">Category</span></span>

<span data-ttu-id="99c47-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="99c47-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="99c47-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="99c47-120">Affected APIs</span></span>

* [<span data-ttu-id="99c47-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="99c47-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="99c47-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span><span class="sxs-lookup"><span data-stu-id="99c47-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="99c47-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span><span class="sxs-lookup"><span data-stu-id="99c47-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [<span data-ttu-id="99c47-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="99c47-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="99c47-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span><span class="sxs-lookup"><span data-stu-id="99c47-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="99c47-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span><span class="sxs-lookup"><span data-stu-id="99c47-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
