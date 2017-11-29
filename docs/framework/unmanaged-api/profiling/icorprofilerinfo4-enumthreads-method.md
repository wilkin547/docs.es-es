---
title: "ICorProfilerInfo4::EnumThreads (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.EnumThreads
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 20022a3b7353c0e43aaa44e368c06cd79906956e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="8d02e-102">ICorProfilerInfo4::EnumThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="8d02e-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="8d02e-103">Devuelve un enumerador que proporciona métodos para iterar secuencialmente por la colección de todos los subprocesos administrados en el proceso perfilado.</span><span class="sxs-lookup"><span data-stu-id="8d02e-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d02e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d02e-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d02e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d02e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="8d02e-106">[out] Un puntero a un [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="8d02e-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d02e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d02e-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d02e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d02e-108">Requirements</span></span>  
 <span data-ttu-id="8d02e-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d02e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d02e-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d02e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d02e-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d02e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d02e-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d02e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d02e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d02e-113">See Also</span></span>  
 [<span data-ttu-id="8d02e-114">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d02e-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="8d02e-115">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d02e-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="8d02e-116">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8d02e-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="8d02e-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8d02e-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
