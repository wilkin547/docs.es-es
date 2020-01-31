---
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
ms.openlocfilehash: 9899ea8afc739207ad0b70e9720e90e5c7f09fcf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790189"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="138f5-102">ICorProfilerCallback::AssemblyLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="138f5-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="138f5-103">Notifica al generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="138f5-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="138f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="138f5-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="138f5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="138f5-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="138f5-106">\[en] identifica el ensamblado que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="138f5-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="138f5-107">Notas</span><span class="sxs-lookup"><span data-stu-id="138f5-107">Remarks</span></span>  
 <span data-ttu-id="138f5-108">El valor de `assemblyId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: AssemblyLoadFinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="138f5-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="138f5-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="138f5-109">Requirements</span></span>  
 <span data-ttu-id="138f5-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="138f5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="138f5-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="138f5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="138f5-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="138f5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="138f5-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="138f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138f5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="138f5-114">See also</span></span>

- [<span data-ttu-id="138f5-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="138f5-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
