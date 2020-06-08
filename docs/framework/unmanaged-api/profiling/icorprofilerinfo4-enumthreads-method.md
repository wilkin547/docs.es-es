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
ms.openlocfilehash: d42c86a458661d3559f99235a6d5b208c82d1963
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502813"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="0418e-102">ICorProfilerInfo4::EnumThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="0418e-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="0418e-103">Devuelve un enumerador que proporciona métodos para recorrer secuencialmente en iteración la colección de todos los subprocesos administrados en el proceso de la que se van a realizar perfiles.</span><span class="sxs-lookup"><span data-stu-id="0418e-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0418e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0418e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0418e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0418e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="0418e-106">enuncia Puntero a una interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0418e-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0418e-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0418e-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0418e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0418e-108">Requirements</span></span>  
 <span data-ttu-id="0418e-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0418e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0418e-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0418e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0418e-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0418e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0418e-112">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0418e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0418e-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0418e-113">See also</span></span>

- [<span data-ttu-id="0418e-114">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0418e-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="0418e-115">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0418e-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="0418e-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0418e-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="0418e-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0418e-117">Profiling</span></span>](index.md)
