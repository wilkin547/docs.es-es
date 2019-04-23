---
title: ICorProfilerInfo::ForceGC (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5672d1b89b4260d1ebfbf444deb2702f215a0e95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078088"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="4e918-102">ICorProfilerInfo::ForceGC (Método)</span><span class="sxs-lookup"><span data-stu-id="4e918-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="4e918-103">Fuerza la recolección que se produzca dentro de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4e918-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e918-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e918-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4e918-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e918-105">Remarks</span></span>  
 <span data-ttu-id="4e918-106">El `ForceGC` método debe llamarse únicamente desde un subproceso que nunca se ha ejecutado el código administrado y no tiene las devoluciones de llamada del generador de perfiles en su pila.</span><span class="sxs-lookup"><span data-stu-id="4e918-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="4e918-107">La implementación más conveniente consiste en crear un subproceso independiente en el generador de perfiles llama a `ForceGC` cuando está señalado.</span><span class="sxs-lookup"><span data-stu-id="4e918-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e918-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e918-108">Requirements</span></span>  
 <span data-ttu-id="4e918-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e918-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e918-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e918-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e918-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e918-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e918-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e918-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e918-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e918-113">See also</span></span>

- [<span data-ttu-id="4e918-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e918-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
