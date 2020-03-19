---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394333"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a><span data-ttu-id="c4963-101">Hospedaje: los tipos IHostingEnvironment e IApplicationLifetime se han marcado como obsoletos y se han reemplazado</span><span class="sxs-lookup"><span data-stu-id="c4963-101">Hosting: IHostingEnvironment and IApplicationLifetime types marked obsolete and replaced</span></span>

<span data-ttu-id="c4963-102">Se han introducido tipos nuevos para reemplazar los tipos de `IHostingEnvironment` y `IApplicationLifetime` existentes.</span><span class="sxs-lookup"><span data-stu-id="c4963-102">New types have been introduced to replace existing `IHostingEnvironment` and `IApplicationLifetime` types.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c4963-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c4963-103">Version introduced</span></span>

<span data-ttu-id="c4963-104">3.0</span><span class="sxs-lookup"><span data-stu-id="c4963-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c4963-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="c4963-105">Old behavior</span></span>

<span data-ttu-id="c4963-106">Había dos tipos de `IHostingEnvironment` y `IApplicationLifetime` distintos de `Microsoft.Extensions.Hosting` y `Microsoft.AspNetCore.Hosting`.</span><span class="sxs-lookup"><span data-stu-id="c4963-106">There were two different `IHostingEnvironment` and `IApplicationLifetime` types from `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c4963-107">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="c4963-107">New behavior</span></span>

<span data-ttu-id="c4963-108">Los tipos antiguos se han marcado como obsoletos y se han reemplazado por tipos nuevos.</span><span class="sxs-lookup"><span data-stu-id="c4963-108">The old types have been marked as obsolete and replaced with new types.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c4963-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c4963-109">Reason for change</span></span>

<span data-ttu-id="c4963-110">Cuando `Microsoft.Extensions.Hosting` se presentó en ASP.NET Core 2.1, algunos tipos como `IHostingEnvironment` y `IApplicationLifetime` se copiaron de `Microsoft.AspNetCore.Hosting`.</span><span class="sxs-lookup"><span data-stu-id="c4963-110">When `Microsoft.Extensions.Hosting` was introduced in ASP.NET Core 2.1, some types like `IHostingEnvironment` and `IApplicationLifetime` were copied from `Microsoft.AspNetCore.Hosting`.</span></span> <span data-ttu-id="c4963-111">Algunos cambios de ASP.NET Core 3.0 provocan que las aplicaciones incluyan los espacios de nombres `Microsoft.Extensions.Hosting` y `Microsoft.AspNetCore.Hosting`.</span><span class="sxs-lookup"><span data-stu-id="c4963-111">Some ASP.NET Core 3.0 changes cause apps to include both the `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting` namespaces.</span></span> <span data-ttu-id="c4963-112">Cualquier uso de estos tipos duplicados produce un error del compilador de "referencia ambigua" cuando se hace referencia a ambos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="c4963-112">Any use of those duplicate types causes an "ambiguous reference" compiler error when both namespaces are referenced.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c4963-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c4963-113">Recommended action</span></span>

<span data-ttu-id="c4963-114">Reemplazados los usos de los tipos anteriores por los tipos recién introducidos, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c4963-114">Replaced any usages of the old types with the newly introduced types as below:</span></span>

<span data-ttu-id="c4963-115">**Tipos obsoletos (advertencia):**</span><span class="sxs-lookup"><span data-stu-id="c4963-115">**Obsolete types (warning):**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

<span data-ttu-id="c4963-116">**Tipos nuevos:**</span><span class="sxs-lookup"><span data-stu-id="c4963-116">**New types:**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

<span data-ttu-id="c4963-117">Los nuevos métodos de extensión `IsDevelopment` y `IsProduction` de `IHostEnvironment` se encuentran en el espacio de nombres `Microsoft.Extensions.Hosting`.</span><span class="sxs-lookup"><span data-stu-id="c4963-117">The new `IHostEnvironment` `IsDevelopment` and `IsProduction` extension methods are in the `Microsoft.Extensions.Hosting` namespace.</span></span> <span data-ttu-id="c4963-118">Es posible que sea necesario agregar ese espacio de nombres al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c4963-118">That namespace may need to be added to your project.</span></span>

#### <a name="category"></a><span data-ttu-id="c4963-119">Categoría</span><span class="sxs-lookup"><span data-stu-id="c4963-119">Category</span></span>

<span data-ttu-id="c4963-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c4963-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c4963-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c4963-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
