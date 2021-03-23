---
description: 'Más información sobre: ICorProfilerInfo12:: EventPipeAddProviderToSession (método)'
title: 'ICorProfilerInfo12:: EventPipeAddProviderToSession (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeAddProviderToSession
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 70654660c496211c20459ef9ba37dfbd96b829b3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805693"
---
# <a name="icorprofilerinfo12eventpipeaddprovidertosession-method"></a><span data-ttu-id="73bb2-103">ICorProfilerInfo12:: EventPipeAddProviderToSession (método)</span><span class="sxs-lookup"><span data-stu-id="73bb2-103">ICorProfilerInfo12::EventPipeAddProviderToSession Method</span></span>

<span data-ttu-id="73bb2-104">Agrega un proveedor a una sesión de EventPipe existente.</span><span class="sxs-lookup"><span data-stu-id="73bb2-104">Adds a provider to an existing EventPipe session.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="73bb2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73bb2-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeAddProviderToSession(
        [in] EVENTPIPE_SESSION                 session,
        [in] COR_PRF_EVENTPIPE_PROVIDER_CONFIG providerConfig);
```  
  
## <a name="parameters"></a><span data-ttu-id="73bb2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73bb2-106">Parameters</span></span>

<span data-ttu-id="73bb2-107">`session` de IDENTIFICADOR de la sesión a la que se va a agregar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="73bb2-107">`session` [in] The ID of the session to add the provider to.</span></span>

<span data-ttu-id="73bb2-108">`providerConfig` de `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` Que describe el proveedor que se va a agregar a la sesión.</span><span class="sxs-lookup"><span data-stu-id="73bb2-108">`providerConfig` [in] A `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` describing the provider to add to the session.</span></span>

## <a name="requirements"></a><span data-ttu-id="73bb2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73bb2-109">Requirements</span></span>  

<span data-ttu-id="73bb2-110">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="73bb2-110">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="73bb2-111">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73bb2-111">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="73bb2-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73bb2-112">See also</span></span>

- [<span data-ttu-id="73bb2-113">Información general sobre EventPipe</span><span class="sxs-lookup"><span data-stu-id="73bb2-113">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="73bb2-114">EventProviders conocidos</span><span class="sxs-lookup"><span data-stu-id="73bb2-114">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="73bb2-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="73bb2-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="73bb2-116">Interfaz ICorProfilerCallback10</span><span class="sxs-lookup"><span data-stu-id="73bb2-116">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="73bb2-117">Interfaz ICorProfilerInfo12</span><span class="sxs-lookup"><span data-stu-id="73bb2-117">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="73bb2-118">Estructura de COR_PRF_EVENTPIPE_PROVIDER_CONFIG</span><span class="sxs-lookup"><span data-stu-id="73bb2-118">COR_PRF_EVENTPIPE_PROVIDER_CONFIG Structure</span></span>](cor-prf-eventpipe-provider-config-structure.md)
