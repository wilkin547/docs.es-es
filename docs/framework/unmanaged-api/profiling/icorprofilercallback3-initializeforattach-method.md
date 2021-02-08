---
description: 'Más información acerca de: ICorProfilerCallback3:: InitializeForAttach (método)'
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
ms.openlocfilehash: b3c5b8701df9e680e4fcbd57f4e08395dfe0b8da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788818"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="10d8f-103">ICorProfilerCallback3::InitializeForAttach (Método)</span><span class="sxs-lookup"><span data-stu-id="10d8f-103">ICorProfilerCallback3::InitializeForAttach Method</span></span>

<span data-ttu-id="10d8f-104">Lo llama Common Language Runtime (CLR) para dar al generador de perfiles una oportunidad de inicializar su estado después de una operación de adjuntar.</span><span class="sxs-lookup"><span data-stu-id="10d8f-104">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10d8f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10d8f-105">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10d8f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10d8f-106">Parameters</span></span>  

 `pCorProfilerInfoUnk`  
 <span data-ttu-id="10d8f-107">[in] Puntero de interfaz para la interfaz `ICorProfilerInfo*`.</span><span class="sxs-lookup"><span data-stu-id="10d8f-107">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="10d8f-108">de Un puntero a los datos pasados al método [IClrProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) en su `pvClientData` parámetro.</span><span class="sxs-lookup"><span data-stu-id="10d8f-108">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="10d8f-109">Si este parámetro es nulo, `cbClientData` será 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="10d8f-109">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="10d8f-110">CLR libera esta memoria cuando vuelve de `InitializeForAttach`.</span><span class="sxs-lookup"><span data-stu-id="10d8f-110">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="10d8f-111">[in] Tamaño, en bytes, de los datos a los que señala `pvClientData`.</span><span class="sxs-lookup"><span data-stu-id="10d8f-111">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10d8f-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="10d8f-112">Remarks</span></span>  

 <span data-ttu-id="10d8f-113">CLR llama a `InitializeForAttach` para dar al generador de perfiles una oportunidad de solicitar devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="10d8f-113">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10d8f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10d8f-114">Requirements</span></span>  

 <span data-ttu-id="10d8f-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10d8f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10d8f-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10d8f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="10d8f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10d8f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10d8f-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10d8f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d8f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="10d8f-119">See also</span></span>

- [<span data-ttu-id="10d8f-120">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10d8f-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="10d8f-121">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10d8f-121">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="10d8f-122">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="10d8f-122">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="10d8f-123">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="10d8f-123">Profiling</span></span>](index.md)
