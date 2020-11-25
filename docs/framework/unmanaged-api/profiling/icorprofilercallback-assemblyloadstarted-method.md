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
ms.openlocfilehash: c2fbc0ae8cdeb79b65cbad9a055a8051acf67e50
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700423"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="602a6-102">ICorProfilerCallback::AssemblyLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="602a6-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>

<span data-ttu-id="602a6-103">Notifica al generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="602a6-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="602a6-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="602a6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="602a6-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="602a6-106">\[in] identifica el ensamblado que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="602a6-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="602a6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="602a6-107">Remarks</span></span>  

 <span data-ttu-id="602a6-108">El valor de `assemblyId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: AssemblyLoadFinished (](icorprofilercallback-assemblyloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="602a6-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="602a6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="602a6-109">Requirements</span></span>  

 <span data-ttu-id="602a6-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="602a6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="602a6-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="602a6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="602a6-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="602a6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="602a6-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="602a6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602a6-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="602a6-114">See also</span></span>

- [<span data-ttu-id="602a6-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="602a6-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
