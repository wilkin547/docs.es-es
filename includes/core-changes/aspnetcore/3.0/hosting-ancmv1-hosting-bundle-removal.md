---
ms.openlocfilehash: 04e5ca41374fc333a31f0422bc2e89f54b3cb049
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394293"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a><span data-ttu-id="2a862-101">Hospedaje: AspNetCoreModule V1 se ha quitado del conjunto de hospedaje de Windows</span><span class="sxs-lookup"><span data-stu-id="2a862-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>

<span data-ttu-id="2a862-102">A partir de ASP.NET Core 3.0, el conjunto de hospedaje de Windows no incluirá AspNetCoreModule (ANCM) V1.</span><span class="sxs-lookup"><span data-stu-id="2a862-102">Starting with ASP.NET Core 3.0, the Windows Hosting Bundle won't contain AspNetCoreModule (ANCM) V1.</span></span>

<span data-ttu-id="2a862-103">ANCM V2 es compatible con las versiones anteriores de ANCM OutOfProcess y se recomienda para su uso con aplicaciones de ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a862-103">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="2a862-104">Para obtener información, consulte [aspnet/AspNetCore#7095](https://github.com/aspnet/AspNetCore/issues/7095).</span><span class="sxs-lookup"><span data-stu-id="2a862-104">For discussion, see [aspnet/AspNetCore#7095](https://github.com/aspnet/AspNetCore/issues/7095).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2a862-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2a862-105">Version introduced</span></span>

<span data-ttu-id="2a862-106">3.0</span><span class="sxs-lookup"><span data-stu-id="2a862-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2a862-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="2a862-107">Old behavior</span></span>

<span data-ttu-id="2a862-108">ANCM V1 está incluido en el conjunto de hospedaje de Windows.</span><span class="sxs-lookup"><span data-stu-id="2a862-108">ANCM V1 is included in the Windows Hosting Bundle.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2a862-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="2a862-109">New behavior</span></span>

<span data-ttu-id="2a862-110">ANCM V1 no está incluido en el conjunto de hospedaje de Windows.</span><span class="sxs-lookup"><span data-stu-id="2a862-110">ANCM V1 isn't included in the Windows Hosting Bundle.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2a862-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="2a862-111">Reason for change</span></span>

<span data-ttu-id="2a862-112">ANCM V2 es compatible con las versiones anteriores de ANCM OutOfProcess y se recomienda para su uso con aplicaciones de ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a862-112">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2a862-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="2a862-113">Recommended action</span></span>

<span data-ttu-id="2a862-114">Use ANCM V2 con aplicaciones de ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2a862-114">Use ANCM V2 with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="2a862-115">Si se requiere ANCM V1, se puede instalar mediante el conjunto de hospedaje de Windows ASP.NET Core 2.1 o 2.2.</span><span class="sxs-lookup"><span data-stu-id="2a862-115">If ANCM V1 is required, it can be installed using the ASP.NET Core 2.1 or 2.2 Windows Hosting Bundle.</span></span>

<span data-ttu-id="2a862-116">Este cambio interrumpirá las aplicaciones de ASP.NET Core 3.0 que:</span><span class="sxs-lookup"><span data-stu-id="2a862-116">This change will break ASP.NET Core 3.0 apps that:</span></span>

- <span data-ttu-id="2a862-117">Participen del uso de ANCM V1 con `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span><span class="sxs-lookup"><span data-stu-id="2a862-117">Explicitly opted into using ANCM V1 with `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span></span>
- <span data-ttu-id="2a862-118">Tengan un archivo *web.config* personalizado con `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span><span class="sxs-lookup"><span data-stu-id="2a862-118">Have a custom *web.config* file with `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span></span>

#### <a name="category"></a><span data-ttu-id="2a862-119">Categoría</span><span class="sxs-lookup"><span data-stu-id="2a862-119">Category</span></span>

<span data-ttu-id="2a862-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2a862-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2a862-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2a862-121">Affected APIs</span></span>

<span data-ttu-id="2a862-122">None</span><span class="sxs-lookup"><span data-stu-id="2a862-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
