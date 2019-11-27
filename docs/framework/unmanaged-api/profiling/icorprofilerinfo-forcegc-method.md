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
ms.openlocfilehash: 9f97da4e68d4b76178198e91c3fb8f08b56dda7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448190"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="1c741-102">ICorProfilerInfo::ForceGC (Método)</span><span class="sxs-lookup"><span data-stu-id="1c741-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="1c741-103">Fuerza la recolección de elementos no utilizados en el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1c741-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c741-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c741-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1c741-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c741-105">Remarks</span></span>  
 <span data-ttu-id="1c741-106">Solo se debe llamar al método `ForceGC` desde un subproceso que nunca ha ejecutado código administrado y no tiene ninguna devolución de llamada del generador de perfiles en su pila.</span><span class="sxs-lookup"><span data-stu-id="1c741-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="1c741-107">La implementación más cómoda es crear un subproceso independiente en el generador de perfiles que llama a `ForceGC` cuando se señala.</span><span class="sxs-lookup"><span data-stu-id="1c741-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c741-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c741-108">Requirements</span></span>  
 <span data-ttu-id="1c741-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c741-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c741-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c741-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c741-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c741-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c741-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c741-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c741-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c741-113">See also</span></span>

- [<span data-ttu-id="1c741-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c741-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
