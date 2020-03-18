---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858575"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="a8466-101">Los generadores de perfiles no enumeran COR_PRF_GC_ROOT_HANDLE</span><span class="sxs-lookup"><span data-stu-id="a8466-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a8466-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a8466-102">Details</span></span>|<span data-ttu-id="a8466-103">En .NET Framework v4.5.1, el método <code>RootReferences2()</code> de la API de generación de perfiles de manera incorrecta nunca devuelve <code>COR_PRF_GC_ROOT_HANDLE</code> (en su lugar se devuelven como <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="a8466-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="a8466-104">Este problema se corrigió a partir de .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="a8466-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="a8466-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a8466-105">Suggestion</span></span>|<span data-ttu-id="a8466-106">Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8466-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="a8466-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a8466-107">Scope</span></span>|<span data-ttu-id="a8466-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="a8466-108">Minor</span></span>|
|<span data-ttu-id="a8466-109">Versión</span><span class="sxs-lookup"><span data-stu-id="a8466-109">Version</span></span>|<span data-ttu-id="a8466-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a8466-110">4.5.1</span></span>|
|<span data-ttu-id="a8466-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="a8466-111">Type</span></span>|<span data-ttu-id="a8466-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a8466-112">Runtime</span></span>|
