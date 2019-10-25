---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522665"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="42bc3-101">Identidad: se ha quitado la sobrecarga del método AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="42bc3-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="42bc3-102">A partir de ASP.NET Core 3.0, ya no existe la sobrecarga del método <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="42bc3-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="42bc3-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="42bc3-103">Version introduced</span></span>

<span data-ttu-id="42bc3-104">3.0</span><span class="sxs-lookup"><span data-stu-id="42bc3-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="42bc3-105">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="42bc3-105">Reason for change</span></span>

<span data-ttu-id="42bc3-106">Este cambio fue el resultado de la adopción de la característica de recursos web estáticos.</span><span class="sxs-lookup"><span data-stu-id="42bc3-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="42bc3-107">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="42bc3-107">Recommended action</span></span>

<span data-ttu-id="42bc3-108">Llame a <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> en lugar de la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="42bc3-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="42bc3-109">Si usa Bootstrap 3, agregue también la línea siguiente a un elemento `<PropertyGroup>` del archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="42bc3-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="42bc3-110">Categoría</span><span class="sxs-lookup"><span data-stu-id="42bc3-110">Category</span></span>

<span data-ttu-id="42bc3-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="42bc3-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="42bc3-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="42bc3-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
