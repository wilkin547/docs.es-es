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
ms.openlocfilehash: df172edb97a82ae3bf2d46c8be6ea05d5445a09a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500434"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="a5f41-102">ICorProfilerCallback::AssemblyLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="a5f41-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="a5f41-103">Notifica al generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a5f41-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5f41-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5f41-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5f41-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5f41-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="a5f41-106">\[in] identifica el ensamblado que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="a5f41-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="a5f41-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5f41-107">Remarks</span></span>  
 <span data-ttu-id="a5f41-108">El valor de `assemblyId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: AssemblyLoadFinished (](icorprofilercallback-assemblyloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a5f41-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5f41-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5f41-109">Requirements</span></span>  
 <span data-ttu-id="a5f41-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5f41-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5f41-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5f41-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5f41-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5f41-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5f41-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5f41-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f41-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a5f41-114">See also</span></span>

- [<span data-ttu-id="a5f41-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5f41-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
