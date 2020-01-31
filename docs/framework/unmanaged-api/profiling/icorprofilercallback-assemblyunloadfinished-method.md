---
title: ICorProfilerCallback::AssemblyUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: 734ae1d14d02d47c7d3126f1b4cf55dcb4ad151b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866629"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="48090-102">ICorProfilerCallback::AssemblyUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="48090-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="48090-103">Notifica al generador de perfiles que se ha descargado un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="48090-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48090-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48090-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48090-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="48090-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="48090-106">\[en] identifica el ensamblado que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="48090-106">\[in] Identifies the assembly that is being unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="48090-107">\[in] un valor HRESULT que indica si el ensamblado se ha descargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="48090-107">\[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="48090-108">Notas</span><span class="sxs-lookup"><span data-stu-id="48090-108">Remarks</span></span>  
 <span data-ttu-id="48090-109">El valor de `assemblyId` no es válido para una solicitud de información después de que se devuelva el método [ICorProfilerCallback:: assemblyunloadstarted (](icorprofilercallback-assemblyunloadstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="48090-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="48090-110">Algunas partes de la descarga del ensamblado pueden continuar después de la devolución de llamada de `AssemblyUnloadFinished`.</span><span class="sxs-lookup"><span data-stu-id="48090-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="48090-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="48090-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="48090-112">Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la descarga del ensamblado se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="48090-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48090-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="48090-113">Requirements</span></span>  
 <span data-ttu-id="48090-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48090-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48090-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48090-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48090-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48090-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48090-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48090-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48090-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="48090-118">See also</span></span>

- [<span data-ttu-id="48090-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48090-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
