---
ms.openlocfilehash: 25437dcc0c814ed2265b2efb34316af48b372ebd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496189"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="29360-101">Los generadores de perfiles no enumeran COR_PRF_GC_ROOT_HANDLE</span><span class="sxs-lookup"><span data-stu-id="29360-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="29360-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="29360-102">Details</span></span>

<span data-ttu-id="29360-103">En .NET Framework v4.5.1, el método <code>RootReferences2()</code> de la API de generación de perfiles de manera incorrecta nunca devuelve <code>COR_PRF_GC_ROOT_HANDLE</code> (en su lugar se devuelven como <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="29360-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="29360-104">Este problema se corrigió a partir de .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="29360-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="29360-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="29360-105">Suggestion</span></span>

<span data-ttu-id="29360-106">Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29360-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="29360-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="29360-107">Name</span></span>    | <span data-ttu-id="29360-108">Valor</span><span class="sxs-lookup"><span data-stu-id="29360-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="29360-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="29360-109">Scope</span></span>   |<span data-ttu-id="29360-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="29360-110">Minor</span></span>|
|<span data-ttu-id="29360-111">Versión</span><span class="sxs-lookup"><span data-stu-id="29360-111">Version</span></span>|<span data-ttu-id="29360-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="29360-112">4.5.1</span></span>|
|<span data-ttu-id="29360-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="29360-113">Type</span></span>|<span data-ttu-id="29360-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="29360-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="29360-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="29360-115">Affected APIs</span></span>

<span data-ttu-id="29360-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="29360-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
