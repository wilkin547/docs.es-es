---
ms.openlocfilehash: e77312605ee367c159171e305d8f69429f9ac58b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032786"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="a2da3-101">Identidad: se ha quitado la sobrecarga del método AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="a2da3-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="a2da3-102">A partir de ASP.NET Core 3.0, ya no existe la sobrecarga del método [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_).</span><span class="sxs-lookup"><span data-stu-id="a2da3-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a2da3-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a2da3-103">Version introduced</span></span>

<span data-ttu-id="a2da3-104">3.0</span><span class="sxs-lookup"><span data-stu-id="a2da3-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a2da3-105">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a2da3-105">Reason for change</span></span>

<span data-ttu-id="a2da3-106">Este cambio fue el resultado de la adopción de la característica de recursos web estáticos.</span><span class="sxs-lookup"><span data-stu-id="a2da3-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a2da3-107">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a2da3-107">Recommended action</span></span>

<span data-ttu-id="a2da3-108">Llame a <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> en lugar de a la sobrecarga que toma dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="a2da3-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="a2da3-109">Si usa Bootstrap 3, agregue también la línea siguiente a un elemento `<PropertyGroup>` del archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="a2da3-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="a2da3-110">Categoría</span><span class="sxs-lookup"><span data-stu-id="a2da3-110">Category</span></span>

<span data-ttu-id="a2da3-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a2da3-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a2da3-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a2da3-112">Affected APIs</span></span>

[<span data-ttu-id="a2da3-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="a2da3-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
