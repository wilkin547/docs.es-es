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
ms.openlocfilehash: d6af5aec4f1a012b6ec33cf80b1de62a7397262d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442988"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="a778b-102">ICorProfilerInfo4::EnumThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="a778b-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="a778b-103">Devuelve un enumerador que proporciona métodos para recorrer secuencialmente en iteración la colección de todos los subprocesos administrados en el proceso de la que se van a realizar perfiles.</span><span class="sxs-lookup"><span data-stu-id="a778b-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a778b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a778b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a778b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a778b-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a778b-106">enuncia Puntero a una interfaz [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a778b-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a778b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a778b-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a778b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a778b-108">Requirements</span></span>  
 <span data-ttu-id="a778b-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a778b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a778b-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a778b-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a778b-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a778b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a778b-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a778b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a778b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a778b-113">See also</span></span>

- [<span data-ttu-id="a778b-114">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a778b-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="a778b-115">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a778b-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="a778b-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a778b-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="a778b-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a778b-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
