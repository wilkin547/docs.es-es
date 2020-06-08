---
title: ICorProfilerCallback::ExceptionCLRCatcherFound (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
ms.openlocfilehash: 4f4d53b086453adce38902518f2de3dde1f2812f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500252"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="4985a-102">ICorProfilerCallback::ExceptionCLRCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="4985a-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="4985a-103">Llamado cuando `catch` se encuentra un bloque para una excepción dentro del propio Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4985a-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="4985a-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="4985a-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4985a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4985a-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="4985a-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4985a-106">Requirements</span></span>  
 <span data-ttu-id="4985a-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4985a-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4985a-108">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4985a-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4985a-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4985a-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4985a-110">**Versión de .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="4985a-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4985a-111">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="4985a-111">See also</span></span>

- [<span data-ttu-id="4985a-112">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4985a-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4985a-113">Método ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="4985a-113">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)
