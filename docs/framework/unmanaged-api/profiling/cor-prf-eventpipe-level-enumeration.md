---
description: 'Más información acerca de: enumeración COR_PRF_EVENTPIPE_LEVEL'
title: Enumeración COR_PRF_EVENTPIPE_LEVEL
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_LEVEL
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: da8211da1a9bb6262b078c5e56bee1d0c1f9342e
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805823"
---
# <a name="cor_prf_eventpipe_level-enumeration"></a><span data-ttu-id="313e1-103">Enumeración COR_PRF_EVENTPIPE_LEVEL</span><span class="sxs-lookup"><span data-stu-id="313e1-103">COR_PRF_EVENTPIPE_LEVEL Enumeration</span></span>

<span data-ttu-id="313e1-104">Describe el nivel de un evento EventPipe.</span><span class="sxs-lookup"><span data-stu-id="313e1-104">Describes the level of an EventPipe event.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="313e1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="313e1-105">Syntax</span></span>  
  
```cpp  
typedef enum
{
    COR_PRF_EVENTPIPE_LOGALWAYS = 0,
    COR_PRF_EVENTPIPE_CRITICAL = 1,
    COR_PRF_EVENTPIPE_ERROR = 2,
    COR_PRF_EVENTPIPE_WARNING = 3,
    COR_PRF_EVENTPIPE_INFORMATIONAL = 4,
    COR_PRF_EVENTPIPE_VERBOSE = 5
} COR_PRF_EVENTPIPE_LEVEL;
```  
  
## <a name="members"></a><span data-ttu-id="313e1-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="313e1-106">Members</span></span>  
  
|<span data-ttu-id="313e1-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="313e1-107">Member</span></span>|<span data-ttu-id="313e1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="313e1-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_EVENTPIPE_LOGALWAYS`|<span data-ttu-id="313e1-109">El evento siempre se registra.</span><span class="sxs-lookup"><span data-stu-id="313e1-109">The event is always logged.</span></span>|
|`COR_PRF_EVENTPIPE_CRITICAL`|<span data-ttu-id="313e1-110">El evento representa un mensaje crítico.</span><span class="sxs-lookup"><span data-stu-id="313e1-110">The event represents a critical message.</span></span>|
|`COR_PRF_EVENTPIPE_ERROR`|<span data-ttu-id="313e1-111">El evento representa un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="313e1-111">The event represents an error message.</span></span>|
|`COR_PRF_EVENTPIPE_WARNING`|<span data-ttu-id="313e1-112">El evento representa un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="313e1-112">The event represents a warning message.</span></span>|
|`COR_PRF_EVENTPIPE_INFORMATIONAL`|<span data-ttu-id="313e1-113">El evento representa un mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="313e1-113">The event represents an informational message.</span></span>|
|`COR_PRF_EVENTPIPE_VERBOSE`|<span data-ttu-id="313e1-114">El evento representa un mensaje detallado.</span><span class="sxs-lookup"><span data-stu-id="313e1-114">The event represents a verbose message.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="313e1-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="313e1-115">Remarks</span></span>  

 <span data-ttu-id="313e1-116">El `COR_PRF_EVENTPIPE_LEVEL` método [ICorProfilerInfo12:: EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) usa la enumeración para indicar el nivel del evento que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="313e1-116">The `COR_PRF_EVENTPIPE_LEVEL` enumeration is used by the [ICorProfilerInfo12::EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) method to indicate the level of the event being defined.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="313e1-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="313e1-117">Requirements</span></span>  

<span data-ttu-id="313e1-118">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="313e1-118">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="313e1-119">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="313e1-119">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="313e1-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="313e1-120">See also</span></span>

- [<span data-ttu-id="313e1-121">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="313e1-121">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="313e1-122">ICorProfilerInfo12::EventPipeDefineEvent</span><span class="sxs-lookup"><span data-stu-id="313e1-122">ICorProfilerInfo12::EventPipeDefineEvent</span></span>](icorprofilerinfo12-eventpipedefineevent-method.md)
