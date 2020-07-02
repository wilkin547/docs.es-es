---
ms.openlocfilehash: a1db9916c69c5974191eb6108fb54a0d9ff060d2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622134"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a><span data-ttu-id="cf66b-101">Se produce un error de SqlConnection.Open en Windows 7 con presencia de un BSP o LSP de Winsock distinto de IFS</span><span class="sxs-lookup"><span data-stu-id="cf66b-101">SqlConnection.Open fails on Windows 7 with non-IFS Winsock BSP or LSP present</span></span>

#### <a name="details"></a><span data-ttu-id="cf66b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="cf66b-102">Details</span></span>

<span data-ttu-id="cf66b-103">Se produce un error de <xref:System.Data.SqlClient.SqlConnection.Open> y <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> en .NET Framework 4.5 si se ejecutan en un equipo Windows 7 con un Winsock BSP o LSP que no sea IFS en el equipo. Para determinar si está instalado un LSP o BSP distinto de IFS, use el comando <code>netsh WinSock Show Catalog</code> y examine todos los elementos <code>Winsock Catalog Provider Entry</code> que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="cf66b-103"><xref:System.Data.SqlClient.SqlConnection.Open> and <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> fail in the .NET Framework 4.5 if running on a Windows 7 machine with a non-IFS Winsock BSP or LSP are present on the computer.To determine whether a non-IFS BSP or LSP is installed, use the <code>netsh WinSock Show Catalog</code> command, and examine every <code>Winsock Catalog Provider Entry</code> item that is returned.</span></span> <span data-ttu-id="cf66b-104">Si el valor Service Flags tiene establecido el bit <code>0x20000</code>, el proveedor usa controladores IFS y funcionará correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf66b-104">If the Service Flags value has the <code>0x20000</code> bit set, the provider uses IFS handles and will work correctly.</span></span> <span data-ttu-id="cf66b-105">Si el bit <code>0x20000</code> está claro (no establecido), se trata de un BSP o LSP distinto de IFS.</span><span class="sxs-lookup"><span data-stu-id="cf66b-105">If the <code>0x20000</code> bit is clear (not set), it is a non-IFS BSP or LSP.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cf66b-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="cf66b-106">Suggestion</span></span>

<span data-ttu-id="cf66b-107">Este error se corrigió en .NET Framework 4.5.2, por lo que se puede evitar actualizando a una versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf66b-107">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="cf66b-108">También puede evitarse eliminando cualquier LSP de Winsock distinto de IFS que haya instalado.</span><span class="sxs-lookup"><span data-stu-id="cf66b-108">Alternatively, it can be avoided by removing any installed non-IFS Winsock LSPs.</span></span>

| <span data-ttu-id="cf66b-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="cf66b-109">Name</span></span>    | <span data-ttu-id="cf66b-110">Valor</span><span class="sxs-lookup"><span data-stu-id="cf66b-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cf66b-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="cf66b-111">Scope</span></span>   |<span data-ttu-id="cf66b-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="cf66b-112">Minor</span></span>|
|<span data-ttu-id="cf66b-113">Versión</span><span class="sxs-lookup"><span data-stu-id="cf66b-113">Version</span></span>|<span data-ttu-id="cf66b-114">4.5</span><span class="sxs-lookup"><span data-stu-id="cf66b-114">4.5</span></span>|
|<span data-ttu-id="cf66b-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="cf66b-115">Type</span></span>|<span data-ttu-id="cf66b-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="cf66b-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cf66b-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cf66b-117">Affected APIs</span></span>

-<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
