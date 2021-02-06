---
description: 'Más información sobre: ICorProfilerCallback:: Assemblyunloadstarted ((método)'
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
ms.openlocfilehash: e9c72d481df7242f305b5efa6f747866984b31f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657845"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="35dc2-103">ICorProfilerCallback::AssemblyUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="35dc2-103">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>

<span data-ttu-id="35dc2-104">Notifica al generador de perfiles que se está descargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="35dc2-104">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35dc2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35dc2-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35dc2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35dc2-106">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="35dc2-107">\[en] identifica el ensamblado que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="35dc2-107">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="35dc2-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35dc2-108">Remarks</span></span>  

 <span data-ttu-id="35dc2-109">El valor de `assemblyId` no es válido para una solicitud de información después de que se `AssemblyUnloadStarted` devuelva el método; esta es la última oportunidad del generador de perfiles para obtener información sobre este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="35dc2-109">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35dc2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35dc2-110">Requirements</span></span>  

 <span data-ttu-id="35dc2-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35dc2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35dc2-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35dc2-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35dc2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35dc2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35dc2-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35dc2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35dc2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="35dc2-115">See also</span></span>

- [<span data-ttu-id="35dc2-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35dc2-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="35dc2-117">Método AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="35dc2-117">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
