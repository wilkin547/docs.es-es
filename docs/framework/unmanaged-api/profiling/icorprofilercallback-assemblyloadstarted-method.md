---
description: 'Más información sobre: ICorProfilerCallback:: AssemblyLoadStarted ((método)'
title: ICorProfilerCallback::AssemblyLoadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
ms.openlocfilehash: 19737fc284d49c3690f66e4881450ca5803622e3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760612"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="c8265-103">ICorProfilerCallback::AssemblyLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="c8265-103">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>

<span data-ttu-id="c8265-104">Notifica al generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c8265-104">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8265-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8265-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8265-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8265-106">Parameters</span></span>

<span data-ttu-id="c8265-107">`assemblyId` de Identifica el ensamblado que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="c8265-107">`assemblyId` [in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8265-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c8265-108">Remarks</span></span>  

 <span data-ttu-id="c8265-109">El valor de `assemblyId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: AssemblyLoadFinished (](icorprofilercallback-assemblyloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c8265-109">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8265-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8265-110">Requirements</span></span>  

 <span data-ttu-id="c8265-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8265-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8265-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c8265-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8265-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8265-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8265-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8265-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8265-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8265-115">See also</span></span>

- [<span data-ttu-id="c8265-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8265-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
