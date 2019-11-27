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
ms.openlocfilehash: 047516574595f9ffcd61360f51823da73a2f9733
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439519"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="efb26-102">ICorProfilerCallback3::InitializeForAttach (Método)</span><span class="sxs-lookup"><span data-stu-id="efb26-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="efb26-103">Lo llama Common Language Runtime (CLR) para dar al generador de perfiles una oportunidad de inicializar su estado después de una operación de adjuntar.</span><span class="sxs-lookup"><span data-stu-id="efb26-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efb26-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efb26-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="efb26-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="efb26-106">[in] Puntero de interfaz para la interfaz `ICorProfilerInfo*`.</span><span class="sxs-lookup"><span data-stu-id="efb26-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="efb26-107">de Un puntero a los datos pasados al método [IClrProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) en su parámetro `pvClientData`.</span><span class="sxs-lookup"><span data-stu-id="efb26-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="efb26-108">Si este parámetro es nulo, `cbClientData` será 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="efb26-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="efb26-109">CLR libera esta memoria cuando vuelve de `InitializeForAttach`.</span><span class="sxs-lookup"><span data-stu-id="efb26-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="efb26-110">[in] Tamaño, en bytes, de los datos a los que señala `pvClientData`.</span><span class="sxs-lookup"><span data-stu-id="efb26-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efb26-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efb26-111">Remarks</span></span>  
 <span data-ttu-id="efb26-112">CLR llama a `InitializeForAttach` para dar al generador de perfiles una oportunidad de solicitar devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="efb26-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb26-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efb26-113">Requirements</span></span>  
 <span data-ttu-id="efb26-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efb26-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb26-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="efb26-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="efb26-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efb26-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efb26-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb26-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb26-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="efb26-118">See also</span></span>

- [<span data-ttu-id="efb26-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="efb26-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="efb26-120">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="efb26-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="efb26-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="efb26-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="efb26-122">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="efb26-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
