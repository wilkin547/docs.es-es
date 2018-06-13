---
title: ICorProfilerCallback3::InitializeForAttach (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50fe7399896c35c1d6595b2d7214280e3009fab5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455806"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="900c4-102">ICorProfilerCallback3::InitializeForAttach (Método)</span><span class="sxs-lookup"><span data-stu-id="900c4-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="900c4-103">Lo llama Common Language Runtime (CLR) para dar al generador de perfiles una oportunidad de inicializar su estado después de una operación de adjuntar.</span><span class="sxs-lookup"><span data-stu-id="900c4-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="900c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="900c4-104">Syntax</span></span>  
  
```  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="900c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="900c4-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="900c4-106">[in] Puntero de interfaz para la interfaz `ICorProfilerInfo*`.</span><span class="sxs-lookup"><span data-stu-id="900c4-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="900c4-107">[in] Pasa un puntero a los datos a la [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) método en su `pvClientData` parámetro.</span><span class="sxs-lookup"><span data-stu-id="900c4-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="900c4-108">Si este parámetro es nulo, `cbClientData` será 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="900c4-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="900c4-109">CLR libera esta memoria cuando vuelve de `InitializeForAttach`.</span><span class="sxs-lookup"><span data-stu-id="900c4-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="900c4-110">[in] Tamaño, en bytes, de los datos a los que señala `pvClientData`.</span><span class="sxs-lookup"><span data-stu-id="900c4-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="900c4-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="900c4-111">Remarks</span></span>  
 <span data-ttu-id="900c4-112">CLR llama a `InitializeForAttach` para dar al generador de perfiles una oportunidad de solicitar devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="900c4-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="900c4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="900c4-113">Requirements</span></span>  
 <span data-ttu-id="900c4-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="900c4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="900c4-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="900c4-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="900c4-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="900c4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="900c4-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="900c4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="900c4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="900c4-118">See Also</span></span>  
 [<span data-ttu-id="900c4-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="900c4-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="900c4-120">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="900c4-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="900c4-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="900c4-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="900c4-122">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="900c4-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
