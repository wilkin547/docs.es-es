---
description: 'Más información sobre: ICorProfilerInfo12:: EventPipeStopSession (método)'
title: 'ICorProfilerInfo12:: EventPipeStopSession (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeStopSession
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c1b104f63755bcec52a113be7e2aa9af76ecd34e
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805719"
---
# <a name="icorprofilerinfo12eventpipestopsession-method"></a><span data-ttu-id="cabb7-103">ICorProfilerInfo12:: EventPipeStopSession (método)</span><span class="sxs-lookup"><span data-stu-id="cabb7-103">ICorProfilerInfo12::EventPipeStopSession Method</span></span>

<span data-ttu-id="cabb7-104">Detiene una sesión de EventPipe, evitando que se escriban eventos futuros en la sesión.</span><span class="sxs-lookup"><span data-stu-id="cabb7-104">Stops an EventPipe session, preventing any future events from being written to the session.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="cabb7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cabb7-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeStopSession(
        [in] EVENTPIPE_SESSION session);
```  
  
## <a name="parameters"></a><span data-ttu-id="cabb7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cabb7-106">Parameters</span></span>

<span data-ttu-id="cabb7-107">`session` de IDENTIFICADOR de la sesión que se va a detener.</span><span class="sxs-lookup"><span data-stu-id="cabb7-107">`session` [in] The ID of the session to stop.</span></span>

## <a name="requirements"></a><span data-ttu-id="cabb7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cabb7-108">Requirements</span></span>  

<span data-ttu-id="cabb7-109">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="cabb7-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="cabb7-110">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cabb7-110">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cabb7-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cabb7-111">See also</span></span>

- [<span data-ttu-id="cabb7-112">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="cabb7-112">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="cabb7-113">Interfaz ICorProfilerCallback10</span><span class="sxs-lookup"><span data-stu-id="cabb7-113">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="cabb7-114">Interfaz ICorProfilerInfo12</span><span class="sxs-lookup"><span data-stu-id="cabb7-114">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
