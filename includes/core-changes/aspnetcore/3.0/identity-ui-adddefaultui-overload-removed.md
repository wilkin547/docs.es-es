---
ms.openlocfilehash: 474f039cf00cb48761bfe7b7c4a0a9c6300cd820
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81637202"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="2e4b8-101">Identidad: se ha quitado la sobrecarga del método AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="2e4b8-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="2e4b8-102">A partir de ASP.NET Core 3.0, ya no existe la sobrecarga del método [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_).</span><span class="sxs-lookup"><span data-stu-id="2e4b8-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2e4b8-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2e4b8-103">Version introduced</span></span>

<span data-ttu-id="2e4b8-104">3.0</span><span class="sxs-lookup"><span data-stu-id="2e4b8-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2e4b8-105">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="2e4b8-105">Reason for change</span></span>

<span data-ttu-id="2e4b8-106">Este cambio fue el resultado de la adopción de la característica de recursos web estáticos.</span><span class="sxs-lookup"><span data-stu-id="2e4b8-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2e4b8-107">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="2e4b8-107">Recommended action</span></span>

<span data-ttu-id="2e4b8-108">Llame a <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> en lugar de a la sobrecarga que toma dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="2e4b8-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="2e4b8-109">Si usa Bootstrap 3, agregue también la línea siguiente a un elemento `<PropertyGroup>` del archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="2e4b8-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="2e4b8-110">Categoría</span><span class="sxs-lookup"><span data-stu-id="2e4b8-110">Category</span></span>

<span data-ttu-id="2e4b8-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2e4b8-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2e4b8-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2e4b8-112">Affected APIs</span></span>

[<span data-ttu-id="2e4b8-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="2e4b8-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
