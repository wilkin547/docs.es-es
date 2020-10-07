---
ms.openlocfilehash: e450c53008e7562e37518fdfd6872ff9b63b6ac3
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609144"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="989ce-101">Compartir el estado de sesión con StateServer de ASP.NET requiere que todos los servidores de la granja de servidores web usen la misma versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="989ce-101">Sharing session state with ASP.NET StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="989ce-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="989ce-102">Details</span></span>

<span data-ttu-id="989ce-103">Al habilitar el estado de sesión <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>, todos los servidores de la granja de servidores web indicada deben usar la misma versión de .NET Framework para que el estado se comparta correctamente.</span><span class="sxs-lookup"><span data-stu-id="989ce-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="989ce-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="989ce-104">Suggestion</span></span>

<span data-ttu-id="989ce-105">Asegúrese de actualizar las versiones de .NET Framework en los servidores web que compartan el estado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="989ce-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="989ce-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="989ce-106">Name</span></span>    | <span data-ttu-id="989ce-107">Valor</span><span class="sxs-lookup"><span data-stu-id="989ce-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="989ce-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="989ce-108">Scope</span></span>   |<span data-ttu-id="989ce-109">Borde</span><span class="sxs-lookup"><span data-stu-id="989ce-109">Edge</span></span>|
|<span data-ttu-id="989ce-110">Versión</span><span class="sxs-lookup"><span data-stu-id="989ce-110">Version</span></span>|<span data-ttu-id="989ce-111">4.5</span><span class="sxs-lookup"><span data-stu-id="989ce-111">4.5</span></span>|
|<span data-ttu-id="989ce-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="989ce-112">Type</span></span>|<span data-ttu-id="989ce-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="989ce-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="989ce-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="989ce-114">Affected APIs</span></span>

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
