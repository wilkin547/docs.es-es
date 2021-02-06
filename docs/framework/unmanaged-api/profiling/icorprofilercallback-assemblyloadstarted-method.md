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
ms.openlocfilehash: f771008b9aed9322f0c5fd279fa9dfb3086755e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648024"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="1791a-103">ICorProfilerCallback::AssemblyLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="1791a-103">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>

<span data-ttu-id="1791a-104">Notifica al generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1791a-104">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1791a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1791a-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1791a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1791a-106">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="1791a-107">\[in] identifica el ensamblado que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="1791a-107">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="1791a-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1791a-108">Remarks</span></span>  

 <span data-ttu-id="1791a-109">El valor de `assemblyId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: AssemblyLoadFinished (](icorprofilercallback-assemblyloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1791a-109">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1791a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1791a-110">Requirements</span></span>  

 <span data-ttu-id="1791a-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1791a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1791a-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1791a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1791a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1791a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1791a-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1791a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1791a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1791a-115">See also</span></span>

- [<span data-ttu-id="1791a-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1791a-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
