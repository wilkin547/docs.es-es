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
ms.openlocfilehash: 0a677e33950f178b916a5e9e9cbb7bd918c1349b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866616"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="68c56-102">ICorProfilerCallback::AssemblyUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="68c56-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="68c56-103">Notifica al generador de perfiles que se está descargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="68c56-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68c56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68c56-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68c56-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="68c56-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="68c56-106">\[en] identifica el ensamblado que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="68c56-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="68c56-107">Notas</span><span class="sxs-lookup"><span data-stu-id="68c56-107">Remarks</span></span>  
 <span data-ttu-id="68c56-108">El valor de `assemblyId` no es válido para una solicitud de información después de que se devuelva el método `AssemblyUnloadStarted`; esta es la última oportunidad del generador de perfiles para obtener información sobre este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="68c56-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68c56-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="68c56-109">Requirements</span></span>  
 <span data-ttu-id="68c56-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68c56-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68c56-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="68c56-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="68c56-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68c56-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68c56-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68c56-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68c56-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="68c56-114">See also</span></span>

- [<span data-ttu-id="68c56-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="68c56-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="68c56-116">AssemblyUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="68c56-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
