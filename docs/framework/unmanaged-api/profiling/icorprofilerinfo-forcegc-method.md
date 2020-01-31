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
ms.openlocfilehash: e1fe38419cda328c919f0840d51cf6336919aa60
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864250"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="b2dc9-102">ICorProfilerInfo::ForceGC (Método)</span><span class="sxs-lookup"><span data-stu-id="b2dc9-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="b2dc9-103">Fuerza la recolección de elementos no utilizados en el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b2dc9-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2dc9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2dc9-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b2dc9-105">Notas</span><span class="sxs-lookup"><span data-stu-id="b2dc9-105">Remarks</span></span>  
 <span data-ttu-id="b2dc9-106">Solo se debe llamar al método `ForceGC` desde un subproceso que nunca ha ejecutado código administrado y no tiene ninguna devolución de llamada del generador de perfiles en su pila.</span><span class="sxs-lookup"><span data-stu-id="b2dc9-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="b2dc9-107">La implementación más cómoda es crear un subproceso independiente en el generador de perfiles que llama a `ForceGC` cuando se señala.</span><span class="sxs-lookup"><span data-stu-id="b2dc9-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2dc9-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b2dc9-108">Requirements</span></span>  
 <span data-ttu-id="b2dc9-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2dc9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2dc9-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2dc9-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2dc9-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2dc9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2dc9-112">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2dc9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2dc9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2dc9-113">See also</span></span>

- [<span data-ttu-id="b2dc9-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2dc9-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
