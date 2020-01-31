---
title: ICorProfilerInfo4::EnumThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
ms.openlocfilehash: 5bea1b75e94d8011d3582d4f07d36bbc7a560502
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862222"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="e4744-102">ICorProfilerInfo4::EnumThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="e4744-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="e4744-103">Devuelve un enumerador que proporciona métodos para recorrer secuencialmente en iteración la colección de todos los subprocesos administrados en el proceso de la que se van a realizar perfiles.</span><span class="sxs-lookup"><span data-stu-id="e4744-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4744-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4744-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4744-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="e4744-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="e4744-106">enuncia Puntero a una interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e4744-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4744-107">Notas</span><span class="sxs-lookup"><span data-stu-id="e4744-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4744-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e4744-108">Requirements</span></span>  
 <span data-ttu-id="e4744-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4744-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4744-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4744-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4744-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4744-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4744-112">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4744-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4744-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4744-113">See also</span></span>

- [<span data-ttu-id="e4744-114">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4744-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="e4744-115">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4744-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="e4744-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e4744-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e4744-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e4744-117">Profiling</span></span>](index.md)
