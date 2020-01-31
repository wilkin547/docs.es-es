---
title: ICorProfilerCallback::AssemblyUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: 4c14b3e8b9d0116d638e2983955598a6c51c405a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790203"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="02278-102">ICorProfilerCallback::AssemblyUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="02278-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="02278-103">Notifica al generador de perfiles que se está descargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02278-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02278-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02278-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02278-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="02278-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="02278-106">\[en] identifica el ensamblado que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="02278-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="02278-107">Notas</span><span class="sxs-lookup"><span data-stu-id="02278-107">Remarks</span></span>  
 <span data-ttu-id="02278-108">El valor de `assemblyId` no es válido para una solicitud de información después de que se devuelva el método `AssemblyUnloadStarted`; esta es la última oportunidad del generador de perfiles para obtener información sobre este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="02278-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02278-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="02278-109">Requirements</span></span>  
 <span data-ttu-id="02278-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02278-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02278-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02278-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02278-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02278-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02278-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02278-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02278-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="02278-114">See also</span></span>

- [<span data-ttu-id="02278-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02278-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="02278-116">AssemblyUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="02278-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
