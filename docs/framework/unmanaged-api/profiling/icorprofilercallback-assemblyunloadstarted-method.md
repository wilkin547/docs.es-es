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
ms.openlocfilehash: bb7dade1ccd46cb9e13d45468c2ca2a8b451b70b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700306"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="2ca29-102">ICorProfilerCallback::AssemblyUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="2ca29-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>

<span data-ttu-id="2ca29-103">Notifica al generador de perfiles que se está descargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ca29-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca29-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ca29-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ca29-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ca29-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="2ca29-106">\[en] identifica el ensamblado que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="2ca29-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="2ca29-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ca29-107">Remarks</span></span>  

 <span data-ttu-id="2ca29-108">El valor de `assemblyId` no es válido para una solicitud de información después de que se `AssemblyUnloadStarted` devuelva el método; esta es la última oportunidad del generador de perfiles para obtener información sobre este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ca29-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ca29-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ca29-109">Requirements</span></span>  

 <span data-ttu-id="2ca29-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ca29-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ca29-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2ca29-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2ca29-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ca29-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ca29-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ca29-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca29-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ca29-114">See also</span></span>

- [<span data-ttu-id="2ca29-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ca29-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2ca29-116">Método AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="2ca29-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
