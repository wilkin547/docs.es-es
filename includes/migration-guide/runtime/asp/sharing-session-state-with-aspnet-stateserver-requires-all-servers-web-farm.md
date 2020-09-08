---
ms.openlocfilehash: 76425ca03c98cd6a23b8366257f9e0d53b486edb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497322"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="7fc53-101">Compartir el estado de sesión con StateServer de ASP.NET requiere que todos los servidores de la granja de servidores web usen la misma versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7fc53-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="7fc53-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="7fc53-102">Details</span></span>

<span data-ttu-id="7fc53-103">Al habilitar el estado de sesión <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>, todos los servidores de la granja de servidores web indicada deben usar la misma versión de .NET Framework para que el estado se comparta correctamente.</span><span class="sxs-lookup"><span data-stu-id="7fc53-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7fc53-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="7fc53-104">Suggestion</span></span>

<span data-ttu-id="7fc53-105">Asegúrese de actualizar las versiones de .NET Framework en los servidores web que compartan el estado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="7fc53-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="7fc53-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="7fc53-106">Name</span></span>    | <span data-ttu-id="7fc53-107">Valor</span><span class="sxs-lookup"><span data-stu-id="7fc53-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7fc53-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="7fc53-108">Scope</span></span>   |<span data-ttu-id="7fc53-109">Borde</span><span class="sxs-lookup"><span data-stu-id="7fc53-109">Edge</span></span>|
|<span data-ttu-id="7fc53-110">Versión</span><span class="sxs-lookup"><span data-stu-id="7fc53-110">Version</span></span>|<span data-ttu-id="7fc53-111">4.5</span><span class="sxs-lookup"><span data-stu-id="7fc53-111">4.5</span></span>|
|<span data-ttu-id="7fc53-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="7fc53-112">Type</span></span>|<span data-ttu-id="7fc53-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7fc53-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7fc53-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7fc53-114">Affected APIs</span></span>

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
