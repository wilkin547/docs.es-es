---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394085"
---
### <a name="authentication-google-deprecated-and-replaced"></a><span data-ttu-id="a3824-101">Autenticación: Google+ se ha dejado en desuso y se ha reemplazado</span><span class="sxs-lookup"><span data-stu-id="a3824-101">Authentication: Google+ deprecated and replaced</span></span>

<span data-ttu-id="a3824-102">Google está empezando a [apagar](https://developers.google.com/+/api-shutdown) el inicio de sesión de Google+ en las aplicaciones a partir del 28 de enero de 2019.</span><span class="sxs-lookup"><span data-stu-id="a3824-102">Google is starting to [shut down](https://developers.google.com/+/api-shutdown) Google+ Sign-in for apps as early as January 28, 2019.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a3824-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="a3824-103">Change description</span></span>

<span data-ttu-id="a3824-104">ASP.NET 4.x y ASP.NET Core han estado usando las API de inicio de sesión de Google+ para autenticar a los usuarios de cuentas de Google en las aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="a3824-104">ASP.NET 4.x and ASP.NET Core have been using the Google+ Sign-in APIs to authenticate Google account users in web apps.</span></span> <span data-ttu-id="a3824-105">Los paquetes NuGet afectados son [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) para ASP.NET Core y [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) para `Microsoft.Owin` con ASP.NET Web Forms y MVC.</span><span class="sxs-lookup"><span data-stu-id="a3824-105">The affected NuGet packages are [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) for ASP.NET Core and [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) for `Microsoft.Owin` with ASP.NET Web Forms and MVC.</span></span>

<span data-ttu-id="a3824-106">Las API de reemplazo de Google utilizan un formato y un origen de datos distintos.</span><span class="sxs-lookup"><span data-stu-id="a3824-106">Google's replacement APIs use a different data source and format.</span></span> <span data-ttu-id="a3824-107">Las mitigaciones y soluciones que se proporcionan a continuación tienen en cuenta los cambios estructurales.</span><span class="sxs-lookup"><span data-stu-id="a3824-107">The mitigations and solutions provided below account for the structural changes.</span></span> <span data-ttu-id="a3824-108">Las aplicaciones deben comprobar que los datos en sí cumplen sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="a3824-108">Apps should verify the data itself still satisfies their requirements.</span></span> <span data-ttu-id="a3824-109">Por ejemplo, los nombres, las direcciones de correo electrónico, los vínculos de perfil y las fotos de perfil pueden proporcionar valores ligeramente distintos a los anteriores.</span><span class="sxs-lookup"><span data-stu-id="a3824-109">For example, names, email addresses, profile links, and profile photos may provide subtly different values than before.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a3824-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a3824-110">Version introduced</span></span>

<span data-ttu-id="a3824-111">Todas las versiones.</span><span class="sxs-lookup"><span data-stu-id="a3824-111">All versions.</span></span> <span data-ttu-id="a3824-112">Este cambio es externo a ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a3824-112">This change is external to ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a3824-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a3824-113">Recommended action</span></span>

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a><span data-ttu-id="a3824-114">Owin con ASP.NET Web Forms y MVC</span><span class="sxs-lookup"><span data-stu-id="a3824-114">Owin with ASP.NET Web Forms and MVC</span></span>

<span data-ttu-id="a3824-115">En el caso de `Microsoft.Owin` 3.1.0 y versiones posteriores, se describe una mitigación temporal [aquí](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635).</span><span class="sxs-lookup"><span data-stu-id="a3824-115">For `Microsoft.Owin` 3.1.0 and later, a temporary mitigation is outlined [here](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635).</span></span> <span data-ttu-id="a3824-116">Las aplicaciones deben completar las pruebas con la mitigación para comprobar si hay cambios en el formato de datos.</span><span class="sxs-lookup"><span data-stu-id="a3824-116">Apps should complete testing with the mitigation to check for changes in the data format.</span></span> <span data-ttu-id="a3824-117">Existen planes para lanzar `Microsoft.Owin` 4.0.1 con una corrección.</span><span class="sxs-lookup"><span data-stu-id="a3824-117">There are plans to release `Microsoft.Owin` 4.0.1 with a fix.</span></span> <span data-ttu-id="a3824-118">Las aplicaciones que usen cualquier versión anterior deben actualizarse a la versión 4.0.1.</span><span class="sxs-lookup"><span data-stu-id="a3824-118">Apps using any prior version should update to version 4.0.1.</span></span>

##### <a name="aspnet-core-1x"></a><span data-ttu-id="a3824-119">ASP.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a3824-119">ASP.NET Core 1.x</span></span>

<span data-ttu-id="a3824-120">La mitigación en [Owin con ASP.NET Web Forms y MVC](#owin-with-aspnet-web-forms-and-mvc) puede adaptarse a ASP.NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="a3824-120">The mitigation in [Owin with ASP.NET Web Forms and MVC](#owin-with-aspnet-web-forms-and-mvc) can be adapted to ASP.NET Core 1.x.</span></span> <span data-ttu-id="a3824-121">Las revisiones del paquete NuGet no están planeadas porque 1.x ha alcanzado el estado [final del ciclo de vida](https://dotnet.microsoft.com/platform/support-policy).</span><span class="sxs-lookup"><span data-stu-id="a3824-121">NuGet package patches aren't planned because 1.x has reached [end of life](https://dotnet.microsoft.com/platform/support-policy) status.</span></span>

##### <a name="aspnet-core-2x"></a><span data-ttu-id="a3824-122">ASP.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="a3824-122">ASP.NET Core 2.x</span></span>

<span data-ttu-id="a3824-123">En el caso la versión 2.x de `Microsoft.AspNetCore.Authentication.Google`, reemplace la llamada existente a `AddGoogle` en `Startup.ConfigureServices` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3824-123">For `Microsoft.AspNetCore.Authentication.Google` version 2.x, replace your existing call to `AddGoogle` in `Startup.ConfigureServices` with the following code:</span></span>

```csharp
.AddGoogle(o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.UserInformationEndpoint = "https://www.googleapis.com/oauth2/v2/userinfo";
    o.ClaimActions.Clear();
    o.ClaimActions.MapJsonKey(ClaimTypes.NameIdentifier, "id");
    o.ClaimActions.MapJsonKey(ClaimTypes.Name, "name");
    o.ClaimActions.MapJsonKey(ClaimTypes.GivenName, "given_name");
    o.ClaimActions.MapJsonKey(ClaimTypes.Surname, "family_name");
    o.ClaimActions.MapJsonKey("urn:google:profile", "link");
    o.ClaimActions.MapJsonKey(ClaimTypes.Email, "email");
});
```

<span data-ttu-id="a3824-124">Las revisiones 2.1 y 2.2 de febrero incorporaron la reconfiguración anterior como el nuevo valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a3824-124">The February 2.1 and 2.2 patches incorporated the preceding reconfiguration as the new default.</span></span> <span data-ttu-id="a3824-125">No hay ninguna revisión planeada para ASP.NET Core 2.0 porque ha alcanzado el [final del ciclo de vida](https://dotnet.microsoft.com/platform/support-policy).</span><span class="sxs-lookup"><span data-stu-id="a3824-125">No patch is planned for ASP.NET Core 2.0 since it has reached [end of life](https://dotnet.microsoft.com/platform/support-policy).</span></span>

##### <a name="aspnet-core-30"></a><span data-ttu-id="a3824-126">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a3824-126">ASP.NET Core 3.0</span></span>

<span data-ttu-id="a3824-127">La mitigación proporcionada para ASP.NET Core 2.x también puede usarse para ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a3824-127">The mitigation given for ASP.NET Core 2.x can also be used for ASP.NET Core 3.0.</span></span> <span data-ttu-id="a3824-128">En versiones preliminares futuras de la versión 3.0, se puede quitar el paquete `Microsoft.AspNetCore.Authentication.Google`.</span><span class="sxs-lookup"><span data-stu-id="a3824-128">In future 3.0 previews, the `Microsoft.AspNetCore.Authentication.Google` package may be removed.</span></span> <span data-ttu-id="a3824-129">A los usuarios se les dirigirá a `Microsoft.AspNetCore.Authentication.OpenIdConnect` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a3824-129">Users would be directed to `Microsoft.AspNetCore.Authentication.OpenIdConnect` instead.</span></span> <span data-ttu-id="a3824-130">El código siguiente muestra cómo reemplazar `AddGoogle` por `AddOpenIdConnect` en `Startup.ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="a3824-130">The following code shows how to replace `AddGoogle` with `AddOpenIdConnect` in `Startup.ConfigureServices`.</span></span> <span data-ttu-id="a3824-131">Este reemplazo se puede usar con ASP.NET Core 2.0 y versiones posteriores, y se puede adaptar para ASP.NET Core 1.x, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a3824-131">This replacement can be used with ASP.NET Core 2.0 and later and can be adapted for ASP.NET Core 1.x as needed.</span></span>

```csharp
.AddOpenIdConnect("Google", o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.Authority = "https://accounts.google.com";
    o.ResponseType = OpenIdConnectResponseType.Code;
    o.CallbackPath = "/signin-google"; // Or register the default "/sigin-oidc"
    o.Scope.Add("email");
});
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();
```

#### <a name="category"></a><span data-ttu-id="a3824-132">Categoría</span><span class="sxs-lookup"><span data-stu-id="a3824-132">Category</span></span>

<span data-ttu-id="a3824-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a3824-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a3824-134">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a3824-134">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
