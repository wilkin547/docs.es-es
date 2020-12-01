---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032741"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a><span data-ttu-id="df571-101">Hospedaje: AspNetCoreModule V1 se ha quitado del conjunto de hospedaje de Windows</span><span class="sxs-lookup"><span data-stu-id="df571-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>

<span data-ttu-id="df571-102">A partir de ASP.NET Core 3.0, el conjunto de hospedaje de Windows no incluirá AspNetCoreModule (ANCM) V1.</span><span class="sxs-lookup"><span data-stu-id="df571-102">Starting with ASP.NET Core 3.0, the Windows Hosting Bundle won't contain AspNetCoreModule (ANCM) V1.</span></span>

<span data-ttu-id="df571-103">ANCM V2 es compatible con las versiones anteriores de ANCM OutOfProcess y se recomienda para su uso con aplicaciones de ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="df571-103">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="df571-104">Para obtener información, vea [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).</span><span class="sxs-lookup"><span data-stu-id="df571-104">For discussion, see [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="df571-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="df571-105">Version introduced</span></span>

<span data-ttu-id="df571-106">3.0</span><span class="sxs-lookup"><span data-stu-id="df571-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="df571-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="df571-107">Old behavior</span></span>

<span data-ttu-id="df571-108">ANCM V1 está incluido en el conjunto de hospedaje de Windows.</span><span class="sxs-lookup"><span data-stu-id="df571-108">ANCM V1 is included in the Windows Hosting Bundle.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="df571-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="df571-109">New behavior</span></span>

<span data-ttu-id="df571-110">ANCM V1 no está incluido en el conjunto de hospedaje de Windows.</span><span class="sxs-lookup"><span data-stu-id="df571-110">ANCM V1 isn't included in the Windows Hosting Bundle.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="df571-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="df571-111">Reason for change</span></span>

<span data-ttu-id="df571-112">ANCM V2 es compatible con las versiones anteriores de ANCM OutOfProcess y se recomienda para su uso con aplicaciones de ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="df571-112">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="df571-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="df571-113">Recommended action</span></span>

<span data-ttu-id="df571-114">Use ANCM V2 con aplicaciones de ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="df571-114">Use ANCM V2 with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="df571-115">Si se requiere ANCM V1, se puede instalar mediante el conjunto de hospedaje de Windows ASP.NET Core 2.1 o 2.2.</span><span class="sxs-lookup"><span data-stu-id="df571-115">If ANCM V1 is required, it can be installed using the ASP.NET Core 2.1 or 2.2 Windows Hosting Bundle.</span></span>

<span data-ttu-id="df571-116">Este cambio interrumpirá las aplicaciones de ASP.NET Core 3.0 que:</span><span class="sxs-lookup"><span data-stu-id="df571-116">This change will break ASP.NET Core 3.0 apps that:</span></span>

- <span data-ttu-id="df571-117">Participen del uso de ANCM V1 con `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span><span class="sxs-lookup"><span data-stu-id="df571-117">Explicitly opted into using ANCM V1 with `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span></span>
- <span data-ttu-id="df571-118">Tengan un archivo *web.config* personalizado con `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span><span class="sxs-lookup"><span data-stu-id="df571-118">Have a custom *web.config* file with `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span></span>

#### <a name="category"></a><span data-ttu-id="df571-119">Categoría</span><span class="sxs-lookup"><span data-stu-id="df571-119">Category</span></span>

<span data-ttu-id="df571-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="df571-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="df571-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="df571-121">Affected APIs</span></span>

<span data-ttu-id="df571-122">None</span><span class="sxs-lookup"><span data-stu-id="df571-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
