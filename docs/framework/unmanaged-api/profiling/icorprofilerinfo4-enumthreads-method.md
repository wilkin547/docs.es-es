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
ms.openlocfilehash: 6c394690f6c8d7f3618b385b0a1432fc396fb819
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458025"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="5fdc6-102">ICorProfilerInfo4::EnumThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="5fdc6-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="5fdc6-103">Devuelve un enumerador que proporciona métodos para iterar secuencialmente por la colección de todos los subprocesos administrados en el proceso perfilado.</span><span class="sxs-lookup"><span data-stu-id="5fdc6-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fdc6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fdc6-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5fdc6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fdc6-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5fdc6-106">[out] Un puntero a un [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="5fdc6-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fdc6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fdc6-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fdc6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fdc6-108">Requirements</span></span>  
 <span data-ttu-id="5fdc6-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fdc6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fdc6-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5fdc6-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5fdc6-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fdc6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fdc6-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fdc6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fdc6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fdc6-113">See Also</span></span>  
 [<span data-ttu-id="5fdc6-114">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fdc6-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="5fdc6-115">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fdc6-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="5fdc6-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5fdc6-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="5fdc6-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5fdc6-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
