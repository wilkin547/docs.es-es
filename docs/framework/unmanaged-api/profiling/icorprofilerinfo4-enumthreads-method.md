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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd0a4149b6dc6023579e8bc5b40751d23416e3a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202370"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="35b6e-102">ICorProfilerInfo4::EnumThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="35b6e-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="35b6e-103">Devuelve un enumerador que proporciona métodos para iterar secuencialmente por la colección de todos los subprocesos administrados en el proceso de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="35b6e-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b6e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35b6e-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35b6e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35b6e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="35b6e-106">[out] Un puntero a un [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="35b6e-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35b6e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35b6e-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35b6e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35b6e-108">Requirements</span></span>  
 <span data-ttu-id="35b6e-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35b6e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b6e-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35b6e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35b6e-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35b6e-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="35b6e-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="35b6e-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="35b6e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="35b6e-113">See also</span></span>

- [<span data-ttu-id="35b6e-114">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35b6e-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="35b6e-115">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35b6e-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="35b6e-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="35b6e-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="35b6e-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="35b6e-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
