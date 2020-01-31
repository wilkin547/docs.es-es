---
title: ICorProfilerCallback::ExceptionCLRCatcherExecute (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: f14dff33217656c35379a214f007ccb3642ef4b1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866460"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="a1ed8-102">ICorProfilerCallback::ExceptionCLRCatcherExecute (Método)</span><span class="sxs-lookup"><span data-stu-id="a1ed8-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="a1ed8-103">Se llama cuando se ejecuta un bloque `catch` para una excepción dentro del propio Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a1ed8-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="a1ed8-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="a1ed8-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1ed8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1ed8-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a1ed8-106">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="a1ed8-106">Requirements</span></span>  
 <span data-ttu-id="a1ed8-107">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1ed8-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1ed8-108">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1ed8-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1ed8-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1ed8-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1ed8-110">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="a1ed8-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ed8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1ed8-111">See also</span></span>

- [<span data-ttu-id="a1ed8-112">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1ed8-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a1ed8-113">ExceptionCLRCatcherFound (método)</span><span class="sxs-lookup"><span data-stu-id="a1ed8-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
