---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522665"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="4e418-101">Identidad: se ha quitado la sobrecarga del método AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="4e418-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="4e418-102">A partir de ASP.NET Core 3.0, ya no existe la sobrecarga del método <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4e418-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4e418-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="4e418-103">Version introduced</span></span>

<span data-ttu-id="4e418-104">3.0</span><span class="sxs-lookup"><span data-stu-id="4e418-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4e418-105">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="4e418-105">Reason for change</span></span>

<span data-ttu-id="4e418-106">Este cambio fue el resultado de la adopción de la característica de recursos web estáticos.</span><span class="sxs-lookup"><span data-stu-id="4e418-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4e418-107">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="4e418-107">Recommended action</span></span>

<span data-ttu-id="4e418-108">Llame a <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> en lugar de la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="4e418-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="4e418-109">Si usa Bootstrap 3, agregue también la línea siguiente a un elemento `<PropertyGroup>` del archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="4e418-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="4e418-110">Categoría</span><span class="sxs-lookup"><span data-stu-id="4e418-110">Category</span></span>

<span data-ttu-id="4e418-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4e418-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4e418-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4e418-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
