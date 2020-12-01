---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032810"
---
### <a name="kestrel-empty-https-assembly-removed"></a><span data-ttu-id="766ea-101">Kestrel: se ha quitado un ensamblado HTTPS vacío</span><span class="sxs-lookup"><span data-stu-id="766ea-101">Kestrel: Empty HTTPS assembly removed</span></span>

<span data-ttu-id="766ea-102">Se ha quitado el ensamblado <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="766ea-102">The assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> has been removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="766ea-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="766ea-103">Version introduced</span></span>

<span data-ttu-id="766ea-104">3.0</span><span class="sxs-lookup"><span data-stu-id="766ea-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="766ea-105">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="766ea-105">Reason for change</span></span>

<span data-ttu-id="766ea-106">En ASP.NET Core 2.1, el contenido de `Microsoft.AspNetCore.Server.Kestrel.Https` se ha movido a <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="766ea-106">In ASP.NET Core 2.1, the contents of `Microsoft.AspNetCore.Server.Kestrel.Https` were moved to <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span></span> <span data-ttu-id="766ea-107">Este cambio se realizado de forma no interrumpida mediante el uso de atributos de `[TypeForwardedTo]`.</span><span class="sxs-lookup"><span data-stu-id="766ea-107">This change was done in a non-breaking way using `[TypeForwardedTo]` attributes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="766ea-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="766ea-108">Recommended action</span></span>

- <span data-ttu-id="766ea-109">Las bibliotecas que hacen referencia a `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 deben actualizar todas las dependencias de ASP.NET Core a 2.1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="766ea-109">Libraries referencing `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 should update all ASP.NET Core dependencies to 2.1 or later.</span></span> <span data-ttu-id="766ea-110">De lo contrario, se pueden interrumpir cuando se cargan en una aplicación ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="766ea-110">Otherwise, they may break when loaded into an ASP.NET Core 3.0 app.</span></span>
- <span data-ttu-id="766ea-111">Las aplicaciones y bibliotecas que tienen como destino ASP.NET Core 2.1 y versiones posteriores deben quitar las referencias directas al paquete NuGet `Microsoft.AspNetCore.Server.Kestrel.Https`.</span><span class="sxs-lookup"><span data-stu-id="766ea-111">Apps and libraries targeting ASP.NET Core 2.1 and later should remove any direct references to the `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet package.</span></span>

#### <a name="category"></a><span data-ttu-id="766ea-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="766ea-112">Category</span></span>

<span data-ttu-id="766ea-113">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="766ea-113">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="766ea-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="766ea-114">Affected APIs</span></span>

<span data-ttu-id="766ea-115">None</span><span class="sxs-lookup"><span data-stu-id="766ea-115">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
