---
ms.openlocfilehash: 0fe07ac21effacffc56d37ccb46a121f443acd20
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620545"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="abc05-101">Compartir el estado de sesión con StateServer de ASP.NET requiere que todos los servidores de la granja de servidores web usen la misma versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="abc05-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="abc05-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="abc05-102">Details</span></span>

<span data-ttu-id="abc05-103">Al habilitar el estado de sesión <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>, todos los servidores de la granja de servidores web indicada deben usar la misma versión de .NET Framework para que el estado se comparta correctamente.</span><span class="sxs-lookup"><span data-stu-id="abc05-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="abc05-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="abc05-104">Suggestion</span></span>

<span data-ttu-id="abc05-105">Asegúrese de actualizar las versiones de .NET Framework en los servidores web que compartan el estado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="abc05-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="abc05-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="abc05-106">Name</span></span>    | <span data-ttu-id="abc05-107">Valor</span><span class="sxs-lookup"><span data-stu-id="abc05-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="abc05-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="abc05-108">Scope</span></span>   |<span data-ttu-id="abc05-109">Borde</span><span class="sxs-lookup"><span data-stu-id="abc05-109">Edge</span></span>|
|<span data-ttu-id="abc05-110">Versión</span><span class="sxs-lookup"><span data-stu-id="abc05-110">Version</span></span>|<span data-ttu-id="abc05-111">4.5</span><span class="sxs-lookup"><span data-stu-id="abc05-111">4.5</span></span>|
|<span data-ttu-id="abc05-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="abc05-112">Type</span></span>|<span data-ttu-id="abc05-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="abc05-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="abc05-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="abc05-114">Affected APIs</span></span>

-<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
